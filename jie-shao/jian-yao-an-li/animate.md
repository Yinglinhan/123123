# Animate

这里，我们要让Frame标签的rotate属性产生动画效果。我们利用Frame标签的animate属性来设置一个新的rotate的值。同时，我们可以利用transition这个属性来自定义变化的一些设置，比如说我们可以定义一个变化的时长为5s。

[Open Example](https://codesandbox.io/s/ykppk6k3wv)

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  return (
    <Frame
      animate={{ rotate: 360 }}
      transition={{ duration: 1 }}
    />
  )
}

```



### Loop 循环变化

transition属性包含很多可以设置的属性用来让我们自定义想要的一些变化效果。在这个案例中，我们定义了一个无限循环的变化效果，我们把loop属性的值设置为Infinity，把ease属性的值设置linear，用以实现这个效果。这种动画效果比较适合用来做进度提示，尤其是作为加载旋转提示。

[Open Example](https://codesandbox.io/s/wqz8n1wk05)

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  return (
    <Frame
      animate={{ rotate: 360 }}
      transition={{
        duration: 2,
        loop: Infinity,
        ease: "linear",
      }}
    />
  )
}
```



### Cycle 两种状态切换

你可以利用Framer中useCycle方法来实现两种状态之间的动画切换效果。这个例子中，我们通过点击让Framer标签在两种状态值之间进行切换。

[Open Example](https://codesandbox.io/s/xl7nmv46wq)

```jsx
import * as React from "react"
import { Frame, useCycle } from "framer"

export function MyComponent() {
  const [animate, cycle] = useCycle(
    { scale: 1.5, rotate: 0 },
    { scale: 1.0, rotate: 90 }
  )

  return <Frame animate={animate} onTap={() => cycle()} />
}
```



### Color 颜色变化

Frame标签的背景颜色也能通过background属性来产生变化。在下面这个例子中，我们让Frame标签的颜色从在1秒的时间内从淡蓝色变化为紫色，然后再从紫色变回蓝色，一直循环不停。这是使用了yoy'o这个属性，让背景色的变化可以反向变化，同时yoyo的值设置成了Infinity，就是无限循环。

[Open Example](https://codesandbox.io/s/vv8ll0pmk7)

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  return (
    <Frame
      animate={{ background: "#85F" }}
      transition={{
        duration: 1,
        yoyo: Infinity,
      }}
      background={"#0CF"}
    />
  )
}
```



### Arrays 数组 

除了使用一个单一的值，你也可以把好几个值放到数组里面然后放在animate属性里面。在这个案例中，我们让Frame标签的颜色在2秒之内从几个颜色之间不停地来回切换。

[Open Example](https://codesandbox.io/s/o4j24j2zmq)

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  return (
    <Frame
      animate={{ background: ["#F05", "#85F", "#0CF"] }}
      transition={{
        duration: 2,
        yoyo: Infinity,
      }}
      background={"#0CF"}
    />
  )
}
```














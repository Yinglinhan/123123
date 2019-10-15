# useAnimation

**useAnimation\(\)**: AnimationControls

通过useAnimation能创建一个AnimationControls\(动画控制器\)，它能用来在多个组件中手动地控制动画的开始，结束或者进行**一定顺序的**动画。

AnimationControl需要被赋值给你想要进行控制的组件的animate属性。

这样组件就可以通过start方法进行启动了。

```jsx
import * as React from 'react'
import { Frame, useAnimation } from 'framer'

export function MyComponent(props) {
   const controls = useAnimation()

   controls.start({
       x: 100,
       transition: { duration: 0.5 },
   })

   return <Frame animate={controls} />
}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>returns: AnimationControls</p>
        <p>&#x8FD4;&#x56DE;AnimationContols&#x5BF9;&#x8C61;&#xFF0C;&#x8FD9;&#x4E2A;&#x5BF9;&#x8C61;&#x6709;start&#x548C;stop&#x65B9;&#x6CD5;</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

**Sequence**

动画能通过async、await方法进行按一定顺序依次执行，你能通过给start传递动画的参数，让每一步的动画都呈现不同的效果。start方法返回的是Promise对象。

在这一个案例中，我们让一个Frame元素依次移动了四次，每点击一次元素它移动一次，每一次的移动都是在上一次移动结束后才会进行。

```jsx
import * as React from "react"
import { Frame, useAnimation } from "framer"

export function MyComponent(props) {
  const controls = useAnimation()

  async function sequence() {
    await controls.start({ left: 100 })
    await controls.start({ top: 100 })
    await controls.start({ left: 0 })
    await controls.start({ top: 0 })
  }

  return <Frame animate={controls} onTap={sequence} />
}
```

\*\*\*\*

**Dynamic Start**

通过useAnimation返回的的控制器的start方法，可以接受一个函数，通过这个函数能够实现让每一个使用这个控制器的元素实现不同的动画设置。给这个函数设置一个形参，然后在组件上用custom这个属性把你想要传进去的数值传入到这个形参中。

这下面这个案例中，我们给控制器的函数设置一个index的参数，然后在组件上用custom属性来传递不同的额实参给它。

我们通过每个组件传递的index的值不同，给不同的组件设置了不同的delay延时的时间，因为这个时间就是在函数中设置的。这里第一个组件的delay是0.5，第二个组件的delay是1。这样，通过这个函数，就很快地创建了一个分步动画效果。

最后，我们给这两个Frame组件添加了一些尺寸、背景色、透明度的效果，这样我们就能很清楚的看到他们的动画效果了。

```jsx
import * as React from "react"
import { Frame, useAnimation } from "framer"

export function MyComponent(props) {
  const controls = useAnimation()

  controls.start(index => ({
    opacity: 1,
    transition: { delay: index * 0.5 },
  }))

  return (
    <Frame background="#09F">
      <Frame
        custom={0}
        opacity={0}
        animate={controls}
        size={50}
        background={"rgba(255,255,255,0.5)"}
      />
      <Frame
        custom={1}
        opacity={0}
        animate={controls}
        size={50}
        background={"rgba(255,255,255,0.25)"}
      />
    </Frame>
  )
}
```

start方法也可以接受variants的属性名称

```jsx
const controls = useAnimation()
const variants = {
  visible: { opacity: 1 },
  hidden: { opacity: 0 },
}

controls.start("visible")

return <Frame variants={variants} animate={controls} />
```

\*\*\*\*

**Stopping Animations**

所有正在进行中的动画，都可以通过animation.stop\(\)来停止。

```jsx
controls.stop()
```

\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*


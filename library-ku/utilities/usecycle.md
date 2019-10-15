# useCycle

**useCycle\(**c1, c2**\): \[**currentState,  cycleState**\]**

这个方法能实现在多个视觉属性设置中切换。它能让状态切换时产生自然的动画过渡。它的工作原理有点像React中的useState方法。你需要给这个方法传递几个参数，分别是当前的状态和将要切换的状态，然后它会返回一个数组，内含有两个参数，第一个是当前状态值，第二个是能触发切换的方法。

```jsx
import * as React from "react"
import { Frame, useCycle } from "framer"

export function MyComponent() {
  const [x, cycleX] = useCycle(0, 50, 100)

  return (
    <Frame
      animate={{ x: x }}
      onTap={() => cycleX()}
     />
   )
}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>items: T[]</p>
        <p>&#x60F3;&#x8981;&#x8FDB;&#x884C;&#x5207;&#x6362;&#x7684;&#x51E0;&#x4E2A;&#x72B6;&#x6001;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>returns: CycleState&lt;T&gt;</p>
        <p>[currentState, cycleState]</p>
      </td>
    </tr>
  </tbody>
</table>

**Cycling between Variants**

useCycle方法经常被用于和variants属性结合进行切换动画效果。

在这个案例中，我们定义了一个有三个属性装啊提的variants的对象，然后使用useCycle方法创建出了一个current变量和cycle方法，然后把current赋值到了Frame组件上的animate属性上，同时给onTap赋值了一个带有cycle方法的匿名函数。

这样的话，我们每次去点击Frame元素的时候，都会触发Frame的背景颜色向下一个variants的属性进行切换，因为你每次点击，current变量里的属性名称都会进行切换。

```jsx
import * as React from "react"
import { Frame, useCycle } from "framer"

export function MyComponent() {
  const variants = {
    green: { background: "#1ea463" },
    yellow: { background: "#fecd45" },
    red: { background: "#de5347" },
  }

  const [current, cycle] = useCycle(
    "green",
    "yellow",
    "red"
  )

  return (
    <Frame
      variants={variants}
      animate={current}
      onTap={() => cycle()}
    />
  )
}
```



**Cycling to a Specific Value**

你可以通过给useAnimation产生的cycle方法传递index参数，来切换到某个特定的样式。

在上一个案例中，我们每次店家Frame标签都会在三个variants属性名中依次切换。但是在我们这里，我们想要让他在鼠标离开Frame元素时立即到“green”状态，那么我就在cycle方法那里给它传递了一个0，0就是“green”这个状态在使用useCycle这个方法时的下标值。

```jsx
import * as React from "react"
import { Frame, useCycle } from "framer"

export function MyComponent() {
  const variants = {
    green: { background: "#1ea463" },
    yellow: { background: "#fecd45" },
    red: { background: "#de5347" },
  }

  const [current, cycle] = useCycle(
    "green",
    "yellow",
    "red"
  )

  return (
    <Frame
      variants={variants}
      animate={current}
      onTap={() => cycle()}
      onMouseLeave={() => cycle(0)}
    />
  )
}
```
















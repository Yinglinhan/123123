# Dragging 拖拽

你可以轻松让Frame标签可以拖拽，只要你给它设置一个drag属性。它能被设置成只能在单独一个方向上进行拖拽，你可以给drag这个属性赋值“x”或者“y”。如果它被设置了true或者不赋予任何值，那么它就可以在任意方向上进行拖拽。

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  return <Frame drag={true} />
}
```



### Constraints 拖拽限制区域

添加dragConstraints属性能够让你限制可以拖拽的区域。设置的时候你需要设置四个方向的数值，分别是top、bottom、left、right。

这四个方向设置的数值是以被设置的Frame标签的位置为参考品的，如果你想设置让这个Frame标签能向左拖拽100像素，那么你需要设置left为 -100；

[Open Example](https://codesandbox.io/s/53mv19r5r4)

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  return (
    <Frame
      drag={true}
      dragConstraints={{
        left: -100,
        right: 100,
        top: -100,
        bottom: 100,
      }}
    />
  )
}
```




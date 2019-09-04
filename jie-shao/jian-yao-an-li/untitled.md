# Scrolling 滚动

想要做一个滚动的页面，你需要把Frame标签包裹在Scroll组件里面，让它们能够自由滚动。但同时你需要注意，你要让包裹的Frame标签或者多个标签总和的高度或者宽度超过Scroll组件的宽度或者高度。滚动的方向默认是被设置成垂直方向vertical。整个组件内部分尺寸是根据Frame标签的尺寸自动计算的。

[Open Example](https://codesandbox.io/s/zqk53xj9k3)

```jsx
import * as React from "react"
import { Frame, Scroll } from "framer"

export function MyComponent() {
  return (
    <Scroll height={150}>
      <Frame height={70} />
      <Frame height={70} top={80} />
      <Frame height={70} top={160} />
    </Scroll>
  )
}
```


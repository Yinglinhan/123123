# Frame

Frame标签是一个最基础的容器，用于排版、样式、动画和事件。它本质上是一个div的标签加上一些额外的属性和好用的默认设定。这里你可以看到，要给Frame标签加上一些视觉上的设定是一件多么容易的事情，比如说加个background或者radius。额外，我们还增加了一个快捷的属性来方便地定义元素，比如说像size属性，就能同时设定width和height。

[Open Example](https://codesandbox.io/s/62km0298rk)

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  return (
    <Frame size={150} background={"#fff"} radius={30} />
  )
}
```


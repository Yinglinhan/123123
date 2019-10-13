# Stack

## Stack组件能帮你轻松创建弹性的、内容自动分布的布局。

Stack组件是基于Frame标签的，也就是说它支持所有Frame相关的属性。你可以把Stack组件当成一种Frame标签的弹性容器，如果你在Stack组件里面添加了一些Frame标签，它们会实现自动分布，同时你可以很轻松地控制distribution, gap 或者 padding的属性。可以同它来快速实现列表和一些自适应的布局。当有Frame标签添加进Stack组件时，会被设置为相对位置的布局。

 - 创建响应式的布局

 - 创建分类表单

 - 相对定位和内边距

```jsx
import * as React from "react"
import { Frame, Stack } from "framer"

export function MyComponent() {
  return (
    <Stack size={100}>
      <Frame background="#09F" size={25} radius="50%" />
      <Frame background="#05F" size={25} radius="50%" />
    </Stack>
  )
}
```


# Page

## Page组件能让你快速制作一个可以在水平或者垂直方向上进行滑动翻页的区域

Page组件是基于Frame的，这意味着所有Frame组件的属性在Page组件上支持。在一个Page组件里面放入多个Frame组件，就可以在多个页面中滑动翻页。Page组件的元素的尺寸默认是被拉伸撑满整个page组件的尺寸的，但是它们也能设置成auto，来让自己保持原本的尺寸的大小。

 - 创建水平或者垂直的全屏翻页组件

 - 创建局部的可翻页的组件

 - 使用自定义的变化效果 比如 3D和 Pile（堆叠）

```jsx
import * as React from "react"
import { Frame, Page } from "framer"

export function MyComponent() {
  return (
    <Page>
      <Frame>A</Frame>
      <Frame>B</Frame>
      <Frame>C</Frame>
    </Page>
  )
}
```


---
description: 最基本的容器，是用来布局，实现样式和动画以及事件的。
---

# Frame

Frame组件本质上是一个div标签，但是有一个额外的属性和默认的一些设置可以让你实现更高效的设置。Frame层面上的一些属性会给div这个标签设置一些默认的样式，但是你随时都可以通过自定义style属性来改变这些默认的样式。Frames允许你做下面这些事情：

 - 设置尺寸和添加布局限制

 - 水平对齐和垂直对齐

 - 修改背景颜色或者背景图片

 - 在几个状态之间实现动画

 - 给桌面版本和移动版本的页面添加点击事件

 - 添加一些高级的功能比如说拖拽

 - 实现更多手势操作的功能

> 如果你想要看老的v0.10的或者其他早一点的版本的文档 可以参看这个链接[ Frame API](https://www.framer.com/api/frame-deprecated/).

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  return (
    <Frame size={300} center>
      Hello
    </Frame>
  )
}
```



### Performance

为了能让你的原型有更好的动画性能表现，尽量只去通过animate属性使用transform和opacity使元素发生变化，因为它们有GPU加速。通过这样，你甚至可以在移动设备上同时驱动上百个图层同时发生变化。

```jsx
// GPU accelerated (fast)
<Frame initial={{scale: 1}} animate={{scale: 2}} />

// CPU drawing (slower)
<Frame initial={{size: 200}} animate={{size: 400}} />
```



### Integration


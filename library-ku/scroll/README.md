# Scroll

## 为桌面端或者移动创建一个可滚动的区域，支持鼠标和触摸操作。

Scroll组件是基于Frame的，因此它支持所有Frame的属性。它让我们可以快速创建一个可滚动的区域。当包含的Frame的尺寸在水平方向上或者垂直方向是超过包含它的Scroll组件的，那么就可以实现水平或者垂直方向上的滚动。

 - 创建水平或者垂直方向的可滚动区域

 -  创建包裹的滚动区域

 - 可用滚轮实现桌面端的滚动

 - 可以通过控制momentum和overdrag实现更高级的控制

Scroll组件并不是一个简单的带了overflow属性的div标签，它自定了很多基于真实物理效果的设置去模拟真实的类似于iOS系统的滚动效果。它可以在全平台通用，你可以通过各种方式控制它。它能让你探索更多新的、自定一的交互方式。

```jsx
import * as React from "react"
import { Frame, Scroll } from "framer"

export function MyComponent() {
  return (
    <Scroll height={200} width={200}>
      <Frame size={300}>Hello World!</Frame>
    </Scroll>
  )
}
```




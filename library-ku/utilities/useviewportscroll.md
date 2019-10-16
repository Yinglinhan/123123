# useViewportScroll

**useViewportScroll\(\):** ScrollMotionValues

这个方法返回一个MotionValue对象，这个对象每当页面进行scroll操作的时候内部的数据就会更新

 - scrollX —— 水平的滚动距离，单位是px

 - scrollY —— 垂直的滚动距离，单位是px

 - scrollXProgress —— 水平滚动的进度 范围是 0 - 1

 - scrollYProgress —— 垂直滚动的进度 范围是 0 - 1

 - 注意：如果当你srcoll的时候，MotionValue的数据没有实施更新，那么可以去检查一下body的标签的样式中是否把width height设置成100%或者是其他类似的设置，这样会导致无法精确测量滚动区域的尺寸。

```jsx
import * as React from "react"
import {
  Frame,
  useViewportScroll,
  useTransform
} from "framer"

export function MyComponent() {
  const { scrollYProgress } = useViewportScroll()
  return <Frame scaleX={scrollYProgress} />
}
```

| returns: ScrollMotionValues |
| :--- |



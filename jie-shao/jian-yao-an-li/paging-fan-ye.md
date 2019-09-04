# Paging 翻页

想要做翻页的效果，你可以把Frame标签放到Page组件中，这样他们就能翻页了。

翻页的效果是可以自定义配置的。翻动的方向默认是水平方向。整个内容区域的尺寸是自动计算出来的。

[Open Example](https://codesandbox.io/s/88j3049zr9)

```jsx
import * as React from "react"
import { Frame, Page } from "framer"

export function MyComponent() {
  return (
    <Page>
      <Frame />
      <Frame />
      <Frame />
    </Page>
  )
}
```


# Animation

### 一整套属性值可以帮助你实现高性能的动画效果

在Framer中动画主要是通过控制Frame组件来实现的。主要的两个属性分别是animate和transition，它们可以实现各种各样的自定义的动画效果。当你在文件中引入了Frame之后，所有的动画属性都已经包含在内，但是像useCycle这样的功能是要另外引入的。你可以在Frame版块中查看Frame中的动画属性和方法。

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  return (
    <Frame
      animate={{ rotate: 360 }}
      transition={{ duration: 2 }}
    />
  )
}
```




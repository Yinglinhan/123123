# Variants 变量组

Variants是一系列数据的集合，比如状态，你可以通过animate或者cycle让标签在多个状态之间切换。举个例子，比如一般来说按钮都会有一个鼠标悬浮停留时的状态和一个自己默认的状态。当有鼠标悬浮时，可能它的背景色background和投影boxshadow就会变了。这些属性就可以定义在Variants中。

通常，我们会把一些视觉变化的属性定义到Variants中。这这个案例中，Variants中的每个属性都是一组scale和rotate值。我们把它们分别命名为variantA和variantB。

最后，我们用标签上的variants属性来使用定义好的variants这个变量，把标签设置成当有鼠标悬浮时切换到variantB的状态。

[Open Example](https://codesandbox.io/s/98vm5qo84)

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  const variants = {
    variantA: { scale: 0.75, rotate: 0 },
    variantB: { scale: 1.0, rotate: 90 },
  }

  return (
    <Frame
      initial={"variantA"}
      whileHover={"variantB"}
      variants={variants}
    />
  )
}
```




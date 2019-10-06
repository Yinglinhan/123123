# Color

## Color这个函数能帮你进行定义、操作、混合、比较或者是转换颜色等一系列操作。

color方法能让你快速定义和修改定义的颜色的值。这里，我们定义了一个蓝色，动态地让它变得更亮，然后把它的值转换成另一种形式并且用到了一个Frame标签上。

为了能在标签上使用这个颜色，我们首先要把它转换成一个字符串的格式，它会返回一个hex格式的字符串的值\#3377FF。这些方式在你要用某些复杂的颜色体系时候会很有用，在一些你需要用hover状态时颜色有一些细节的变化的时候也很实用。

{% hint style="info" %}
Color函数不支持Share Colors

学习如何从画板模块中导入Shared colors可以点击[这里](../../framer-x/canvascomponents/colors.md)
{% endhint %}

```jsx
import * as React from "react"
import { Frame, Color } from "framer"

export function MyComponent() {
  const darkBlue = Color("#0055FF")
  const blue = Color.lighten(darkBlue, 10)

  return (
    <Frame
      background={Color.toHexString(blue)}
      size="100%"
    />
  )
}
```


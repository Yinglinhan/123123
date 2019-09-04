# Tranforms 变换

这里我们用到了Framer中的两个hook（钩子）将一个数值在一个区间范围内进行转化。

useMotionValue这个功能会返回一个可变的，我们把它赋值到x这个变量中，然后再放到Frame标签的x属性上。同时我们把x这个变量作为useTransform这个方法的第一个参数传进去，第二个参数是一个\[-200,200\]的数组，这个对应的是Frame标签被拖动的距离范围，而最后一个参数也是一个数组，是\[1.5,0.5\]，这是当x在-200到200的范围内，useTransform方法回返回值得范围，然后这个值被赋值到了scale变量中，所以当你拖动Frame标签时，这个scale变量值是在1.5-0.5的范围内变化的，而这个scale变量又被用在了Frame这个标签的scale属性上，所以当你拖动Frame标签时，它会在一定的范围内进行缩放变化。

[Open Example](https://codesandbox.io/s/l0061n7v7)

```jsx
import * as React from "react"
import { Frame, useMotionValue, useTransform } from "framer"

export function MyComponent() {
  const x = useMotionValue(0)
  const scale = useTransform(x, [-200, 200], [1.5, 0.5])

  return <Frame drag={"x"} x={x} scale={scale} />
}
```


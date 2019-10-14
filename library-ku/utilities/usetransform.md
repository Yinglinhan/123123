# useTransform



**useTransform**\(parent, transform\): MotionValue

把一个motionValue通过一个函数处理转换成另一个MotionValue。正在这个案例里，y永远会2倍于x。

```jsx
import * as React from "react"
import { Frame, useMotionValue, useTransform } from "framer"

export function MyComponent() {
  const x = useMotionValue(10)
  const y = useTransform(x, value => value * 2)

  return <Frame x={x} y={y} />
}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>parent: MotionValue</p>
        <p>&#x9700;&#x8981;&#x88AB;&#x8F6C;&#x6362;&#x7684;MotionValue&#x7C7B;&#x578B;&#x7684;&#x6570;&#x636E;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>transform: Transformer&lt;T&gt;</p>
        <p>&#x5C06;MotionValue&#x8FDB;&#x884C;&#x8F6C;&#x6362;&#x7684;&#x4E00;&#x4E2A;&#x51FD;&#x6570;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>returns: MotionValue</p>
        <p><code>MotionValue</code>
        </p>
      </td>
    </tr>
  </tbody>
</table>

**Transforming Ranges**

也可以利用这个useTramsform方法实现范围映射，在下面这个例子中，我们创建了一个可水平移动的Frame元素。

Frame这个元素的x初始状态时值是0，我们通过useTransform方法，当Frame移动范围是0-200的时候，会映射输出一个1-0.5范围的数字，同时这个数据被赋值到了Frame标签的scale属性上，这样Frame标签的缩放就和水平移动的距离产生联动了。

```jsx
import * as React from "react"
import { Frame, useMotionValue, useTransform } from "framer"

export function MyComponent() {
  const x = useMotionValue(0)
  const scale = useTransform(x, [0, 200], [1, 0.5])

  return <Frame drag={"x"} x={x} scale={scale} />
}
```


# Modify

Color**.alpha**\(color, a\): Color

设置颜色的透明度

```jsx
const blue = Color("#0099FF")

const transparent = Color.alpha(blue, 0.1)
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8BBE;&#x7F6E;&#x989C;&#x8272;&#x7684;&#x989C;&#x8272;&#x5B9E;&#x4F8B;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>a:</b> number</p>
        <p>0-1&#x7684;&#x4E00;&#x4E2A;&#x503C;&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;1</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>returns:</b> Color</td>
    </tr>
  </tbody>
</table>

Color.**brighten**\(color, amount\): Color

返回一个在传入颜色基础上更亮一些的颜色。

```jsx
const blue = Color("#0099FF")
const brightblue = Color.lighten(blue, 20)
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8FDB;&#x884C;&#x989C;&#x8272;&#x8C03;&#x6574;&#x7684;&#x989C;&#x8272;&#x5B9E;&#x4F8B;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>amount:</b> number</p>
        <p>0-100&#x7684;&#x6570;&#x503C;&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;10&#xFF0C;&#x8C03;&#x6574;&#x7684;&#x767E;&#x5206;&#x6BD4;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>returns:</b> Color</p>
        <p>&#x8FD4;&#x56DE;&#x7ECF;&#x8FC7;&#x8C03;&#x6574;&#x7684;&#x989C;&#x8272;&#x5B9E;&#x4F8B;</p>
      </td>
    </tr>
  </tbody>
</table>

Color.**darken**\(color, amount\): Color

把传入的颜色变暗

```jsx
const blue = Color("#0099FF")
const darkblue = Color.darken(blue, 20)
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8FDB;&#x884C;&#x989C;&#x8272;&#x8C03;&#x6574;&#x7684;&#x989C;&#x8272;&#x5B9E;&#x4F8B;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>amount:</b> number</p>
        <p>0-100&#x7684;&#x6570;&#x503C;&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;10&#xFF0C;&#x8C03;&#x6574;&#x7684;&#x767E;&#x5206;&#x6BD4;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>returns:</b> Color</p>
        <p>&#x8FD4;&#x56DE;&#x7ECF;&#x8FC7;&#x8C03;&#x6574;&#x7684;&#x989C;&#x8272;&#x5B9E;&#x4F8B;</p>
      </td>
    </tr>
  </tbody>
</table>

Color.**desaturate**\(color, amount\): Color

降低传入颜色的饱和度

```jsx
const blue = Color("#0099FF")
const desaturated = Color.desaturate(blue, 100)
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8FDB;&#x884C;&#x989C;&#x8272;&#x8C03;&#x6574;&#x7684;&#x989C;&#x8272;&#x5B9E;&#x4F8B;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>amount:</b> number</p>
        <p>0-100&#x7684;&#x6570;&#x503C;&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;10&#xFF0C;&#x8C03;&#x6574;&#x7684;&#x767E;&#x5206;&#x6BD4;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>returns:</b> Color</p>
        <p>&#x8FD4;&#x56DE;&#x7ECF;&#x8FC7;&#x8C03;&#x6574;&#x7684;&#x989C;&#x8272;&#x5B9E;&#x4F8B;</p>
      </td>
    </tr>
  </tbody>
</table>

Color.**difference**\(colorA, colorB\): number

用[Euclidean distance fitting human perception](https://en.wikipedia.org/wiki/Color_difference#Euclidean) 方式去计算两个颜色之间的差异，返回一个0-765之间的数值。

| colorA: Color |
| :--- |
| **colorB:** Color |
| **returns:** number |














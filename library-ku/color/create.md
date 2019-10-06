# Create

**Color\(color, r, g, b\):** Color

Color函数可以用来定义颜色，你既可以直接传颜色的字符串形式的值，也可以传进去一个对象。所有颜色都会被转换成一个颜色对象，r、g、b或者h、s、l及a的格式。有多种颜色格式的参数都可以实现创建一个颜色的对象。

```jsx
// HEX
const blue = Color("#0099FF")

// RGB
const blue = Color("rgb(0, 153, 255)")
const blue = Color(0, 153, 255)
const blue = Color({r: 0, g: 153, b: 255})
const blue = Color({r: 0, g: 153, b: 255, a: 1})

// HSL
const blue = Color("hsl(204, 100%, 50%)")
const blue = Color({h: 204, s: 1, l: 0.5})
const blue = Color({h: 204, s: 1, l: 0.5, a: 1})
```

| **color:** IncomingColor \| Color \| number |
| :--- |
| **r:** number |
| **g:** number |
| **b:** number |
| **returns:** Color |



Color.random\(alphaValue\): Color

返回一个颜色对象的实例同时设置了随机的透明度

```jsx
const random = Color.random()
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>alphaValue: number</p>
        <p>&#x53EF;&#x9009;&#x7684;&#x900F;&#x660E;&#x5EA6;&#x503C;&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;1</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>returns:</b> Color&#x5B9E;&#x4F8B;</td>
    </tr>
  </tbody>
</table>
































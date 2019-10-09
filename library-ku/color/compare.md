# Compare

Color**.inspect**\(color, initialValue\): string

把一个颜色对象转换成可读的字符串形式，一般用来debug

```jsx
const blue = Color("#0099FF")

Color.inspect(blue)
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>The Color object to format</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>initialValue: </b>string</p>
        <p>&#x8FD9;&#x662F;&#x4E00;&#x4E2A;&#x53EF;&#x9009;&#x53C2;&#x6570;&#xFF0C;A
          canonical hex string to be used instead of an rgba() value.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>returns:</b> string</td>
    </tr>
  </tbody>
</table>

Color.**isColor\(color\)**: boolean

验证传进来的参数是不是合法的颜色值

```jsx
Color.isColor("#0099FF") // true
Color.isColor(Color("#0099FF")) // true
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: string | Color</p>
        <p>&#x8981;&#x8FDB;&#x884C;&#x9A8C;&#x8BC1;&#x7684;&#x503C;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>returns:</b> boolean</td>
    </tr>
  </tbody>
</table>

Color**.isColorObject**\(color\):color is object & Color

验证传进来的参数是否为一个color对象，返回true或false

```jsx
const blue = Color("#0099FF")

Color.isColorObject(blue) // true
Color.isColorObject("#0099FF") // false
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: any</p>
        <p>&#x4E00;&#x4E2A;&#x989C;&#x8272;&#x5BF9;&#x8C61;&#x6216;&#x8005;&#x5176;&#x4ED6;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">returns: color is object &amp; Color</td>
    </tr>
  </tbody>
</table>

Color.**isColorString**\(colorString\): boolean

检查传进来的值是否为一个合法的颜色值的字符串，返回true或者false

```jsx
Color.isColorString("#0099FF") // true
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>colorString: string | object</p>
        <p>A string representing a color</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">returns: boolean</td>
    </tr>
  </tbody>
</table>










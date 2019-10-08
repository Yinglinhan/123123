# Convert

Color.**toHex**\(color, allow3Char\): string

把颜色对象的颜色值的格式转成16进制的格式.，注意这个方法返回的值**不带\#号**

```jsx
const blue = Color("#0099FF")

Color.toHex(blue) // "0099FF"
Color.toHex(Color("#FFAAFF"), true) // "FAF"
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8FDB;&#x884C;&#x989C;&#x8272;&#x8F6C;&#x6362;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>allow3Char:</b> boolean</p>
        <p>&#x5982;&#x679C;&#x53EF;&#x4EE5;&#xFF0C;&#x4F1A;&#x8FD4;&#x56DE;&#x4E00;&#x4E2A;3&#x4F4D;&#x7684;hex&#x683C;&#x5F0F;&#x7684;&#x989C;&#x8272;&#x503C;&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;false</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>returns:</b> string</td>
    </tr>
  </tbody>
</table>

Color.**toHexString**\(color, allow3Char\): string

把颜色对象的颜色值的格式转成16进制的格式，注意这个方法返回的值**带\#号**

```jsx
const blue = Color("#0099FF")

Color.toHexString(blue) // "#0099FF"
Color.toHexString(Color("#FFAAFF"), true) // "#FAF"
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8FDB;&#x884C;&#x989C;&#x8272;&#x8F6C;&#x6362;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>allow3Char:</b> boolean</p>
        <p>&#x5982;&#x679C;&#x53EF;&#x4EE5;&#xFF0C;&#x4F1A;&#x8FD4;&#x56DE;&#x4E00;&#x4E2A;3&#x4F4D;&#x7684;hex&#x683C;&#x5F0F;&#x7684;&#x989C;&#x8272;&#x503C;&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;false</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>returns:</b> string</td>
    </tr>
  </tbody>
</table>

Color.**toHsl**\(color\): ColorHSLA

格式化一个颜色的，返回一个HSL格式的对象

```jsx
const blue = Color("#0099FF")

Color.toHsl(blue) // {h: 204, s: 1, l: 0.5, a: 1}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x683C;&#x5F0F;&#x5316;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>returns:</b> ColorHSLA</td>
    </tr>
  </tbody>
</table>

Color.**toHslString**\(color\): string

格式化一个颜色，把它转变成hsl格式的字符串形式

```jsx
const blue = Color("#0099FF")

Color.toHslString(blue) // "hsl(204, 100%, 50%)"
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x683C;&#x5F0F;&#x5316;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>returns:</b> string</td>
    </tr>
  </tbody>
</table>

Color.**toHsv**\(color\): ColorHSVA

格式化一个颜色，把它转变成HSV格式的颜色对象

```jsx
const blue = Color("#0099FF")

Color.toHsv(blue) // {h: 204, s: 1, v: 1, a: 1}"
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x8981;&#x8FDB;&#x884C;&#x8F6C;&#x6362;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>returns:</b> ColorHSVA</td>
    </tr>
  </tbody>
</table>

Color.**toHsvString**\(color\): string

格式化一个颜色实例，把它转换成HSV颜色格式的字符串

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x683C;&#x5F0F;&#x8F6C;&#x6362;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>returns:</b> string</td>
    </tr>
  </tbody>
</table>

Color.**toHusl**\(color\): ColorHSLA

把一个颜色实例转换成HUSL格式的对象

```jsx
const blue = Color("#0099FF")

Color.toHusl(blue) // {h: 250, s: 100, l: 50, a: 1}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8FDB;&#x884C;&#x683C;&#x5F0F;&#x8F6C;&#x6362;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>returns:</b> ColorHSLA</td>
    </tr>
  </tbody>
</table>

Color.**toName**\(color\): string \| false

把一个颜色实例的值转换成横css中的颜色名称，如果当前颜色值没有对应可转换的，那就返回false

```jsx
const green = Color("#8FBC8F")

Color.toName(green) // "darkseagreen"
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x88AB;&#x8F6C;&#x6362;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>returns:</b> string | false</td>
    </tr>
  </tbody>
</table>



Color.**toRgb**\(color\): ColorRGBA

把颜色实例转换成一个RGB的对象

```jsx
const blue = Color("#0099FF")

Color.toRgb(blue) // {r: 40, g: 175, b: 250, a: 1}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8F6C;&#x6362;&#x7684;&#x989C;&#x8272;&#x5B9E;&#x4F8B;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>returns:</b> ColorRGBA</td>
    </tr>
  </tbody>
</table>

Color.toRgbString\(color\): string

把颜色实例转换成RGB的格式的字符串形式

```jsx
const blue = Color("#0099FF")

Color.toRgbString(blue) // "rgb(0, 153, 255)"
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8F6C;&#x6362;&#x7684;&#x989C;&#x8272;&#x5B9E;&#x4F8B;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>returns:</b> string</td>
    </tr>
  </tbody>
</table>

Color.**toString**\(color\): string

把颜色实例转换成RGB的格式的字符串形式

```jsx
const blue = Color("#0099FF")

Color.toString(blue) // "rgb(0, 153, 255)"
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8F6C;&#x6362;&#x7684;&#x989C;&#x8272;&#x5B9E;&#x4F8B;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>returns:</b> string</td>
    </tr>
  </tbody>
</table>


















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



Color.**grayscale**\(color\): Color

返回一个完全无饱和度的颜色

```jsx
const blue = Color("#0099FF")
const gray = Color.grayscale(blue)
```

| color: Color |
| :--- |
| **returns:** number |



Color.**hueRotate**\(color, angle\): Color

返回一个调整了色相角度的颜色

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8C03;&#x6574;&#x8272;&#x76F8;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>angle:</b> number</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x8272;&#x76F8;&#x8C03;&#x6574;&#x7684;&#x89D2;&#x5EA6;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>returns:</b> number</td>
    </tr>
  </tbody>
</table>

Color.**interpolate**\(colorA, colorB, model\)

返回一个函数，可以实现输出的颜色在两种颜色之间混合及切换，默认使用的RGB的颜色模式对象，在实现某些颜色变化时非常有效。

```jsx
const blend = Color.interpolate(Color("red"), Color("blue"))

blend(0)   // Initial state (red)
blend(0.5) // Mid state (purple)
blend(1)   /
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>colorA: Color</p>
        <p>&#x5F00;&#x59CB;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>colorB:</b> Color</p>
        <p>&#x7ED3;&#x675F;&#x989C;&#x8272;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>model: ColorMixModelType</p>
        <p>&#x989C;&#x8272;&#x6A21;&#x5F0F;&#x5BF9;&#x8C61;&#xFF0C;ColorMixModelType&#x4E2D;&#x7684;&#x5176;&#x4E2D;&#x4E00;&#x79CD;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>returns:</b> (progress:number) =&gt; Color</td>
    </tr>
  </tbody>
</table>

Color.**lighten**\(color, amount\): Color

给颜色添加白色返回一个更亮的颜色

```jsx
const blue = Color("#0099FF")
const lightblue = Color.lighten(blue, 20)
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x8981;&#x8FDB;&#x884C;&#x5904;&#x7406;&#x7684;&#x989C;&#x8272;&#x5BF9;&#x8C61;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>amount: </b>number</p>
        <p>&#x8C03;&#x6574;&#x6570;&#x503C;&#xFF0C;&#x4ECE;0-100&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;10</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>returns:</b> Color</td>
    </tr>
  </tbody>
</table>

Color.**mix**\(from, toColor, { model }\): \(p:number\) =&gt; string

返回一个函数可以混合两个颜色，然后输出一个字符串类型的RGB颜色格式的值

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p><b>from:</b> Color</p>
        <p>&#x5F00;&#x59CB;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>toColor:</b> Color</p>
        <p>&#x7ED3;&#x675F;&#x7684;&#x989C;&#x8272;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>{ model }: </b>{ model?: ColorMixModelType | undefined; }</p>
        <p>&#x53EF;&#x9009;&#x7684;&#x989C;&#x8272;&#x6A21;&#x5F0F;&#x5BF9;&#x8C61;&#x53C2;&#x6570;</p>
        <p><b><code>model</code></b>: &#x989C;&#x8272;&#x6A21;&#x5F0F;&#x5BF9;&#x8C61;&#x7684;&#x5176;&#x4E2D;&#x4E00;&#x79CD;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>returns:</b> (p: number) =&gt; string</td>
    </tr>
  </tbody>
</table>

Color.**multiplyAlpha**\(color, alphaValue\): Color

改变颜色的透明度，把原透明度乘以传入alphaValue

```jsx
const blue = Color("#0099FF")
const transparent = Color.multiplyAlpha(blue, 0.5)
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x9700;&#x8981;&#x8FDB;&#x884C;&#x8C03;&#x6574;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>alphaValue:</b> number</p>
        <p>&#x4E00;&#x4E2A;0-1&#x8303;&#x56F4;&#x5185;&#x7684;&#x6570;&#x5B57;&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;1</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>returns:</b> Color</td>
    </tr>
  </tbody>
</table>

Color.**saturate**\(color, amount\): Color

增加一个颜色的饱和度

```jsx
const blue = Color("#0099FF")
const saturated = Color.saturate(blue, 100)
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x8981;&#x8FDB;&#x884C;&#x8C03;&#x6574;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>amount:</b> number</p>
        <p>0-100&#x8303;&#x56F4;&#x5185;&#x7684;&#x6570;&#x5B57;&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;10</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>returns:</b> Color</td>
    </tr>
  </tbody>
</table>

Color.**transparent**\(color\): Color

把颜色的opacity的值设为0

```jsx
const blue = Color("#0099FF")

const transparent = Color.alpha(blue)
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>color: Color</p>
        <p>&#x8981;&#x88AB;&#x8C03;&#x6574;&#x7684;&#x989C;&#x8272;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">returns: Color</td>
    </tr>
  </tbody>
</table>






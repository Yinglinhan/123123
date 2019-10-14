# Transfrom

**transform\(**inputValue, inputRange, outputRange, options**\): T**

这个方法能把传入的inputValue转换成inputRange和outputRange映射后的在outputRange范围内的映射值。返回一个数据的类型决定于你传入数据的类型。

当你传入的inputRange是一个\[0,200\]的数组，同时你传入的outputRange是\[0,1\]，那么这个函数返回的是就是0到1范围内的一个数，当然，前提是你传入的数据是在0-200范围内的。你传入的值必须是这个连续范围内一个数。outputValue范围类型支持数字、颜色、投影、数组和对象以及更多。每一个返回的值的类型都和输入的inputValue值保持一致。

```jsx
import * as React from "react"
import { Frame, transform } from "framer"

export function MyComponent() {
   const inputRange = [0, 200]
   const outputRange = [0, 1]
   const output = transform(100, inputRange, outputRange)

   // Returns 0.5
   return <Frame>{output}</Frame>
}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>inputValue: number</p>
        <p>&#x4E00;&#x4E2A;&#x9700;&#x8981;&#x88AB;&#x8F6C;&#x6362;&#x7684;&#x6570;&#x636E;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>inputRange: number[]</p>
        <p>inputValue&#x7684;&#x503C;&#x7684;&#x8303;&#x56F4;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>outputRange: T[]</p>
        <p>&#x652F;&#x6301;&#x591A;&#x79CD;&#x6570;&#x636E;&#x7C7B;&#x578B;&#xFF0C;&#x6BD4;&#x5982;numbers,
          colors, shadows, arrays&#x548C;objects</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>options: TransformOptions&lt;T&gt;</p>
        <p>Clamp: &#x662F;&#x5426;&#x73B0;&#x5728;&#x6570;&#x636E;&#x5728;&#x7ED9;&#x5B9A;&#x7684;&#x8303;&#x56F4;&#x5185;&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;true</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">returns: T</td>
    </tr>
  </tbody>
</table>

**Ranges**

transform方法同样也支持传入的范围数组包含的数据超过2个。比如说下面这个例子，当inputValue是\[ -200, -100, 100, 200 \]，outputValue 范围是\[ 0, 1, 1, 0 \]，那么这个函数会返回：

 - 当inputValue的值在 -200 到 -100之间，那么返回一个值是0到1范围的

 - 当inputValue的值在-100 到 100之间，那么返回的值都是1

 - 当inputValue的值在100 到 200之间，那么返回的值是1到0的范围

```jsx
import * as React from "react"
import { Frame, transform } from "framer"

export function MyComponent() {
  const inputRange = [-200, -100, 100, 200]
  const outputRange = [0, 1, 1, 0]
  const output = transform(150, inputRange, outputRange)
  // output equals 0.5
  return <Frame>{output}</Frame>
}
```

\*\*\*\*

**transform\(**inputRange, outputRange, options**\): \(inputValue: number\) =&gt; T**

为了提高运行效果，可以先将inputRange和outputRange传入到transform函数中，这将回返回一个函数。然后再将要转换的数据，在需要转换时传进去。

```jsx
import * as React from "react"
import { Frame, transform } from "framer"

export function MyComponent() {
    const inputRange = [-200, -100, 100, 200]
    const outputRange = [0, 1, 1, 0]
    const convertRange = transform(inputRange, outputRange)
    const output = convertRange(-150)

    // Returns 0.5
    return <Frame>{output}</Frame>
}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>inputRange: number[]</p>
        <p>&#x8FDE;&#x7EED;&#x7684;&#x6570;&#x636E;&#x503C;&#x8303;&#x56F4;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>outputRange: T[]</p>
        <p>&#x652F;&#x6301;&#x591A;&#x79CD;&#x6570;&#x636E;&#x7C7B;&#x578B;&#xFF0C;&#x6BD4;&#x5982;numbers,
          colors, shadows, arrays&#x548C;objects</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>options: TransformOptions&lt;T&gt;</p>
        <p>Clamp: &#x662F;&#x5426;&#x73B0;&#x5728;&#x6570;&#x636E;&#x5728;&#x7ED9;&#x5B9A;&#x7684;&#x8303;&#x56F4;&#x5185;&#xFF0C;&#x9ED8;&#x8BA4;&#x662F;true</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">returns: (inputValue: number) =&gt; T</td>
    </tr>
  </tbody>
</table>\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*


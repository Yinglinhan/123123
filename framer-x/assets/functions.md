# Functions

**url\(**path:string**\)**: string

依据传入的地址生成一个URL地址，不管组件在何处被使用，这个地址都能正确获取到相对应的资源

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>path: string</p>
        <p>&#x5F53;&#x524D;&#x4F60;&#x8981;&#x5F15;&#x7528;&#x7684;&#x6587;&#x4EF6;&#x76F8;&#x5BF9;&#x4E8E;&#x4F60;&#x8FD9;&#x4E2A;&#x9879;&#x76EE;&#x6839;&#x76EE;&#x5F55;&#x7684;&#x8DEF;&#x5F84;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>returns: string</p>
        <p>&#x4E00;&#x4E2A;&#x80FD;&#x591F;&#x5F15;&#x7528;&#x5230;&#x6587;&#x4EF6;&#x7684;&#x7EDD;&#x5BF9;&#x8DEF;&#x5F84;</p>
      </td>
    </tr>
  </tbody>
</table>```jsx
import * as React from "react"
import { Frame } from "framer"
import { url } from "framer/resource"

export function MyComponent() {
  return (
    <Frame image={url("./code/test.png")} size={"100%"} />
  )
}
```

生成的URL地址会根据你的项目在何处在合适打开来生成正确的地址，所有在组件上使用url这个方法，而不要先用一个变量来存放url方法的返回值。

```jsx
// GOOD: Use a relative path. Call url() within component. 这样是对的使用方式
const image = "./code/test.png"

export function MyComponent() {
  return <Frame image={url(image)} size={"100%"} />
}
```

```jsx
// BAD: Avoid this. The returned url may change over time.  这是错的使用方式
const image = url("./code/test.png")

export function MyComponent() {
  return <Frame image={image} size={"100%"} />
}
```




# Data & Overrides

## 通过Override可以用组件之间共享data

Data对象就像是我们平时常用的一般的JavaScript对象，你可以在里面存放任何数据。当数据有变化时就会刷新页面和相关的组件，它能实现组件之间的数据共享。在这里这个案例中，我们简单地来通过override和data改变一下text标签的text文字内容。

```jsx
import { Override, Data } from "framer"

const data = Data({ name: "Ben" })

export function setName(): Override {
  return {
    text: data.name,
  }
}
//override 相当于就是覆写你要操作的组件 设置它的属性为你返回对象中的对应设置
```



**Incrementing Values 增加数值**

你可以利用Data对象去实现一些递增的数值的设置。比如说这个案例中，我们一开始给Data对象里面传的值是rotate: 0，我们把组件的animate属性设置为data中的rotate值，然后通过onTap绑定一个函数，这个函数每次点击都会让data中的rotate数值增加90。

```jsx
import { Data, Override } from "framer"

const data = Data({ rotate: 0 })

export function Rotate(): Override {
  return {
    animate: { rotate: data.rotate },
    onTap() {
      data.rotate = data.rotate + 90
    },
  }
}
```

\*\*\*\*

**Data\(**initial**\): T**

Data的数据可以在多个组件上使用。所有使用了data数据的组件在data数据改变后都会触发组件的刷新或者重新渲染。在下面这个案例中，我们设置了当我们按住组件时，组件的scale属性会使用data中的数据，即为0.5。

```jsx
import { Data, Override } from "framer"

const data = Data({
   scale: 0.5,
})

export function WhileTap(): Override {
   return {
       whileTap: {
           scale: data.scale,
       },
   }
}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>initial: Partial&lt;T&gt; | object</p>
        <p>&#x653E;&#x5165;data&#x4E2D;&#x7684;&#x521D;&#x59CB;&#x6570;&#x636E;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>returns: T</p>
        <p>&#x8FD4;&#x56DE;&#x7684;&#x5BF9;&#x8C61;&#xFF0C;&#x5305;&#x542B;&#x4E86;&#x8BBE;&#x7F6E;&#x7684;&#x6570;&#x636E;</p>
      </td>
    </tr>
  </tbody>
</table>\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*

\*\*\*\*


# Gestures

让我们实现一个当我们点击一个Frame标签让它产生变化的一个效果，我们首先要创建两个变量，一个是初始的rotate，它的初始值为0，一个是用来设置这个rotate变量的setRotate方法。

然后，创建一个函数toggleRotate，每次执行这个函数的时候，rotate变量里面的值就增加90。最后，我们把这个rotate变量传递到aimate这个属性里面，还要把toggleRotate这个函数绑定到onTap这个事件上。

[Open Example](https://codesandbox.io/s/jlq97yryk9)

```jsx
import * as React from "react"
import { useState } from "react"
import { Frame } from "framer"

export function MyComponent() {
  const [rotate, setRotate] = useState(0)
  const toggleRotate = () => setRotate(rotate + 90)

  return <Frame animate={{ rotate }} onTap={toggleRotate} />
}
```



### On Hover  鼠标悬停触发动画效果

现在，让我们实现一个当我们鼠标在Frame标签上会触发缩放的效果。我们可以使用whileHover属性来实现，给它传递一个scale属性及相应想要变化到的缩放比例的值。

[Open Example](https://codesandbox.io/s/8zoqqj2x2j)

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  return <Frame whileHover={{ scale: 0.75 }} />
}
```




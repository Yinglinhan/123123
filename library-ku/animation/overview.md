# Overview

### Frame

绝大部分的动画效果都能通过Frame组件进行控制，你可以自己设置动画的各种参数以及监听动画的变化。和动画相关的一些属性都在下方列了出来。

 - animate

 - transition

 - variants

 - initial 

 - onUpdate

 - onAnimationStart

 - onAnimationComplete

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  function onUpdate({ rotate }) {
    console.log(rotate)
  }

  return (
    <Frame
      initial={{ rotate: 0 }}
      animate={{ rotate: 360 }}
      transition={{ duration: 2 }}
      onUpdate={onUpdate}
    />
  )
}
```



**Animate**

animate属性可以控制动画，当在animate属性中的值发生变化时，Frame标签就会产生动画，使其过渡到新的状态。

```jsx
<Frame animate={{ opacity: 0 }} />
```



**Transition**

通过animate实现的动画效果的过渡效果的设置是通过这个transition属性来设置的。

Transition 有三种类型

 - **Tween** 可设定某种运动曲线并且给定一个过渡时间

 - **Spring** 基于mass，damping和stiffness这三个参数的弹性效果

 - **Inertia** spring和friction两个参数组合使用，用于元素发生位移的动画

```jsx
<Frame
  animate={{ opacity: 0 }}
  transition={{ duration: 1 }}
/>
```



**Initial**

这个属性主要是用来设置元素的初始状态，把相关的值赋值给这个属性就是给元素设定一个初始的

```jsx
<Frame initial={{ scale: 0 }} animate={{ scale: 1 }} />
```



**Variants**

Variants这是一个实现多个视觉状态的管理属性，你可以定义一个对象，然后把不同的视觉状态的设置用不同的属性来分别定义好，然后赋值给variants这个属性。传递给variants这个属性的对象中的属性名字，可以用在animate、initial、press以及hover等属性上。

 - 初始的状态被定义成variants中的hidden

 - hidden这个状态中有自己的transition设置

 - Frame元素会从hidden这个状态过渡到visible这个状态

 - 整个在组件中定义的variants对象被传入了Frame标签中的variants属性

```jsx
export function MyComponent() {
  const variants = {
    hidden: {
      opacity: 0,
      transition: { duration: 0.5 },
    },
    visible: { opacity: 1 },
  }

  return (
    <Frame
      initial="hidden"
      animate="visible"
      variants={variants}
    />
  )
}
```



**Animating Children**




























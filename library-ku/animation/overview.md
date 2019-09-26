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

作为某个元素的子元素的Frame标签，当它也被传入和父级元素一样属性名字的动画效果状态对象时，如果父级元素上设置了相关属性来通过variants实现动画，子元素也被驱动，哪怕这些元素不是直接的子元素。当前这个例子中，你不用再使用animate属性来使你的元素发生变化，如果你用了，那么父级元素上的variant的驱动就不会影响到子元素，它会使用自己的animate来驱动动画。

```jsx
export function MyComponent() {
  // Parent variants
  const list = {
    hidden: { opacity: 0, x: -100 },
    visible: { opacity: 1, x: 0 },
  }

  // Child variants
  const item = {
    hidden: { opacity: 0, scale: 0.5 },
    visible: { opacity: 1, scale: 1 },
  }

  return (
    <Frame
      variants={list}
      initial="hidden"
      animate="visible"
    >
      <Frame variants={item} />
      <Frame variants={item} />
      <Frame variants={item} />
    </Frame>
  )
}
```



**Parent & Child Orchestration**

可以通过父元素的variants属性来实现子元素的分步动画效果，可以在variants的对象中transition中设定相关的属性

**查看分步动效效果的参数**

```jsx
const list = {
  hidden: {
    opacity: 0,
    x: -100,
    transition: { when: "afterChildren" },
  },
  visible: {
    opacity: 1,
    x: 0,
    transition: { when: "beforeChildren" },
  },
}
```



**Dynamic Variants**

Variants能通过函数的方式实现动态生成variant的数据，这样就能动态实现每一个组件按照自己特定的参数值实现特定的动画效果。

这个例子中，我们创建了一个分步动画，使用了custom属性来给每一个组件都传递了不一样的参数，而在variant中定义了一个custom参数的函数。所有的Frame标签都会共享这同一个variants对象，他们都会实现向hidden状态的过渡动画，只是他们的delay不一样。

```jsx
export function MyComponent() {
  const variants = {
    hidden: custom => ({
      opacity: 0,
      transition: { delay: custom * 0.5 },
    }),
  }
  return (
    <Stack>
      <Frame
        custom={0}
        variants={variants}
        animate={"hidden"}
      />
      <Frame
        custom={1}
        variants={variants}
        animate={"hidden"}
      />
      <Frame
        custom={2}
        variants={variants}
        animate={"hidden"}
      />
    </Stack>
  )
}
```
















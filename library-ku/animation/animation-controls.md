# Animation controls

在Frame标签上已经定义好的那些动画效果用来做交互动效是非常理想的，但是有时候我们总会有一些更复杂的需求，做一些更复杂的动画效果。

用useAnimation这个方法，可以创建一个对象，这个对象上有两个方法分别可以是start和stop，用来开始和结束动画。这个对象可以传递给任何一个Frame组件的animate属性，通过这样来控制对应的Frame组件的动画。

```jsx
import { Frame, useAnimation } from "framer"

function MyComponent() {
  const controls = useAnimation()

  return <Frame animate={controls} />
}
```



#### Starting an animation

动画通过controls.start方法来启动，传入一个动画的参数对象

```jsx
controls.start({
  x: "100%",
  backgroundColor: "#f00",
  transition: { duration: 3 },
})
```

参数除了可以是动画的参数对象，还可以是一个被传入这个组件variants属性的对象的一个属性名称。

```jsx
controls.start("hidden")
```



#### Sequencing

start方法返回的是一个Promise对象，所以它可以和async、await一起用来实现分步动画。

不同的通过useAnimation产生的控制动画的对象可以组合在一起使用，在一个函数中用async、await进行组织，就可以实现分步动画

```jsx
async function sequence() {
  await menuControls.start({ x: 0 })
  return await itemControls.start({ opacity: 1 })
}
```



#### Dynamic start

start方法的参数也可以是一个函数，这样可以实现让多个组件使用同一个controls但是同时又有一些不同的效果，因为可以给每一个组件自身传递不同的用于start中传入的函数的参数值。

给start方法传递的参数的具体值可以通过每一个组件的custom属性来实现。

```jsx
const controls = useAnimation()

useEffect(() => {
  controls.start(i => ({
    opacity: 0,
    x: 100,
    transition: { delay: i * 0.3 },
  }))
}, [])

return (
  <>
    <Frame custom={0} animate={controls} />
    <Frame custom={1} animate={controls} />
    <Frame custom={2} animate={controls} />
  </>
)
```



#### Supported Value Types 支持的值的类型

 - Numbers 数字

 - Strings 字符串

 - All Unit Types\(px , %, calc\( \), etc\) 各种单位

 - Colors \( hex , rgba ,hsla\) 颜色模式

 - Complex Values\( String with numbers and colors \) 复合值

当使用复合值进行设置的时候，比如说boxShadow这个属性，每一个位置的非数字类型的数值都要准确的写，比如说，"5px 10px \#333"能够过渡到"0px 0px \#333"，但是没办法过渡到"0 0 \#333"。

```jsx
export function MyComponent() {
  const animate = {
    x: 0,
    y: "100%",
    display: "block",
    color: "rgba(0, 0, 0, 0.5)",
    boxShadow: "5px 10px #333",
  }

  return <Frame animate={animate} />
}
```



#### Transforms

transform的相关属性可以单独使用

 - x, y, z

 - rotate, rotateX, rotateY, rotateZ

 - scale, scaleX, scaleY, scaleZ

 - skewX, slewY

 - originX, originY

 - perspective

```jsx
<Frame animate={{ rotate: 90, scaleX: 1.2 }} />
```



#### Value Conversion

x, y, width, height, top, left, bottom 和 right这些属性的值可以用不同的类型

```jsx
const variants = {
  closed: { x: 0 },
  open: { x: "calc(50vw - 50%)" },
}
```














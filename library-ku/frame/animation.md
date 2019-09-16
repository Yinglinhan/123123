# Animation 动画

接下来的这些属性是用来帮助Frame组件高效实现一些动画效果的，当用来设置动画的属性被组合在一起传进去的时候，动画的设置就会变得十分灵活和高效。



**initial:** boolean \| Target \| VariantLabels

可以将动画的参数对象，variants对象中定义的属性名字或者属性名字的数组传进去。

也可以设置成false，这样就能让animate属性在组件刚加载的时候不起作用。

```jsx
// As values
<Frame initial={{ opacity: 1 }} />

// As variant
<Frame initial="visible" variants={variants} />

// Multiple variants
<Frame initial={["visible", "active"]} variants={variants} />

// As false (disable mount animation)
<Frame initial={false} animate={{ opacity: 0 }} />
```



**animate**: AnimationControls \| TargetAndTransition \| VariantLabels

同样可以传variants对象中定义的属性，或者是动画属性的对象，还有就是可以传动画控制对象（通过useAnimation方法返回的对象）

```jsx
// As values
<Frame animate={{ opacity: 1 }} />

// As variant
<Frame animate="visible" variants={variants} />

// Multiple variants
<Frame animate={["visible", "active"]} variants={variants} />

// AnimationControls
<Frame animate={animation} />
```



**exit**: AnimationControls \| TargetAndTransition \| VariantLabels

如果使用这个属性，当组件被移除的时候会触发相应的动画效果。

这个要产生动画效果必须要用一个AnimatePresence标签（要在文档开头引入）包裹，并且是作为第一个子标签。

之所以会有这么一个设定，是因为React本身不允许组件等到动画完成后再被移除，如果这个React本身的问题解决了，那么AnimatePresence这个标签也就不需要了。

```jsx
import { Frame, AnimatePresence } from 'framer'

export function MyComponent(props) {
  return (
    <AnimatePresence>
       {props.isVisible && (
         <Frame
           initial={{ opacity: 0 }}
           animate={{ opacity: 1 }}
           exit={{ opacity: 0 }}
         />
       )}
    </AnimatePresence>
  )
}
```

\*\*\*\*

**transition:** Transition

默认的transition定义。如果在animate属性中没有定义transition，那么它就会使用这里的transition的设定。

```jsx
const spring = {
  type: "spring",
  damping: 10,
  stiffness: 100
}

<Frame transition={spring} animate={{ scale: 1.2 }} />
```



**positionTransition:** Transition \| boolean \| ResolveLayoutTransition

当一个Frame标签是Stack标签的子元素时，Stack标签决定了它的子元素的布局，这让我们很难去知道一个Frame标签的位置在什么时候会发生变化以及如何变化。

给Frame标签添加一个positionTransition属性，当他发生位置变化时都会自动产生动画效果，不管是Stack标签本身的布局或者内部Frame标签的顺序发生了改变。

当然，它也能直接赋值一个你自己定义的过渡效果的对象，也可以设置成true，当设置成true就会使用默认的布局变化动画效果。

```jsx
function MyComponent({ distribution = "space-around" }) {
  const spring = {
    type: "spring",
    damping: 10,
    stiffness: 100
  }

  return (
    <Stack distribution={distribution}>
      <Frame positionTransition={spring} />
    </Stack>
  )
}
```



**onUpdate**\(latest\): **void**

获取动画过程中最新的动画属性并传入定义好的回调函数中，每运动一帧触发一次相应的回调函数

```jsx
function onUpdate(latest) {
  console.log(latest.x, latest.opacity)
}

<Frame animate={{ x: 100, opacity: 0 }} onUpdate={onUpdate} />
```

| 动画对象的类型和约束 |
| :--- |
| latest: { \[key: string\]: string \| number; } |



**onAnimationStart\(\):void**

当动画开始时触发相关回调函数

```jsx
function onStart() {
  console.log("Animation completed")
}

<Frame animate={{ x: 100 }} onAnimationStart={onStart} />
```



**onAnimationComplete\(\):void**

当动画结束时触发相关的回调函数

```jsx
function onComplete() {
  console.log("Animation completed")
}

<Frame animate={{ x: 100 }} onAnimationComplete={onComplete} />
```














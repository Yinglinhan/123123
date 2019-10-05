# Types

## MotionValue

**MotionValue**是来追踪运动数值的状态和速度的。

这个类的构造函数是内置的。第三方代码不应直接调用这个类的构造函数或者创建一些子类来继承这个MotionValue的类。

 - **updateAndNotify:** \(v:V, render?:boolean\) =&gt; void



**destroy\(\):** void

取消对于MotionValue的订阅

当你使用useMotionValue和useTransform这两个方法时，会返回一个MotionValue对象并且自动和它的生命周期函数相关联，所以这个方法只有在你手动通过MotionValue函数创建一个MotionValue对象时，需要取消订阅时才用到。



**get\(\):** V

返回MotionValue对象最新的状态

| returns:V |
| :--- |
|  - MotionValue的最新的状态 |

  
**getVelocity\(\):** number

返回MotionValue对象最新的速度

| returns：number |
| :--- |
|  - 返回MotionValue对象最新的速度 |



**isAnimating\(\):** boolean

当绑定的值在发生变化时，返回true

| returns:boolean |
| :--- |




**onChange\(subscription\):** \(\) =&gt; void

这是一个当MotionValue对象的值改变的时候会执行传入函数的方法（）

这个方法会返回一个函数，当它执行这个返回的函数，那么订阅会被取消。

要在useEffect方法中使用onChange，因为它会返回取消订阅的函数，如果在useEffect函数里面将取消订阅的函数返回出去，那么当组件刷新时就会先把原先的订阅取消了，再重新订阅，这样就避免了重复订阅

```jsx
function MyComponent() {
  const x = useMotionValue(0)
  const y = useMotionValue(0)
  const opacity = useMotionValue(1)

  useEffect(() => {
    function updateOpacity() {
      const maxXY = Math.max(x.get(), y.get())
      const newOpacity = transform(maxXY, [0, 100], [1, 0])
      opacity.set(newOpacity)
    }

    const unsubscribeX = x.onChange(updateOpacity)
    const unsubscribeY = y.onChange(updateOpacity)

    return () => {
      unsubscribeX()
      unsubscribeY()
    }
  }, [])

  return <Frame x={x} />
}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>subscription:Subscribe&lt;T&gt;</p>
        <p>&#x4E00;&#x4E2A;&#x5F53;&#x88AB;&#x8BA2;&#x9605;&#x7684;MotionValue&#x6570;&#x503C;&#x66F4;&#x65B0;&#x7684;&#x65F6;&#x5019;&#x8981;&#x6267;&#x884C;&#x7684;&#x51FD;&#x6570;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>returns:() =&gt; void</p>
        <p>&#x8FD4;&#x56DE;&#x4E00;&#x4E2A;&#x51FD;&#x6570;&#x53EF;&#x4EE5;&#x53D6;&#x6D88;&#x76F8;&#x5173;&#x8BA2;&#x9605;</p>
      </td>
    </tr>
  </tbody>
</table>

**set:\(v, render\):** void

设置MotionValue状态值

```jsx
const x = useMotionValue(0)
x.set(10)
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>v:V</p>
        <p>&#x6700;&#x65B0;&#x7684;&#x8981;&#x88AB;&#x8BBE;&#x5B9A;&#x7684;&#x503C;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>render: </b>boolean</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x662F;&#x5426;&#x901A;&#x77E5;&#x8BA2;&#x9605;&#x5BF9;&#x8C61;&#xFF08;&#x662F;&#x5426;&#x4F1A;&#x8BA9;onChange&#x65B9;&#x6CD5;&#x4F20;&#x5165;&#x7684;&#x51FD;&#x6570;&#x6267;&#x884C;&#xFF09;&#x3002;&#x9ED8;&#x8BA4;&#x662F;true&#x3002;</td>
    </tr>
  </tbody>
</table>\*\*\*\*

**stop:** void

停止现在正在进行的动画

## AnimationControls

同时控制一个或者多个动画



**set\(definition\):** void

直接给控制器设置动画参数或者variants变量对象中的一个属性

```jsx
// With properties
controls.set({ opacity: 0 })

// With variants
controls.set("hidden")
```

| definition: VariantLabels \| TargetAndTransition |
| :--- |




**start\(definition, transitionOverride\):** Promise&lt;any&gt;

启动动画，会同时在所有的关联组件上启动

```jsx
controls.start("variantLabel")
controls.start({
  x: 0,
  transition: { duration: 1 }
})
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>definition:AnimationDefinition</p>
        <p>&#x7528;&#x6765;&#x5B9E;&#x73B0;&#x52A8;&#x753B;&#x7684;&#x52A8;&#x753B;&#x53C2;&#x6570;&#x6216;&#x8005;variants&#x5BF9;&#x8C61;&#x4E2D;&#x7684;&#x4E00;&#x4E2A;&#x5C5E;&#x6027;&#x540D;&#x79F0;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>transitionOverride:</b>Transition</p>
        <p>&#x53EF;&#x9009;&#x7684;&#x53C2;&#x6570;&#xFF0C;&#x7528;&#x6765;&#x5B9A;&#x4E49;&#x4F60;&#x81EA;&#x5DF1;&#x60F3;&#x8981;&#x7684;&#x8FC7;&#x6E21;&#x53C2;&#x6570;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>returns:</b> Promise&lt;any&gt;</td>
    </tr>
    <tr>
      <td style="text-align:left">- &#x5F53;&#x6240;&#x6709;&#x52A8;&#x753B;&#x90FD;&#x6267;&#x884C;&#x5B8C;&#x6210;&#xFF0C;&#x8FD4;&#x56DE;&#x7684;Promise&#x5BF9;&#x8C61;&#x4F1A;resolve</td>
    </tr>
  </tbody>
</table>

**stop\( \):** void

停止所有通过控制器绑定的组件的动画

```jsx
controls.stop()
```



**EasingFunction**

一个函数接收一个名称为progress的参数，这个参数值的在0-1范围内，并且返回一个也是0-1范围的值

```jsx
const transition = {
  ease: progress => progress * progress
}

<Frame
  animate={{ opacity: 0 }}
  transition={transition}
/>
```



**TargetAndTransition**

一个对象，里面设置了动画的参数。每一个属性可以是单独的一个值，或者一个包含各种值的数组。

它也有可能包含以下属性：

 - transition：特殊的动画过渡参数，专门用来给某一个或者所有动画效果设置

 - transitionEnd: 当动画完成后对组件设置的属性和值

```jsx
const target = {
  x: "0%",
  opacity: 0,
  transition: { duration: 1 },
  transitionEnd: { display: "none" }
}
```








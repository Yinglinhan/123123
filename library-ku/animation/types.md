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












# Drag

drag的操作和pan操作的规则相同，但是有一个最大的区别是，drag操作的组件是真实发生位移才会触发。

**onDrag\(event, info\)**: void

当组件被拖动时，绑定的函数会被触发

```jsx
function onDrag(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame drag onDrag={onDrag} />
```

| 绑定函数的参数 |
| :--- |
| **event:** MouseEvent \| TouchEvent \| PointerEvent |
| **info:** PanInfo |



**onDragStart\(event, info\):** void

当组件刚被拖动的时候触发绑定的函数

```jsx
function onDragStart(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame drag onDragStart={onDragStart} />
```

| 绑定函数的参数 |
| :--- |
| **event:** MouseEvent \| TouchEvent \| PointerEvent |
| **info:** PanInfo |



**onDragEnd\(event, info\):** void

当组件拖动结束时会触发绑定的函数

```jsx
function onDragEnd(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame drag onDragEnd={onDragEnd} />
```

| 绑定函数的参数 |
| :--- |
| **event:** MouseEvent \| TouchEvent \| PointerEvent |
| **info:** PanInfo |



**onDirectionLock\(axis\):** void

当拖动的方向被锁定时会触发绑定的函数

```jsx
function onDirectionLock(axis) {
  console.log(axis)
}

<Frame
  drag
  dragDirectionLock
  onDirectionLock={onDirectionLock}
/>
```

| axis: "x" \| "y" |
| :--- |




**drag:** boolean \| "x" \| "y"

通过这个属性能设置该标签元素是否能被拖动，默认是false，如果设置为true，则可往任意方向拖动。设置成"x"或者"y"方向则只能在该方向上拖动。

```jsx
<Frame drag="x" />
```



**dragConstraints:** false \| { top?:number; right?:number; left?: number; bottom?:number } \| RefObject&lt;Element&gt;

可以传入一个包含top，left，right，bottom属性的数值对象，这样就可以设置元素的被拖拽限制范围，注意，如果要设置向右和向上的拖拽距离限制，要用负数。

另外你也可以使用React中的useRef这个hook，通过使用这个功能，你可以把某个元素的范围设置为拖动限制区域。

```jsx
// In pixels
<Frame
  drag="x"
  dragConstraints={{ left: 0, right: 300 }}
/>

// As a ref to another component
function MyComponent() {
  const constraintsRef = useRef(null)

  return (
     <Frame ref={constraintsRef} width={400} height={400}>
         <Frame drag dragConstraints={constraintsRef} />
     </Frame>
  )
}
```



**dragElastic:** boolean \| number

这个属性用来设置拖拽的时候能够超出限制区域的效果。0就是没有这样的效果，1是最大的效果，0.5是默认的设置。

```jsx
<Frame
  drag={true}
  dragConstraints={{ left: 0, right: 300 }}
  dragElastic={0.2}
/>
```



**dragMomentum:** boolean

设置拖拽结束后的一个运动效果。默认是true。

```jsx
<Frame
  drag={true}
  dragConstraints={{ left: 0, right: 300 }}
  dragMomentum={false}
/>
```



**dragTransition:** InertiaOptions

这个可以用来修改拖拽结束后的惯性效果参数。当我们拖拽一个Frame标签，当我们放开的时候，它会有一定惯性的动画效果，这是根据你拖拽结束时的速度来计算生成的，当然你也可以进行自定义。你可以参看Inertia部分的内容，里面有更具体的其他参数的设置。

```jsx
<Frame
  drag={true}
  dragTransition={{ bounceStiffness: 600, bounceDamping: 10 }}
/>
```



**dragPropagation:** boolean

允许拖拽操作事件传递到子组件中，默认是设置为false。

```jsx
<Frame drag="x" dragPropagation={true} />
```
























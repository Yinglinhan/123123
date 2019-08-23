# 基础

#### 动画 Animate

让我们来做一个简单的动画效果，让一个**Frame**缩放到它自身的一半大小。注意，你可以把**Frame**元素和其他HTML元素混起来用，就像你在使用其他的React组件一样。

```jsx
export function MyComponent() {
  return <Frame animate={{ scale: 0.5 }} />
}
```



#### 切换 Cycle

这是一个更常用的例子，你有时候会需要点击切换一个元素的缩放，这可以通过**useCycle**这个功能去实现，在使用它时你需要传入一组数据。

```jsx
// Cycle scale on tap
export function MyComponent() {
  const [scale, cycle] = useCycle(3, 1)
  return (
    <Frame
      animate={{ scale: scale }}
      onTap={() => cycle()}
    />
  )
}
```

你在使用**useCycle**这个功能时，可以传入两个对象，表示两个状态的数据。这里我们在对象里设置了**rotate**（旋转），这样每次点击这个元素的时候不仅会切换缩放，也会切换旋转的角度。



#### 拖拽 Dragging

你能轻松得让任何一个Frame可以拖拽，只要你在**Frame**标签上使用了**drag**属性。如果你想要限制只能在垂直方向或者水平方向的拖拽，那么你需要给drag属性赋值，"x"是只能水平拖拽，"y"是只能垂直方向拖拽。

```jsx
// Drag Frame in any direction
export function MyComponent() {
  return <Frame drag />
}
```



#### 滚动 Scrolling

如果你想要做一个滚动的效果，那么你可以把你的内容放到**Scroll**组件当中去，同时你的内容的尺寸要在滚动方向上超过**Scroll**组件才能实现滚动的效果。

```jsx
// Scroll two Frames
export function MyComponent() {
  return (
    <Scroll>
      <Frame />
      <Frame />
    </Scroll>
  )
}
```


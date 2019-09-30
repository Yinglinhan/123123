# Inertia 惯性

这是当你拖动一个Frame元素并且释放的时候会产生的动画效果。这个减速的动画效果是基于元素初始的速度的。min，max这个两个边界参数是作为可选项进行设置。如果设置了min和max这个参数，这个动画效果可以产生弹性效果，你可以自行设置相关的参数对象赋值给dragTransition这个属性来改变这个动画效果。

**bounceDamping:** number

如果你设置了min或者max这个两个参数中的其中一个，那么属性会影响弹性动画的阻尼。如果设置为0，那么这个元素会一直来回晃动，默认的值是0。

```jsx
const transition = {
  min: 0,
  max: 100,
  bounceDamping: 8
}

<Frame
  drag
  dragTransition={transition}
/>
```



**bounceStiffness:** number

如果已经设置了min或者max的参数，那么设置这个参数会影响弹性动画的柔和度。越高的数值就会让动画效果变得越硬。默认这是是500。

```jsx
const transition = {
  min: 0,
  max: 100,
  bounceStiffness: 100
}

<Frame
  drag
  dragTransition={transition}
/>
```



**max:** number

最大的限制量，当动画超出这个范围，那么会回到这个范围的边界。

```jsx
<Frame
  drag
  dragTransition={{ min: 0, max: 100 }}
/>
```



**min:** number

最小限制范围，如果在这回范围以外，元素就会回到这个范围的边界。

```jsx
<Frame
  drag
  dragTransition={{ min: 0, max: 100 }}
/>
```



**power:** number

A higher power value equals a further target. Set to `0.8` by default.（待翻）

```jsx
const transition = {
  min: 0,
  max: 100,
  power: 0.2
}

<Frame
  drag
  dragTransition={transition}
/>
```



**restDelta:** number

当元素在动画时的距离目标距离的值小于这个设定的值时，就会立即结束动画并到目标结束的位置。默认的设置是0.01，默认这个设置会让动画更平滑，只有在相当少见的情况下你才需要去修改这个参数。

```jsx
const transition = {
  min: 0,
  max: 100,
  restDelta: 10
}

<Frame
  drag
  dragTransition={transition}
/>
```



**timeConstant:** number

调整这个参数会改变元素的减速的过程的时间。默认是700。

```jsx
const transition = {
  min: 0,
  max: 100,
  timeConstant: 200
}

<Frame
  drag
  dragTransition={transition}
/>
```



**modifyTarget\( v \):** number

这个参数可以使用一个函数，自动传入一个点击位置的数字值，然后返回一个另外的数字值，从而可以实现一种类似于贴着网格拖拽的效果。

```jsx
const transition = {
  power: 0,
  // Snap calculated target to nearest 50 pixels
  modifyTarget: target => Math.round(target / 50) * 50
}

<Frame
  drag
  dragTransition={transition}
/>
```

| 函数参数和返回值 |
| :--- |
| **v:** number |
| **returns:** number |






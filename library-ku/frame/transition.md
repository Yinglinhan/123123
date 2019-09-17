# Transition 过渡

transition属性是用来给Frame标签设定动画过渡的参数用的。transition这个属性被设置之后，会应用到所有在这个Frame标签上的动画效果。如果你有在其他地方设置了transition的参数，比如说你通过variants参数的对象或者单纯的transition参数的对象应用到了animate、hover或者press等属性上，那么transition这个属性的数据会被覆盖，也就是说只要某个的动画效果里面设置了自己的transition的参数就会使用它自己的过渡效果。

```jsx
<Frame
  animate={{ scale: 0.5 }}
  transition={{ ease: "easeOut" }}
/>
```

你可以在每一个动画效果都定义自己的transition过渡参数，任何一个没有单独设置transition的动画都会使用默认的一个动画过渡效果。

```jsx
const transition = {
  x: { type: "spring", stiffness: 400 },
  opacity: { ease: "easeIn" },
}
```

你可以通过给单独的动画设置自己的transition参数来覆盖默认的transition参数。

```jsx
const transition = {
  x: { type: "keyframes", values: [0, 100, 0] },
  default: { duration: 0.5 },
}
```

你可以在transition里面使用delay来让某个动画 延迟一定时间开始。它的数字值的单位是秒。

```jsx
const transition = {
  delay: 1,
  opacity: { duration: 0.5 },
}
```

transition的参数也可以通过variants属性来设置，在相应的variant里面设置单独的动画过渡属性，这样在Frame变化时就会产生效果。

```jsx
const variants = {
  hidden: {
    opacity: 0,
    transition: { duration: 0.25 },
  },
  visible: { opacity: 1 },
}
```










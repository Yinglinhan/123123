# Spring

这是一种模拟真实物理运动中弹簧抖动的动画效果。这些是元素物理属性上发生变化时默认的动画效果，比如说位移，x、y和rotate。

**type:** "spring"

设置type属性的值为"spring"就能使用这种自然的运动动画效果。Type默认的设置就是"spring"

```jsx
const transition = {
  type: "spring"
}

<Frame
  animate={{ rotate: 180 }}
  transition={transition}
/>
```



**damping:** number

这个参数是设置反作用力的强度，默认是10，如果你设置为0，那么元素会无休止的晃动。

```jsx
const transition = {
  type: "spring",
  damping: 300
}

<Frame
  animate={{ rotate: 180 }}
  transition={transition}
/>
```



**mass:** number

这个参数是模拟物体的质量，这个值设置得越大，那么它的运动就越看起来越笨重，默认是1。

```jsx
const transition = {
  type: "spring",
  mass: 0.5
}

<Frame
  animate={{ rotate: 180 }}
  transition={transition}
/>
```



**stiffness:** number

这个参数改变弹性动画的柔和度，数值越大，动起来就越僵硬。默认是100。

```jsx
const transition = {
  type: "spring",
  stiffness: 50
}

<Frame
  animate={{ rotate: 180 }}
  transition={transition}
/>
```



**velocity:** number

弹性动画的初始速度，默认就是该元素的当前速度。

```jsx
const transition = {
  type: "spring",
  velocity: 2
}

<Frame
  animate={{ rotate: 180 }}
  transition={transition}
/>
```



**restSpeed:** number

当元素的绝对速度小于这个restSpeed的值，同时元素的delta值小于restDelta值的话，动画就会立即结束。这个默认值是0.01。

```jsx
const transition = {
  type: "spring",
  restSpeed: 0.5
}

<Frame
  animate={{ rotate: 180 }}
  transition={transition}
/>
```



**restDelta:** number

当元素运动的距离小于这个设定的值，同时运动速度小于设置的restSpeed，那么动画就会立即结束，元素就会停在应该停留的位置，默认是0.01。

```jsx
const transition = {
  type: "spring",
  restDelta: 0.5
}

<Frame
  animate={{ rotate: 180 }}
  transition={transition}
/>
```


















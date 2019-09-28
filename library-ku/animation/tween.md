# Tween

这是一种在两个或两个以上状态之间在一定时间内发生变化的动画方式。这是非物理运动的值的动画的默认动画方式，比如说一个元素的透明度，比如说颜色。

**type:** "tween"

设置type属性为"tween"，这样就能使用duration这个属性让动画在一定时间内发生变化，如果一个没有设置分步动画属性的transition也没有设置type属性，那么"tween"就是默认的一种动画方式。

```jsx
<Frame
  animate={{ opacity: 0 }}
  transition={{ duration: 2, type: "tween" }}
/>
```



**duration:**number

duration属性就是设置整个tween动画的时长，默认是0.3，如果是一系列帧动画，那么默认是0.8

```jsx
<Frame
  animate={{ opacity: 0 }}
  transition={{ duration: 2 }}
/>
```



**ease:** Easing \| Easing \[ \]

可以设置动运动曲线，有以下几种设置方式：

 - 现有的几种运动曲线

 - 用一个包含四个数字的数组定义一条贝塞尔曲线。就像现有运动曲线一样，它接收和返回的数值都是0-1范围内的

如果你的动画式用一个包含多个数字的数组来驱动实现关键帧动画的，那么你就可以用一个包含了多个动画曲线名称的数组来实现关键帧动画之间不同的动画曲线效果。

Framer内置的动画曲线，使用时用字符串的类型

 - "linear"

 - "easeIn", "easeOut", "easeInOut"

 - "circIn", "circOut", "circInOut"

 - "backIn", "backOut", "backInOut"

 - "anticipate"



**from:**number \| string

从哪一个状态开始变化，默认是元素要变化属性的当前的状态

```jsx
const transition = {
  from: 90,
  duration: 2
}

<Frame
  animate={{ rotate: 180 }}
  transition={transition}
/>
```



**loop:**number

设置动画变化的循环次数，设置为Infinity则为无限的循环

```jsx
const transition = {
  loop: Infinity,
  ease: "linear",
  duration: 2
}

<Frame
  animate={{ rotate: 360 }}
  transition={transition}
/>
```



**flip**:number

用flip的方式来实现动画，动画从初始状态变化到设定状态后，会快速变化回初始状态，然后再重新开始动画。（待定）

```jsx
const transition = {
  flip: Infinity,
  duration: 2
}

<Frame
  animate={{ opacity: 0 }}
  transition={transition}
/>
```



**yoyo:** number

设置动画变化从两个状态之间循环往复的次数，即正向变化然后再反向变化，设置为Infinity则为无限循环往复，单个方向的变化持续时间就是设置的duration。

```jsx
const transition = {
  yoyo: Infinity,
  duration: 2
}

<Frame
  animate={{ rotate: 180 }}
  transition={transition}
/>
```



**repeatDelay:** number

当给动画设置各种循环之后，这个属性可以用来设置每次循环之前的等待时间，单位是秒。

```jsx
const transition = {
  yoyo: Infinity,
  repeatDelay: 1
}

<Frame
  animate={{ rotate: 180 }}
  transition={transition}
/>
```



**times:** number\[ \]

当你使用关键帧动画时，这个times可以设置一个在0-1范围内的一次增大的数字，用来实现每个关键帧阶段分别使用的时间。

times这个数组的数字的数量必须和关键帧动画中数据数量一致。默认的关键帧动画之间的时间是平分设置的duration时间。

```jsx
const transition = {
  times: [0, 0.1, 0.9, 1]
}

<Frame
  animate={{ scale: [0, 1, 0.5, 1] }}
  transition={transition}
/>
```




























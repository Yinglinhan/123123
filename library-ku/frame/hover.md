# Hover 悬浮

悬浮是是指鼠标指针或者是手指在组件区域内或者离开组件区域的一种行为。

它和原生的onMouseEnter和onMouseLeave事件不太一样，原生的这两个事件是专门针对鼠标的悬浮行为的，但是这里的悬浮也包括用手指操作，即当你把手指放在组件上持续一段时间，也是悬浮的操作。

**whileHover:** string \| TargetAndTransition

直接使用一些属性或者用variant定义好的其中一个属性名称去驱动hover发生时的动画效果。

```jsx
<Frame whileHover={{ scale: 1.2 }} />
```



**onHoverStart\(event, info\):** void

传递一个回调函数，当悬浮操作一开始时就会触发这个函数

| 回调函数的参数 |
| :--- |
| **event:** MouseEvent 事件对象 |
| **info:** EventInfo 事件信息 |

```jsx
function onHoverStart(event) {
  console.log("Hover starts")
}

<Frame onHoverStart={onHoverStart} />
```



**onHoverEnd\(event, info\):** void

传递一个回调函数，当悬浮操作一结束时就会触发这个函数

| 回调函数的参数 |
| :--- |
| **event:** MouseEvent 事件对象 |
| **info:** EventInfo 事件信息 |

```jsx
function onHoverEndStart(event) {
  console.log("Hover starts")
}

<Frame onHoverEnd={onHoverStart} />
```






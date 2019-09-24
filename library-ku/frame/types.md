# Types

### Tapinfo

tap事件的回调函数中有Tapinfo对象，里面包含了很多信息例如像点击的位置。

```jsx
function onTap(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame onTap={onTap} />
```



**point:** Point

这个属性包含了x和y的值，是点击的位置相对于设备或者是页面的坐标数据

```jsx
function onTapStart(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame onTapStart={onTapStart} />
```



### PanInfo

pan事件触发的函数会传入一个PanInfo对象，它包含了当前的操作的一些信息，比如point、delta、offset和velocity。

```jsx
function onPan(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame onPan={onPan} />
```



**delta:** Point

这个属性包含了x和y的值，是相对于上一次触发事件位置的距离值。

```jsx
function onPan(event, info) {
  console.log(info.delta.x, info.delta.y)
}

<Frame onPan={onPan} />
```



**offset:** Point

这个属性包含了x和y的值，是相对于第一次触发事件位置的距离值。

```jsx
function onPan(event, info) {
  console.log(info.offset.x, info.offset.y)
}

<Frame onPan={onPan} />
```



**point:** Point

这个属性包含了x和y的值，是点击的位置相对于设备或者是页面的坐标数据

```jsx
function onPan(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame onPan={onPan} />
```



**velocity:** Point

这个属性包含了x和y的值，是当前触发点的速度

```jsx
function onPan(event, info) {
  console.log(info.velocity.x, info.velocity.y)
}

<Frame onPan={onPan} />
```


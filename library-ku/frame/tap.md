# Tap 点击

当手指或者鼠标在一个组件上按下然后放开，这样就是一次点击行为Tap。

Tap在一个组件上会触发一个tap事件，如果点击释放时鼠标或者手指不在该组件上就会触发一个tapCancel的事件。

如果被点击的组件是一个可拖拽组件的子元素，那么它会在你的手指或者鼠标在点击过程中移动了三个像素之后自动取消该手势。



**whileTap:** string \| TargetAndTransition

用动画的参数和variants对象中的属性名赋值，当组件被按住的时候就会发生相应的动画。

```jsx
<Frame whileTap={{ scale: 0.8 }} />
```



**onTap\(event , info\):** void

这个属性给它赋值一个回调函数，当点击操作完成时就会触发相应的函数执行。

```jsx
function onTap(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame onTap={onTap} />
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x56DE;&#x8C03;&#x51FD;&#x6570;&#x4E2D;&#x7684;&#x53C2;&#x6570;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>event</b>: MouseEvent | TouchEvent | PointerEvent</p>
        <p>&#x539F;&#x751F;&#x7684;&#x70B9;&#x51FB;&#x4E8B;&#x4EF6;&#x5BF9;&#x8C61;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>info: </b>TapInfo</p>
        <p>&#x5305;&#x542B;&#x70B9;&#x51FB;&#x4F4D;&#x7F6E;&#x76F8;&#x5BF9;&#x4E8E;&#x9875;&#x9762;&#x6216;&#x8005;&#x8BBE;&#x5907;&#x7684;&#x5750;&#x6807;&#x4FE1;&#x606F;</p>
      </td>
    </tr>
  </tbody>
</table>

**onTapStart\(event, info\)**:void

当点击操作一开始时会触发相应的回调函数

```jsx
function onTapStart(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame onTapStart={onTapStart} />
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x56DE;&#x8C03;&#x51FD;&#x6570;&#x4E2D;&#x7684;&#x53C2;&#x6570;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>event</b>: MouseEvent | TouchEvent | PointerEvent</p>
        <p>&#x539F;&#x751F;&#x7684;&#x70B9;&#x51FB;&#x4E8B;&#x4EF6;&#x5BF9;&#x8C61;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>info: </b>TapInfo</p>
        <p>&#x5305;&#x542B;&#x70B9;&#x51FB;&#x4F4D;&#x7F6E;&#x76F8;&#x5BF9;&#x4E8E;&#x9875;&#x9762;&#x6216;&#x8005;&#x8BBE;&#x5907;&#x7684;&#x5750;&#x6807;&#x4FE1;&#x606F;</p>
      </td>
    </tr>
  </tbody>
</table>



**onTapCancel\(event, info\)**:void

当点击操作取消时会触发相应的回调函数

```jsx
function onTapCancel(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame onTapCancel={onTapCancel} />
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x56DE;&#x8C03;&#x51FD;&#x6570;&#x4E2D;&#x7684;&#x53C2;&#x6570;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>event</b>: MouseEvent | TouchEvent | PointerEvent</p>
        <p>&#x539F;&#x751F;&#x7684;&#x70B9;&#x51FB;&#x4E8B;&#x4EF6;&#x5BF9;&#x8C61;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>info: </b>TapInfo</p>
        <p>&#x5305;&#x542B;&#x70B9;&#x51FB;&#x4F4D;&#x7F6E;&#x76F8;&#x5BF9;&#x4E8E;&#x9875;&#x9762;&#x6216;&#x8005;&#x8BBE;&#x5907;&#x7684;&#x5750;&#x6807;&#x4FE1;&#x606F;</p>
      </td>
    </tr>
  </tbody>
</table>














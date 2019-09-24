# Pan

Pan方法是当你鼠标或者手指按住某个物体尝试想去拖动它的时候，鼠标或者手指在按住这个元素的情况下移动的距离超过3个像素就会触发，并且一直会持续触发，直到松开。它这个拖动可以不是真实的拖动，即物体可以不动，但是只要你鼠标是按住的，并且鼠标本身发生移动，这个事件就会触发，所以这个操作的触发是以鼠标或者手指移动的距离为判断，而不是被操作的物体的位移。

**onPan\(event, info\):** void

当Pan这个行为发生时会一直触发该回调函数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x56DE;&#x8C03;&#x51FD;&#x6570;&#x7684;&#x53C2;&#x6570;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>event:</b> MouseEvent | TouchEvent | PointerEvent &#x4E0D;&#x540C;&#x7684;&#x8BBE;&#x5907;&#x64CD;&#x4F5C;&#x65F6;&#x4F1A;&#x6709;&#x4E0D;&#x540C;&#x7684;&#x4E8B;&#x4EF6;&#x5BF9;&#x8C61;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>info:</b> PanInfo</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#x4E00;&#x4E2A;&#x5BF9;&#x8C61;&#xFF0C;&#x5305;&#x542B;&#x5404;&#x79CD;x&#x548C;y&#x7684;&#x5750;&#x6807;&#x503C;</p>
        <p>- <b>point:</b> &#x60F3;&#x5BF9;&#x4E8E;&#x8BBE;&#x5907;&#x6216;&#x8005;&#x9875;&#x9762;</p>
        <p>- <b>delta: </b>&#x4E0A;&#x4E00;&#x6B21;&#x89E6;&#x53D1;&#x4E8B;&#x4EF6;&#x65F6;&#x548C;&#x5F53;&#x524D;&#x89E6;&#x53D1;&#x4E8B;&#x4EF6;&#x65F6;&#x7684;&#x5750;&#x6807;&#x503C;&#x7684;&#x8DDD;&#x79BB;</p>
        <p>- <b>offset:</b> &#x548C;&#x6700;&#x5F00;&#x59CB;&#x89E6;&#x53D1;&#x4E8B;&#x4EF6;&#x65F6;&#x7684;&#x70B9;&#x7684;&#x504F;&#x79FB;&#x8DDD;&#x79BB;</p>
        <p>- <b>velocity:</b> &#x5F53;&#x524D;&#x9F20;&#x6807;&#x6216;&#x8005;&#x64CD;&#x4F5C;&#x8BBE;&#x5907;&#x7684;&#x901F;&#x5EA6;</p>
      </td>
    </tr>
  </tbody>
</table>```jsx
function onPan(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame onPan={onPan} />
```



**onPanStart\(event, info\):** void

当Pan这个行为一开始发生时会触发该回调函数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x56DE;&#x8C03;&#x51FD;&#x6570;&#x7684;&#x53C2;&#x6570;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>event:</b> MouseEvent | TouchEvent | PointerEvent &#x4E0D;&#x540C;&#x7684;&#x8BBE;&#x5907;&#x64CD;&#x4F5C;&#x65F6;&#x4F1A;&#x6709;&#x4E0D;&#x540C;&#x7684;&#x4E8B;&#x4EF6;&#x5BF9;&#x8C61;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>info:</b> PanInfo</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#x4E00;&#x4E2A;&#x5BF9;&#x8C61;&#xFF0C;&#x5305;&#x542B;&#x5404;&#x79CD;x&#x548C;y&#x7684;&#x5750;&#x6807;&#x503C;</p>
        <p>- <b>point:</b> &#x60F3;&#x5BF9;&#x4E8E;&#x8BBE;&#x5907;&#x6216;&#x8005;&#x9875;&#x9762;</p>
        <p>- <b>delta: </b>&#x4E0A;&#x4E00;&#x6B21;&#x89E6;&#x53D1;&#x4E8B;&#x4EF6;&#x65F6;&#x548C;&#x5F53;&#x524D;&#x89E6;&#x53D1;&#x4E8B;&#x4EF6;&#x65F6;&#x7684;&#x5750;&#x6807;&#x503C;&#x7684;&#x8DDD;&#x79BB;</p>
        <p>- <b>offset:</b> &#x548C;&#x6700;&#x5F00;&#x59CB;&#x89E6;&#x53D1;&#x4E8B;&#x4EF6;&#x65F6;&#x7684;&#x70B9;&#x7684;&#x504F;&#x79FB;&#x8DDD;&#x79BB;</p>
        <p>- <b>velocity:</b> &#x5F53;&#x524D;&#x9F20;&#x6807;&#x6216;&#x8005;&#x64CD;&#x4F5C;&#x8BBE;&#x5907;&#x7684;&#x901F;&#x5EA6;</p>
      </td>
    </tr>
  </tbody>
</table>```jsx
function onPanStart(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame onPanStart={onPanStart} />
```



**onPanEnd\(event, info\):** void

当Pan这个行为结束时会触发该回调函数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x56DE;&#x8C03;&#x51FD;&#x6570;&#x7684;&#x53C2;&#x6570;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>event:</b> MouseEvent | TouchEvent | PointerEvent &#x4E0D;&#x540C;&#x7684;&#x8BBE;&#x5907;&#x64CD;&#x4F5C;&#x65F6;&#x4F1A;&#x6709;&#x4E0D;&#x540C;&#x7684;&#x4E8B;&#x4EF6;&#x5BF9;&#x8C61;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>info:</b> PanInfo</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#x4E00;&#x4E2A;&#x5BF9;&#x8C61;&#xFF0C;&#x5305;&#x542B;&#x5404;&#x79CD;x&#x548C;y&#x7684;&#x5750;&#x6807;&#x503C;</p>
        <p>- <b>point:</b> &#x60F3;&#x5BF9;&#x4E8E;&#x8BBE;&#x5907;&#x6216;&#x8005;&#x9875;&#x9762;</p>
        <p>- <b>delta: </b>&#x4E0A;&#x4E00;&#x6B21;&#x89E6;&#x53D1;&#x4E8B;&#x4EF6;&#x65F6;&#x548C;&#x5F53;&#x524D;&#x89E6;&#x53D1;&#x4E8B;&#x4EF6;&#x65F6;&#x7684;&#x5750;&#x6807;&#x503C;&#x7684;&#x8DDD;&#x79BB;</p>
        <p>- <b>offset:</b> &#x548C;&#x6700;&#x5F00;&#x59CB;&#x89E6;&#x53D1;&#x4E8B;&#x4EF6;&#x65F6;&#x7684;&#x70B9;&#x7684;&#x504F;&#x79FB;&#x8DDD;&#x79BB;</p>
        <p>- <b>velocity:</b> &#x5F53;&#x524D;&#x9F20;&#x6807;&#x6216;&#x8005;&#x64CD;&#x4F5C;&#x8BBE;&#x5907;&#x7684;&#x901F;&#x5EA6;</p>
      </td>
    </tr>
  </tbody>
</table>```jsx
function onPanEnd(event, info) {
  console.log(info.point.x, info.point.y)
}

<Frame onPanEnd={onPanEnd} />
```




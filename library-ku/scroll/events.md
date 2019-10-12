# Events

**onScroll\(info\):** void

当滚动时周期性地调用该事件绑定的函数

```jsx
function onScroll(info) {
  console.log(info.offset, info.velocity)
}

<Scroll onScroll={onScroll} />
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>info: PanInfo</p>
        <p>&#x8FD9;&#x4E2A;&#x5BF9;&#x8C61;&#x5305;&#x542B;&#x4E86;&#x5404;&#x79CD;x&#x548C;y&#x7684;&#x4FE1;&#x606F;:</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">- <b>point: </b>&#x76F8;&#x5BF9;&#x4E8E;&#x8BBE;&#x5907;&#x6216;&#x8005;&#x9875;&#x9762;&#x7684;&#x4F4D;&#x7F6E;&#x4FE1;&#x606F;</td>
    </tr>
    <tr>
      <td style="text-align:left">- <b>delta&#xFF1A;</b>&#x548C;&#x4E0A;&#x4E00;&#x6B21;&#x4E8B;&#x4EF6;&#x89E6;&#x53D1;&#x65F6;&#x7684;&#x8DDD;&#x79BB;</td>
    </tr>
    <tr>
      <td style="text-align:left">- <b>offset:</b> &#x4E0E;&#x521A;&#x5F00;&#x59CB;&#x6EDA;&#x52A8;&#x65F6;&#x9F20;&#x6807;&#x6216;&#x8005;&#x624B;&#x6307;&#x4F4D;&#x7F6E;&#x76F8;&#x6BD4;&#x7684;&#x504F;&#x79FB;&#x91CF;</td>
    </tr>
    <tr>
      <td style="text-align:left">- <b>velocity:</b> &#x5F53;&#x524D;&#x6307;&#x9488;&#x7684;&#x901F;&#x5EA6;</td>
    </tr>
  </tbody>
</table>

**onScrollStart\(info\):** void

开始滚动时触发绑定的函数

```jsx
function onScrollStart(info) {
  console.log(info.offset, info.velocity)
}

<Scroll onScrollStart={onScrollStart} />
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>info: PanInfo</p>
        <p>&#x8FD9;&#x4E2A;&#x5BF9;&#x8C61;&#x5305;&#x542B;&#x4E86;&#x5404;&#x79CD;x&#x548C;y&#x7684;&#x4FE1;&#x606F;:</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">- <b>point: </b>&#x76F8;&#x5BF9;&#x4E8E;&#x8BBE;&#x5907;&#x6216;&#x8005;&#x9875;&#x9762;&#x7684;&#x4F4D;&#x7F6E;&#x4FE1;&#x606F;</td>
    </tr>
    <tr>
      <td style="text-align:left">- <b>delta&#xFF1A;</b>&#x548C;&#x4E0A;&#x4E00;&#x6B21;&#x4E8B;&#x4EF6;&#x89E6;&#x53D1;&#x65F6;&#x7684;&#x8DDD;&#x79BB;</td>
    </tr>
    <tr>
      <td style="text-align:left">- <b>offset:</b> &#x4E0E;&#x521A;&#x5F00;&#x59CB;&#x6EDA;&#x52A8;&#x65F6;&#x9F20;&#x6807;&#x6216;&#x8005;&#x624B;&#x6307;&#x4F4D;&#x7F6E;&#x76F8;&#x6BD4;&#x7684;&#x504F;&#x79FB;&#x91CF;</td>
    </tr>
    <tr>
      <td style="text-align:left">- <b>velocity:</b> &#x5F53;&#x524D;&#x6307;&#x9488;&#x7684;&#x901F;&#x5EA6;</td>
    </tr>
  </tbody>
</table>

**onScrolEnd\(info\):** void

开始结束时触发绑定的函数

```jsx
function onScrollEndStart(info) {
  console.log(info.offset, info.velocity)
}

<Scroll onScrollEnd={onScrollEnd} />
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>info: PanInfo</p>
        <p>&#x8FD9;&#x4E2A;&#x5BF9;&#x8C61;&#x5305;&#x542B;&#x4E86;&#x5404;&#x79CD;x&#x548C;y&#x7684;&#x4FE1;&#x606F;:</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">- <b>point: </b>&#x76F8;&#x5BF9;&#x4E8E;&#x8BBE;&#x5907;&#x6216;&#x8005;&#x9875;&#x9762;&#x7684;&#x4F4D;&#x7F6E;&#x4FE1;&#x606F;</td>
    </tr>
    <tr>
      <td style="text-align:left">- <b>delta&#xFF1A;</b>&#x548C;&#x4E0A;&#x4E00;&#x6B21;&#x4E8B;&#x4EF6;&#x89E6;&#x53D1;&#x65F6;&#x7684;&#x8DDD;&#x79BB;</td>
    </tr>
    <tr>
      <td style="text-align:left">- <b>offset:</b> &#x4E0E;&#x521A;&#x5F00;&#x59CB;&#x6EDA;&#x52A8;&#x65F6;&#x9F20;&#x6807;&#x6216;&#x8005;&#x624B;&#x6307;&#x4F4D;&#x7F6E;&#x76F8;&#x6BD4;&#x7684;&#x504F;&#x79FB;&#x91CF;</td>
    </tr>
    <tr>
      <td style="text-align:left">- <b>velocity:</b> &#x5F53;&#x524D;&#x6307;&#x9488;&#x7684;&#x901F;&#x5EA6;</td>
    </tr>
  </tbody>
</table>










# useSpring

**useSpring\(**source, config**\):** MotionValue**&lt;any&gt;**

这个方法也返回一个MotionValue的对象，当使用这个MotionValue追踪的数据发生改变的时候，会产生一个弹性动画来过渡到新的状态。

当你给它第一个参数传递的是数字的时候，它也能单独作为生成一个MotionValue对象的方法。如果你给它第一个参数传递的是一个MotionValue对象，那么它就会订阅这个MotionValue对象。

```jsx
const x = useSpring(0, { stiffness: 300 })
const y = useSpring(x, { damping: 10 })
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>source: MotionValue | number</p>
        <p>&#x53EF;&#x4EE5;&#x4F20;&#x5165;&#x6570;&#x5B57;&#x6216;&#x8005;MotionValue&#x5BF9;&#x8C61;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>config:</b> SpringProps</p>
        <p>&#x914D;&#x7F6E;&#x5F39;&#x6027;&#x52A8;&#x753B;&#x7684;&#x8FC7;&#x6E21;&#x53C2;&#x6570;&#x5BF9;&#x8C61;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>returns:</b> MotionValue&lt;any&gt;</p>
        <p>&#x8FD4;&#x56DE;&#x4E00;&#x4E2A;MotionValue&#x5BF9;&#x8C61;</p>
      </td>
    </tr>
  </tbody>
</table>
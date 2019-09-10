# Transform 变换

Transform属性利用GPU加速因此动画效果更加流畅。它们其实是利用了CSS的transfrom这个属性，比如说x=20这个属性设置其实就是CSS中的tranform:translateX\(200\)。所有的这些变换的效果都会在元素完成基本布局之后才会被应用。

在CSS中给一个元素设置多个translate属性时会有执行先后顺序的问题，那么在Frame标签上与transform相关的属性的默认执行顺序是:translate,scale,rotate和skew。当然，你也可以通过transformTemplate属性来自定义这几种属性的执行顺序。

```jsx
<Frame
  x={100}
  y={100}
  z={100}
  rotate={90}
  scale={1.2}
  skew={15}
/>
```



**x:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform中的translateX属性

```jsx
<Frame x={100} />
```



**y:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform中的translateY属性

```jsx
<Frame y={100} />
```



**z:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform中的translateZ属性

```jsx
<Frame z={100} />
```



**rotate:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform的rotate的角度值

```jsx
<Frame rotate={45}/>
```



**rotateX:** number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform的rotate的角度值

```jsx
<Frame rotateX={45}/>
```



**rotateY:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform的rotateY的角度值

```jsx
<Frame rotateY={45}/>
```



**rotateZ:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform的rotateZ的角度值

```jsx
<Frame rotateZ={45}/>
```



**scale:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transfrom的scale值

```jsx
<Frame scale={1.5} />
```



**scaleX:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transfrom的scaleX值

```jsx
<Frame scaleX={1.5} />
```



**scaleY:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transfrom的scaleY值

```jsx
<Frame scaleY={1.5} />
```



**skew:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform的skew的角度值

```jsx
<Frame skew={15} />
```





**skewX:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform的skewX的角度值

```jsx
<Frame skewX={15} />
```





**skewY:**number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform的skewY的角度值

```jsx
<Frame skewY={15} />
```



**originX**:number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform的originX的值

```jsx
<Frame originX={0.5} />
```



**originY**:number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform的originY的值

```jsx
<Frame originY={0.5} />
```



**originZ**:number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的transform的originZ的值

```jsx
<Frame originZ={0.5} />
```



**perspective:**number \| string \| motionValue&lt;number \| string&gt;

设置CSS的transform的perspective的值

```jsx
<Frame perspective={500} />
```



**preserve3d:**boolean

将该标签的子元素放置在一个3d空间中。默认是设置为false的。

```jsx
<Frame preserve3d={true} />
```



**backfaceVisible:**boolean

设置当元素的背面朝向用户是是否课件，默认是true

```jsx
<Frame backfaceVisible={true} />
```



**tranformTemplate**\(transform, generatedTransform\): string

默认情况下，Framer Motion会自动给多个transform的变化属性设定一个顺序，你可以通过transformTemplate属性来创建一个自定义的变化顺序，当然也可以在默认的顺序的基础上进行调整和修改。

```jsx
function transformTemplate({ x, rotate }) {
  return `rotate(${rotate}deg) translateX(${x}px)`
}

<Frame x={0} rotate={180} transformTemplate={transformTemplate} />
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x51FD;&#x6570; transformTemplate &#x7684;&#x53C2;&#x6570;&#x548C;&#x8FD4;&#x56DE;&#x503C;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>transform: </b>TransformProperties</p>
        <p>&#x4F60;&#x60F3;&#x8981;&#x8FDB;&#x884C;&#x8C03;&#x6574;&#x987A;&#x5E8F;&#x7684;transform&#x76F8;&#x5173;&#x7684;&#x5C5E;&#x6027;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>generatedTransform:</b> string</p>
        <p>&#x81EA;&#x52A8;&#x751F;&#x6210;&#x7684;transform&#x7684;&#x53D8;&#x5316;&#x987A;&#x5E8F;&#xFF0C;&#x662F;&#x4E00;&#x4E2A;&#x5B57;&#x7B26;&#x4E32;&#x7684;&#x503C;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>return:</b>string</td>
    </tr>
  </tbody>
</table>
























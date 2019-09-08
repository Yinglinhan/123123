# Visual 视觉

**style:**MotionStyle

React DOM的一个属性，用来给Frame标签设置一些没有预设的CSS样式。

```jsx
<Frame style={{ mixBlendMode: "difference" }}  />
```



**visible:**boolean

定义Frame标签是否可见，和opacity属性不一样，这个属性不能用来做动画效果。默认的值是true，这也是CSS的原生属性。

```jsx
<Frame visible={false} />
```

\*\*\*\*

**opacity:**number \| MotionValue&lt;number&gt;

通过设置opacity属性，你可以让元素看起来是半透明或者完全看不见，经常会被用来实现出现和隐藏的动画效果。默认值是1。

```jsx
<Frame opacity={0.5} />
```



**background:**Background \| null

为Frame标签设置背景。支持的值类型包括，颜色的字符串，颜色对象以及图像的src。默认的颜色是半透明的蓝色。当你在Frame标签上设置了image属性，那么background属性会被覆盖，不会生效。如果想要同时使用背景图片和背景色，那么背景色要用backgroundColor属性来设置。

```jsx
<Frame background="#09F"/>
<Frame background={Color({r: 255, g: 0, b: 102})} />
<Frame background={{ alpha: 1, angle: 75, start: "#09F", end: "#F09"}} />
<Frame background={{ src: "https://example.com/logo.png"}} />
```



**backgroundColor:**string \| Color

用来设置Frame标签的背景色，支持使用颜色的字符串和对象。这个属性可以和image属性一起使用。

```jsx
<Frame backgroundColor="#09F"/>
<Frame backgroundColor={Color({r: 255, g: 0, b: 102})} />
```



**image:**string

给Frame标签设置一个背景图片，想要的话也可以用url\( ' ' \)来包裹图片地址。

```jsx
<Frame image="https://source.unsplash.com/random" />
```



**color:**string \| MotionValue&lt;string&gt;

给Frame标签包裹的文字设置颜色。默认是black。

```jsx
<Frame color="#09F" />
```



**border:**string \| MotionValue&lt;string&gt;

用来设置CSS的边框属性，需要使用符合属性，分别是宽度、类型、颜色，默认值是none。

```jsx
<Frame border="1px solid #09F" />
```



**radius**:number \| string \| MotionValue&lt;number \| string&gt;

设置圆角，可以用像素或者是百分比。默认是0。

```jsx
// Radius with pixels
<Frame radius={10} />

// Radius with percentages
<Frame radius="50%" />
```



**shadow:**sting \| MotionValue&lt; string &gt;

设置投影效果

```jsx
<Frame shadow="10px 5px 5px black" />
```



**overflow:**"visible" \| "hidden"

设置CSS中的overflow属性，默认是"visible"。

```jsx
<Frame overflow="hidden" />
```
















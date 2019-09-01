# Hooks & 传递数据

你现在有一个函数组件Slider，但是现在它还没有什么用处。它只是简单地可以像一个普通的滑块一样可以左右拖动而已，不过如果我们可以让它去控制点什么，那么就不一样了。

让我们来实现让一张图片的缩放大小能够被这个滑块控制的效果。要实现这个效果。你需要新增加一个Frame标签用来显示图片，同时利用React Hooks的功能来管理这张图片的缩放（scale）的状态。

Hooks是新的新版本的React（16.8版本及以上）中的新功能，它能让你在函数组件中轻松得管理组件的状态数据以及实现生命周期函数的调用。

![](../../.gitbook/assets/06705a43-4439-46bf-be45-0f801eec3bdf.png)



### 创建一个有图片的标签

一开始创建的图片会显示在滑块组件的下方，这没有关系，我们在后面做一个简单地调整就好了。

 - 打开index.tsx文件

 - 在SliderApp组件的内部，同时在Slider组件的上方创建一个Frame标签，并且添加image属性来实现图片显示在这个Frame标签中

这个显示图片的Frame标签会显示再画面的中间，同时它的缩放（scale）被设置为25%。它本身的尺寸宽和高都是480px像素，因为我们给它设置了size属性的值为480。

```jsx
<Frame
  name={"SliderApp"}
  ...
>
  <Frame
    name={"Image"}
    scale={0.25}
    center
    size={480}
    image={"https://static.framer.com/api/bg.jpg"}
  />
  <Slider />
</Frame>

```





### 添加和应用Scale Hook

React提供了一些内置的Hook功能比如像useStates。这就是你用来更新数据并且在组件每次重新渲染时给scale这个变量重新赋值的方法。

useState这个方法执行之后会返回一对数据：当前的数据和一个能改变这个数据的函数。同时在执行时可以传入一个初始值。当你执行useState时，可以利用数组的解构赋值，可以直接把数据的变量和更新函数传递到相对应的变量里面。

在App组件里面的最上方，用scale这个变量来保存Hook返回的数据，同时用scaleState这个变量来保存用来修改scale这个数据的函数。同时给scale这个数据一个初始值0.5。然后把这个scale变量赋值到用来显示图片的Frame标签中的scale属性上。

现在Slider组件还不能控制图片。你还需要去给这个Slider组件添加一些属性。

```jsx
export function App() {
  const [scale, setScale] = React.useState(0.5);
  return (
    <Frame
      name={"SliderApp"}
      ...
    >
      <Frame
        name={"Image"}
        scale={scale}
        ...
      />
      <Slider />
    </Frame>
  );
}
```



### 设置Slider组件的属性

为了能实现想要的功能，你的Slider组件需要设置一些默认值，设定一个最大值和最小值，这样当你拖动滑块时就会自动更新scale变量里的数据。

你需要给Slider组件把scale变量作为value属性的默认值传进去。同时添加一个min属性一个max属性，这样可以让输出的值控制在0.25到0.75的范围内，还要添加一个onChange属性，然后给这个赋值一个函数，这个函数有一个形参newValue。在这个函数内，调用你的setScale方法，并且把newValue这个形参传进去。

这些属性用来初始化你的Slider组件中的一些数据以及作为图片的Frame标签的缩放值。你可能会看到一个错误提示，说这些属性不存在与你的Slider组件中，所以你还需要在Slider组件中应用它们。

```jsx
<Frame
  name={"SliderApp"}
  ...
>
  <Frame
    name={"Image"}
    ...
  />
  <Slider
    value={scale}
    min={0.25}
    max={0.75}
    onChange={function(newValue) {
      setScale(newValue)
    }}
  />
</Frame>
```



### 使用Slider组件的属性

为了让你能够使用在App组件中通过Sldier组件标签传递的数据，你需要在Slider组件内部添加一些内容。

 - 打开Slider.tsx 文件

 - 在顶部Slider函数中添加一个有属性的对象作为它的参数，利用对象的解构赋值

 - 修改一下position这个变量的值，用上value这个变量

给作为参数的对象的几个属性设置默认值，value设置为0，min也为0，max为1。这样设置是为了当这个组件没有被正确地传入数据时，滑块会获取value为0的值，默认出现在轨道的最左侧的位置，当滑块被拖到左右侧的时候，value的值就相应地变成最大值1。

对象中的onChange属性没有一个默认值。在使用前你需要确认是否有相应的函数被传递进来，以防止不必要的调用和错误。

现在你已经有了一个默认的value值，用它先把useMotionValue的初始值变更一下，然后用position这个比那辆来设置一下滑块和进度条。这里就是用Slider组件的宽度乘以value的值。

所有的错误都消失了！wow！在接下来的几步，你就会用到传进来的onChange属性来修改scale的数据。

```jsx
export function Slider({
  min = 0,
  max = 1,
  value = 0,
  onChange
}) {
  const position = useMotionValue(value * 130);
  return (
    <Frame
      name={"Rail"}
      ...
    >
      <Frame
        name={"Fill"}
        ...
      />
      <Frame
        name={"Knob"}
        ...
      />
    </Frame>
  );
}
```



### 引入useTransform这个功能模块

在使用onChange属性中的函数来更新Sldier组件之前，需要去引入一个工具用来转换MotionValue生成的保存在变量position里面的值，让它能够在min和max之间的范围内变化。

 - 在Slider.tsx文件中import语句中添加useTransform

现在你已经引入了useTransform功能了，让我们开始把它用起来。

```jsx
import * as React from "react"
import { Frame, useMotionValue, useTransform } from "framer"
```



### Transform & 更新数据

先创建一个变量newValue来储存你转换过的数据。使用useTranform功能时，你需要把position这个变量穿进去，它里面其实放的是MotionValu功能产生的值，然后要定义两个数组，一个是输入数据的范围，一个是输出数据的范围。

输入的范围数组用\[0,130\]表示你整个滑块的限制滑动的区间。输出范围数组用的是min和max，表示会输出一个值在min和max之间，输入和输出是一一映射的。

当你使用了useTransform这个方法之后，你其实就是订阅了MotionValue产生的数据，当position里面的值发生变化时，就会产生一个在min和max范围内的值返回到newValue变量中。

为了能够及时地把新产生的newValue传递给图像的Frame标签，要用利用滑块标签上的onDrag事件。onDrag属性每当你拖动滑块时，会触发作为其属性的一系列代码，要记得检查下在代码中用if语句检查下onChange这个变量是否有值，只有当onChange有值时，才会往下执行，这样能帮你避免很多不必要的错误。

你现在能够放心地执行onChange函数了，同时用newValue.ger\(\)给它传一个值。因为newValue是现在保存的是一个特殊的对象，你需要使用get方法才能获取当前的数据。接着，通过一系列传递，就会把取到的这个值传给setScale方法，也就是在index.tsx文件中用来控制图像Frame标签缩放变量scale的方法，这个方法就是在index.tsx文件中用onChange属性传递到Slider标签的组件中的。

看!你拖动滑块的时候，图片的缩放会跟着变化了！

```jsx
export function Slider({
  min = 0,
  max = 1,
  value = 0,
  onChange
}) {
  const position = useMotionValue(value * 130);
  const newValue = useTransform(position,[0,130],[min,max]);
  return (
    <Frame
      name={"Rail"}
      ...
    >
      <Frame
        name={"Fill"}
        ...
      />
      <Frame
        name={"Knob"}
        ...
        onDrag={function() {
          if (onChange) onChange(newValue.get());
        }}
      />
   </Frame>
  );
}
```






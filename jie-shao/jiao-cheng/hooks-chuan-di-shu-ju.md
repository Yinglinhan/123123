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
























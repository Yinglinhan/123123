# 完成

现在你的Silder组件已经可以操作了，让我们把它做得更好一点。

你要给整个图片添加一个遮罩mask，然后把整个图片移动到Slider组件的上方。当你的图片被放大缩小时，你会想要这个图片是可以拖动的，因为这样你才能选择具体哪一块区域被显示在遮罩的区域中。

让我们打开index.tsx文件做一点最后的修改吧。

![](../../.gitbook/assets/1197cee1-b929-489c-a213-516258c8a4cc.png)



### 添加图片的遮罩

为了给图片一个遮罩，你需要用一个新的Frame标签包裹现有的用来展示图片的Frame标签。

作为遮罩的Frame标签设置的尺寸是120px，同时在y轴方向上偏移-100px，也就是向上移动100px的距离。这样就让整个遮罩Frame和Slider组件分开了。要让遮罩的Frame起作用，还要设置一下它的overflow这个属性的值为hidden，这样就能保证超出遮罩范围的图片不会被显示出来。

这样的话遮罩就起作用了，但是现在还是有个问题，当你通过滑块去缩放图片的时候，你能看到的只有图片中心位置的内容。让我们来做一下调整，确保你可以看到任何一块你想看到的区域。

```jsx
<Frame
  name={"Mask"}
  size={120}
  center
  y={"-100px"}
  overflow={"hidden"}
  radius={"50%"}
>
  <Frame
    name={"Image"}
    ...
  />
</Frame>
```



### 使图片能够被拖动

要让图片能够拖动，需要给图片的Frame设置一个drag属性。这就像你在Slider组件中给滑块设置拖动时是一样的，同时要设置一下dragElastic属性的值为0，还有就是dragMomentum的值为false。

你现在可以随意拖动图片了，但是现在还有最后一个问题，就是图片会被拖出遮罩的显示范围，这不是我们想要的，所以我们还要再做最后一点调整。

```jsx
<Frame
  name={"Image"}
  ...
  drag
  dragElastic={0}
  dragMomentum={false}
/>
```



### 设置图片的限制拖动范围

要想让图片只在遮罩的显示区域范围内拖动，你需要给图片的Frame标签设置一个dragConstaints的属性。

因为图片的大小会随着滑块的拖拽改变，那么我们显示图片拖动的区域就要和scale的这个值关联起来，让它们可以保持联动，每一次拖动滑块的时候，限制区域的大小就会重新计算。所以我们要定义一个变量constraint，来利用scale计算出相应的限制区域。

因为设置限制区域的dragConstraints这个属性是要设置top，bottom，left和right四个方向的数值，也就是设置分别向上向下向左向右拖动多少距离。constraint这个变量里面的计算方式是这样的，480\*scale是实际这个图片呈现出来的尺寸，减去120是就是减去遮罩的宽度，然后再除以2，就是往每个方向可以拖动的距离了。然后再把这个constraint变量赋值到dragConstraint属性的四个方向里面，赋值的时候要注意，top和left方向需要在前面加一个负号。

这样，不管你的图片是缩放成多大，你可以拖动随意拖动图片但是不会出现超出遮罩范围的情况。

```jsx
export function App() {
  const [scale, setScale] = React.useState(0.5);
  const constraint = (480 * scale - 120) / 2;
  return (
    <Frame name={"SliderApp"} ... >
      <Frame name={"Mask"} ... >
        <Frame
          name={"Image"}
          ...
          drag
          dragElastic={0}
          dragMomentum={false}
          dragConstraints={{
            top: -constraint,
            bottom: constraint,
            left: -constraint,
            right: constraint
          }}
        />
      </Frame>
      <Slider ... />
    </Frame>
  );
}
```


























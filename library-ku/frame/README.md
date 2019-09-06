---
description: 最基本的容器，是用来布局，实现样式和动画以及事件的。
---

# Frame

Frame组件本质上是一个div标签，但是有一个额外的属性和默认的一些设置可以让你实现更高效的设置。Frame层面上的一些属性会给div这个标签设置一些默认的样式，但是你随时都可以通过自定义style属性来改变这些默认的样式。Frames允许你做下面这些事情：

 - 设置尺寸和添加布局限制

 - 水平对齐和垂直对齐

 - 修改背景颜色或者背景图片

 - 在几个状态之间实现动画

 - 给桌面版本和移动版本的页面添加点击事件

 - 添加一些高级的功能比如说拖拽

 - 实现更多手势操作的功能

> 如果你想要看老的v0.10的或者其他早一点的版本的文档 可以参看这个链接[ Frame API](https://www.framer.com/api/frame-deprecated/).

```jsx
import * as React from "react"
import { Frame } from "framer"

export function MyComponent() {
  return (
    <Frame size={300} center>
      Hello
    </Frame>
  )
}
```



### Performance 性能

为了能让你的原型有更好的动画性能表现，尽量只去通过animate属性使用transform和opacity使元素发生变化，因为它们有GPU加速。通过这样，你甚至可以在移动设备上同时驱动上百个图层同时发生变化。

```jsx
// GPU accelerated (fast)
<Frame initial={{scale: 1}} animate={{scale: 2}} />

// CPU drawing (slower)
<Frame initial={{size: 200}} animate={{size: 400}} />
```



### Integration 融合

Frame组件能和DOM元素完美的配合使用，主要因为它本身就是一个DOM元素（div）。你可以使用任何的属性的组合来设置它比如说size、width、height，top、right、bottom、left和center。

这里是一个稍微有点复杂的动态布局的Frame元素，使用了可变的尺寸，但是位置是相对固定的一个方式，放在了一个div的元素里面。

```jsx
export function MyComponent(props) {
  return (
    <div
      style={{
        width: "100%",
        height: "100%",
        background: "rgba(255, 0, 0, .5)",
      }}
    >
      <Frame size="40%" center="x" top={50}>
        Hello
      </Frame>
    </div>
  )
}
```



### Text Centering 文字居中

如果你的Frame元素只包裹了文字内容你，那么文字会被默认居中。你可以通过给文字包一层span标签来避免这个自动居中的效果。

```jsx
/ Text contents will be centered
<Frame>Hello</Frame>

// Text contents will not be centered
<Frame><span>Hello</span></Frame>
```



### Event Handling 事件绑定

事件冒泡在React的行为方式和DOM事件是类似的。你可以通过preventDefault\(\)取消事件的默认行为以及通过stopPropagation来组织事件冒泡。



### DOM

Frame组件是基于HTML的div的，所以它可以用小驼峰式写法来使用会继承DOM的属性

 - [Standard `HTMLDivElement` DOM properties](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)

 - [Supported `React.Element` DOM props](https://reactjs.org/docs/dom-elements.html#all-supported-html-attributes)

```jsx
// CSS classes
<Frame className="pretty" />

// DOM events
<Frame onClick={onClick} />
<Frame onMouseOut={onMouseOut} />
<Frame onTouchUp={onTouchUp} />
```














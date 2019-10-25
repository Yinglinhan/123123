# Adding Controls

当你需要在你的代码组件中使用Property Control功能时，先要在代码上方引入addPropertyControls 以及ControlType，从framer库中引入

在定义完组件后，调用addPropertyControl方法，并且传入两个参数。第一个参数是你组件的名称，第二个参数是一个对象，这个对象包含了你要控制的属性，属性的值的类型有好几种，并且都在这个版块中罗列出来了。

Property Controls只会影响canvas（设计面板）上的组件，因此你需要去设置一下组件的defaultProps，即默认的参数的值，这样可以防止你在写代码的时候报错，或者别人在使用你的组件的时候产生未知的错误。

在这个案例中，我们给组件的text属性添加了一个Property Control。当你在画板使用这个组件的时候，在属性面板就会有一个可以修改text属性值的地方。

```jsx
import * as React from "react"
import {
  Frame,
  addPropertyControls,
  ControlType,
} from "framer"

export function MyComponent(props) {
  return <Frame>{props.text}</Frame>
}

MyComponent.defaultProps = {
  text: "Hello World!",
}

addPropertyControls(MyComponent, {
  text: { type: ControlType.String, title: "Hello World" },
})
```




# String

**Control.String**

这个类型是表示一个纯文本的值。使用的时候可以配合使用placeholder属性，用来默认显示一些字符。如果你同时设置了obscured这个属性为true，那么输入的字符会被显示为点点点，这个适合用来在使用密码的一些场景。

```jsx
export function MyComponent(props) {
  return <Frame size={"100%"}>{props.title}</Frame>
}

addPropertyControls(MyComponent, {
  title: {
    type: ControlType.String,
    defaultValue: "Framer X",
    placeholder: "Type something…",
    obscured:true
  },
}
```


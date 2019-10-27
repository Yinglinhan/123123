# Color

**ControlType.Color**

一种代表颜色的类型，具体的类型其实是字符串，它是用HEX \( “\#fff” \) 或者 HSL \( hsla\(203, 87%, 50%, 0.5\) \)这两种书写方式写的颜色值，具体是哪一种写法，取决于该颜色是否有透明度。

```jsx
function MyComponent(props) {
  return <Frame background={props.background} size={"100%"} />
}

addPropertyControls(MyComponent, {
  background: {
    type: ControlType.Color,
    defaultValue: "#fff",
  },
})
```




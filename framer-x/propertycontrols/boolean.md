# Boolean

**ControlType.Boolean**

这是一个会在属性面板上显示on/off选项的类型。相关的属性值为true或false，具体是哪个值和选项的状态相关。有一个可选的属性defaultValue，默认设置时true。你可以通过enableTitle和disabledTitle属性来设置在控制面板上选项显示的文字。

```jsx
export function MyComponent(props) {
  return <Frame size={"100%"}>{props.showText ? "Hello World" : null}</Frame>
}

addPropertyControls(MyComponent, {
  showText: {
    type: ControlType.Boolean,
    title: "Show Text",
    defaultValue: true,
    enabledTitle: "On",
    disabledTitle: "Off",
  },
})
```




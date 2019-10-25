# Hiding Controls

在属性面板中的某个属性设置面板可以通过hidden方法进行隐藏。每个属性都可以设置一个hidden的方法，这个方法返回一个boolean值，如果是true属性影藏，返回是false，属性显示。在这个案例中，我们通过和另一个属性值（toggle）的联动来实现了text属性的隐藏。

你可以通过点击Toggle的开关，来决定是否显示和隐藏text属性的设置栏。

```jsx
export function MyComponent(props) {
  return <div>{props.text}</div>
}

MyComponent.defaultProps = {
  text: "Hello World!",
  toggle: true,
}

addPropertyControls(MyComponent, {
  toggle: {
    type: ControlType.Boolean,
    title: "Toggle",
    enabledTitle: "Show",
    disabledTitle: "Hide",
  },
  text: {
    type: ControlType.String,
    title: "Text",
    hidden(props) {
      return props.toggle === false
    },
  },
})
```


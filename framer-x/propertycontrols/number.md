# Number

**ControlType.Number**

这个类型控制是使用数字类型的值。使用的时候要配合一系列的其他属性设置，来实现更具体的数据设置，如果设置了displayStepper，操作面板会出现一个加减控制器，而不是默认的拖动操作杆。

```jsx
export function MyComponent(props) {
  return <Frame rotateZ={props.rotation} size={"100%"}>{rotation}</Frame>
}

addPropertyControls(MyComponent, {
  rotation: {
    type: ControlType.Number,
    defaultValue: 0,
    min: 0,
    max: 360,
    unit: "deg",
    step: 0.1,
    displayStepper: true,
  },
})
```


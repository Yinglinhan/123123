# Enum

**ControlType.Enum**

这个类型控制可表示一系列可选项。这个些数据的值必须是原始值并且不能重复。被选的选项会被传递作为对应的值。这个类型控制会呈现出一个下拉列表的空间可供用户使用，用户可选择其中一个选项。

```jsx
export function MyComponent(props) {
  const value = props.value || "a"
  const colors = { a: "red", b: "green", c: "blue" }
  return <Frame background={colors[value]} size={"100%"}>{value}</Frame>
}

addPropertyControls(MyComponent, {
  value: {
    type: ControlType.Enum,
    defaultValue: "a",
    options: ["a", "b", "c"],
    optionTitles: ["Option A", "Option B", "Option C"],
  },
})
```


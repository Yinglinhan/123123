# SegmentedEnum

**ControlType.SegmentedEnum**

已经被废弃，建议使用ControlType.Enum这个类型

```jsx
export function MyComponent(props) {
  const value = props.value || "a"
  const colors = { a: "red", b: "green", c: "blue" }
  return <Frame background={colors[value]} size={"100%"}>{value}</Frame>
}

addPropertyControls(MyComponent, {
  value: {
    type: ControlType.SegmentedEnum,
    defaultValue: "a",
    options: ["a", "b", "c"],
    optionTitles: ["A", "B", "C"],
  },
})
```


# Array

**ControlType.Array**

一种实现类型控制中实现一个数组中可有多种类型的类型，它的数组类型。这种类型会在属性面板中可添加的选项，可以添加更多自己想要的字段。同时可以通过propertyControl属性来设定数组中可添加的类型。

如果在propertyControl属性中设置了ControlType.ComponentInstance这个属性，那么相关组件的Frame在画板中可以和其他的画板进行链接的操作。

```jsx
export function MyComponent(props) {
  const frames = props.images.map(image => <Frame image={image} width={"1fr"} height={"1fr"} />)
  return <Stack size={"100%"}>{frames}</Stack>
}

addPropertyControls(MyComponent, {
  images: {
    type: ControlType.Array,
    propertyControl: {
      type: ControlType.Image
    }
    // Allow up to five items
  maxCount: 5,
  },
})

addPropertyControls(MyComponent, {
  children: {
    type: ControlType.Array,
    propertyControl: {
      type: ControlType.ComponentInstance
    },
    maxCount: 5,
  },
})
```


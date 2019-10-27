# ComponentInstance

**ControlType.ComponentInstance**

这个类型是表示一个画板上的其他组件，也包括作为组件参数的React节点。使用了这个类型控制之后，该组件上会出现可链接的控件，可以链接到其他的Frame。链接之后的Frame也会出现在属性控制面板的菜单中。组件的引用会被作为一个属性，一般来说，会在组件中用children这个属性来接受这些被链接的组件。

多个组件一起被链接时，需要结合使用ComponentInstance类型和ControlType.Array类型。

```jsx
export function MyComponent(props) {
  return <Stack size={"100%"}>{props.children}</Stack>
}

addPropertyControls(MyComponent, {
  children: {
    type: ControlType.ComponentInstance,
  },
})
```


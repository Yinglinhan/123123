# Image

**ControlType.Image**

这个类型控制适用于用户要选择一个图片资源。被选择的图片地址会被传递到数组中的prop作为其中一个数。在面板上会出现一个选择器，让用户可以选择图片。被选择的图片的地址会被传到组件中去。

```jsx
function MyComponent(props) {
  return <Frame image={props.image} size={"100%"} />
}

addPropertyControls(MyComponent, {
  image: {
    type: ControlType.Image,
  }
})
```


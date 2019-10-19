# Functions

RenderTarget.**current\(\)**: RenderTarget

返回一个当前环境的对象，这样组件可以根据一些判断再做一些想要进行的处理

```jsx
function App() {
  if (RenderTarget.current() === RenderTarget.thumbnail) {
    return <PreviewIcon />
  }
  return <Frame>...</Frame>
}
```

| returns: RenderTarget |
| :--- |




RenderTarget.**hasRestrictions\(\)**: boolean

返回当前的环境对象是否设置了渲染表现限制，可以利用这一点，当前环境如果设置了渲染表现限制，那么可以通过一些方式去避免在当前环境去进行大量的渲染，而用一些占位组件去代替。

```jsx
function App() {
  if (RenderTarget.hasRestrictions()) {
    return <SomePlaceholder />
  }
  return <RichPreviewContent />
}
```

| returns: boolean |
| :--- |



# Properties

**RenderTarget.canvas**

下面的案例就是表示只有当当前环境是canvas时渲染CanvasComponent这个组件

```jsx
function App() {
  if (RenderTarget.current() === RenderTarget.canvas) {
    return <CanvasComponent />
  }
  return <DefaultComponent />
}
```



**RenderTarget.export**

当环境为导出时，才渲染ExportComponent这个组件

```jsx
function App() {
  if (RenderTarget.current() === RenderTarget.export) {
    return <ExportComponent />
  }
  return <DefaultComponent />
}
```



**RenderTarget.preview**

组件会在预览窗口渲染出来

```jsx
function App() {
  React.useEffect(() => {
    if (RenderTarget.current() === RenderTarget.preview) {
      // Do something in preview.
    }
  })
  return <DefaultComponent />
}
```



**RenderTarget.thumbnail**

组件会被渲染成缩略图，比如在组件的列表窗口中

```jsx
function App() {
  if (RenderTarget.current() === RenderTarget.thumbnail) {
    return <Thumbnail />
  }
  return <DefaultComponent />
}
```




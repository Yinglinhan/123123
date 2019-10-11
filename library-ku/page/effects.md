# Effects

Page组件定义了很多页面切换的动画效果，你可以选择其中一个或者自己再重新自定义一个。

**None**

默认的动画效果，没有什么特别的效果。

```jsx
<Page defaultEffect={"none"} />
```



**Cube**

每个页面都成为一个3d盒子的一面，翻页时像一个3d盒子在翻转

```jsx
<Page defaultEffect={"cube"} />
```



**Cover Flow**

每个页面过度时有一个3D的透视效果

```jsx
<Page defaultEffect={"coverflow"} />
```



**Wheel**

页面切换时有很细微的透明度变化（我只看出这个变化）

```jsx
<Page defaultEffect={"wheel"} />
```



**Pile**

每个页面切换时会堆叠到当前页面的上面

```jsx
<Page defaultEffect={"pile"} />
```



**Custom  自定义**

**effect:** \(info: PageEffectInfo\) =&gt; PageEffectValues

你可以自定义每一页的动画过渡效果

这个函数会在每次页面进行切换时进行调用。它返回的是这个页面新的样式的设置。

```jsx
function scaleEffect() {
    const { normalizedOffset } = info
    return {
        scale: Math.max(0, 1 + Math.min(0, normalizedOffset * -1))
    }
}

return <Page effect={scaleEffect} />
```




















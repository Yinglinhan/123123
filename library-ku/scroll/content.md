# Content

**dragEnabled:** boolean

设置是否可以滚动，默认是true

```jsx
<Scroll dragEnabled={false} />
```



wheelEnabled: boolean

设置是否可以滑轮滚动，默认是true

```jsx
<Scroll wheelEnabled={false} />
```



**direction:**"horizontal" \| "vertical" \| "both" \| "locked"

设置可滚动的方向。默认是垂直滚动即"vertical"，如果设置"both"即水平和垂直方向都可滚动。

"locked" 是当你一开始滚动是往哪个方向，在未放开鼠标或者手指之前就只能一直在此方向滚动。

```jsx
// Horizontal
<Scroll direction="horizontal" />

// Vertical
<Scroll direction="vertical" />

// Locked
<Scroll direction="locked" />

// Both directions
<Scroll direction="both" />
```



**contentOffsetX:** MotionValue&lt;number&gt; \| number

组件初始状态下的Y轴滚动偏移量，默认是0。

```jsx
<Scroll contentOffsetX={20} />
```



**contentOffsetY:** MotionValue&lt;number&gt; \| number

组件初始状态下的X轴滚动偏移量，默认是0。

```jsx
<Scroll contentOffsetY={20} />
```



**scrollAnimate:** FrameProps\["animate"\]

给滚动效果设置自定义的控制

```jsx
const controls = useAnimation()
controls.start({ y: -50 })
<Scroll scrollAnimate={controls} />
```










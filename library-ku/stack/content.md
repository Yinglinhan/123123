# Content

**direction:** StackDirection

设置内部元素的排布方向，"vertical'或者"horizontal"。默认是"vertical"。

```jsx
// Vertical
<Stack direction="vertical" />

// Horizontal
<Stack direction="horizontal" />
```



**gap:** number

子元素之间的间隔，默认是10。

```jsx
<Stack gap={120} />
```



**alignment:** StackAlignment

设置内部元素布局的在交叉轴上的对齐方式，"start". "end" 或者"center", 默认是center。这里可以参考flex布局中的align-items属性

```jsx
<Stack alignment="end" />
```



**distribution:** StackDistribution

定义内部元素的分布方式。默认是"space-around"。

 - "start" --- 靠容易左边对齐

 - "center" --- 布局在容器的中间

 - "end" --- 靠容器右边对齐

 - "space-around" --- 两端元素到容器边的距离等于中间元素之间的间隔一半

 - "space-between" --- 两端对齐，中间的元素间隔平分多余的空间

 - "space-evently" --- 所有元素的间距相等

```jsx
// Default
<Stack distribution="space-around" />

// Start
<Stack distribution="start" />

// Center
<Stack distribution="center" />

// End
<Stack distribution="end" />

// Space Between
<Stack distribution="space-between" />

// Space Around
<Stack distribution="space-around" />

// Space Evenly
<Stack distribution="space-evenly" />
```


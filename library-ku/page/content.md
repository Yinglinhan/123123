# Content

**alignment:** PageAlignment

设置内部的页面的和组件容器的对齐方式，可以是”start“，”center“或者”end“。默认是设置”start“。

```jsx
<Page alignment="center" />
```



**animateCurrentPageUpdate:** boolean  **BETA**

决定组件是否在页面改变的时候产生动画效果。默认是true

```jsx
<Page animateCurrentPageUpdate={false} />
```



**contentWidth:** PageContentDimension \| number

控制组件内的页面的宽度，可以设定”auto“或者”stretch“或者一个具体的数值。默认是设置为"stretch"

```jsx
<Page contentWidth="auto" />
```



**currentPage:** number

当前页面的索引。默认是0

```jsx
<Page currentPage={5} />
```



**defaultEffect:** PageEffect

选择一个预定义好的切换的效果，"none", "cube", "coverflow", "wheel", 或者 "pile"。默认设置是"none"

```jsx
<Page defaultEffect={"coverflow"} />
```



**gap:** number

用来内部页面之间的间隔，默认是10，不能是负数

```jsx
<Page gap={0} />
```



**momentum:** boolean

当启动这个设置的时候，能一次翻过多个页面

```jsx
<Page momentum />
```


















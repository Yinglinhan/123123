# Layout 布局

Frame标签的布局规则和一般的CSS是类似的，当父元素（Frame或者div）尺寸变化时会重新计算布局。你可以选择使用快捷写法比如center来让元素快速居中。

Frame标签默认的position属性的值是设置为absolute。你可以自行通过position属性设置其他的值。当你把一个Frame标签添加到某个组件中（比如Stack），Frame的的position属性会自动被改写为relative。

当标签的布局属性相互之间是不兼容，他们的覆盖规则是和CSS保持一致的。x和y的属性是作为transform的变化总是会起作用的，他们会在一般的布局属性设置基础上生效。

* `height` &gt; `top`, `bottom` &gt; `center=“y”`
* `width` &gt; `left`, `right` &gt; `center=“x”`

```jsx
// Right is ignored
<Frame width={100} left={100} right={100} />

// Center is ignored
<Frame left={0} right={100} center="x" />
```





**width:**number \| string \| MotionValue&lt; number \| string&gt;

设置CSS的width属性。默认是200。接受任意CSS支持的值的类型（包括px，percentages，keywords以及其他）

```jsx
// Pixels
<Frame width={100} />

// Percentages
<Frame width={"100%"} />
```



**height**: number \| string \| MotionValue&lt;number \| string&gt;

设置CSS的height属性，默认值是200。

```jsx
// Pixels
<Frame height={100} />

// Percentages
<Frame height={"100%"} />
```





**size**:number \| string

可以同时设置width和height属性的快捷属性。

```jsx
<Frame size={100} />
```



**top**:number \| string \| MotionValue&lt; number \| string&gt;

设置到父元素顶部的距离，默认是0.

父元素是指根元素（即整个画面）或者层级最近的position属性设置为非static值的元素

```jsx
<Frame top={100} />
```



**right**:number \| string \| MotionValue&lt; number \| string&gt;

设置到父元素右边的距离，默认是0.

父元素是指根元素（即整个画面）或者层级最近的position属性设置为非static值的元素

```jsx
<Frame right={100} />
```



**left**: number \| string \| MotionValue&lt;number \| string&gt;

设置到父元素左边的距离，默认是0.

父元素是指根元素（即整个画面）或者层级最近的position属性设置为非static值的元素

```jsx
<Frame left={100} />
```



**bottom**:number \| string \| MotionValue&lt;number \| string&gt;

设置到父元素底部的距离，默认是0.

父元素是指根元素（即整个画面）或者层级最近的position属性设置为非static值的元素

```jsx
<Frame bottom={100} />
```



**center**:boolean \| " X " \| " Y "

让Frame标签快速居中的

```jsx
// Center
<Frame center />

// Center horizontally
<Frame center="x" />

// Center vertically
<Frame center="y" />
```



**position:**string

设置标签的position属性。默认设置是“absolute”。

```jsx
<Frame position={"relative"} />
```








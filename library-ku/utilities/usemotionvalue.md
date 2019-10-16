# useMotionValue

**useMotionValue\(**initial**\)**: MotionValue**&lt;T&gt;**

这个会返回一个MotionValue对象，用来追踪元素某个属性的值的变化

你可以把创建好的MotionValue对象赋值给相应的元素的和样式相关的属性上，用来追踪他们，同时再配合useTransform的方法，可以实现数据之间的联动。

```jsx
export function MyComponent() {
  const scale = useMotionValue(1)

  return <Frame scale={scale} />
}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>initial: T</p>
        <p>&#x521D;&#x59CB;&#x503C;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">returns: MotionValue&lt;T&gt;</td>
    </tr>
  </tbody>
</table>
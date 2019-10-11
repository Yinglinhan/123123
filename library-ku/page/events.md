# Events

**onChangePage\(currentIndex, previousIndex\):** void

当页面切换时会触发的一个回调函数

```jsx
<Page
    onChangePage={(current, previous) => {
        console.log(current, previous)
    }}
/>
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>currentIndex: number</p>
        <p>&#x5F53;&#x524D;&#x7684;&#x9875;&#x9762;&#x9875;&#x6570;</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>previousIndex: number</p>
        <p>&#x4E0B;&#x4E00;&#x4E2A;&#x9875;&#x9762;&#x7684;&#x9875;&#x6570;</p>
      </td>
    </tr>
  </tbody>
</table>




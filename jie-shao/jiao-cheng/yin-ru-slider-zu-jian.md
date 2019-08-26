# 引入 Slider 组件

当你创建了Slider组件，它能让你能直观地看到你的代码效果同时能够实时更新。想要在App中使用Slider组件，你必须先引入它。

当你引入了Slider，你在这部分内容结束后在页面预览中可以看到一个淡蓝色的方块，那说明你已经引入成功了。

### 引入Slider组件 

你必须给你的Slider确定一个名字，这样App组件才能正常使用它。这只要一行简单地引入代码就能办到。

 - 打开index.tsx 文件

 - 在顶部最后加一条引入Slider组件的语句，用相对路径的方式引入它

```jsx
import * as React from "react"
import { render } from "react-dom"
import { Frame } from "framer"
import { Slider } from "./Slider"
```



### 让Slider组件出现在页面中

现在你已经把Slider组件引入到你的Index.tsx文件中了，把之前的用来占位的显示logo的那个Frame标签替换成Sldier组件。

 - 删掉有logo图片的Frame标签

 - 把Sldier用标签的形式放到相同的位置

你现在应该能在页面效果中看到Slider组件了。太棒啦！现在还是默认的淡蓝色的Frame，虽然不是很好看，那让我们开始接着一点一点把Slider组件写出来。

```jsx
<Frame
  name={"SliderApp"}
  width={"100%"}
  height={"100%"}
  background={"#242424"}
>
  <Slider />
</Frame>
```


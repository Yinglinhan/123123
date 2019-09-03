# Stack

Stack标签能够帮助你使用Frame标签轻松地创建有弹性而且自动布局的排版。Stack标签是基于Frame标签的，也就是说所有能在Frame上用的属性都能在Stack标签上使用。在下面这个例子中，我们用Stack标签展示了一组Frame标签。注意下Stack标签是如何控制排版的。这非常容易使用：设置一下direction属性为“vertical”，你可以看一下Frame标签的排布是如何跟随者变化的。

[Open Example](https://codesandbox.io/s/o9y86o898q)

```jsx
import * as React from "react"
import { Frame, Stack } from "framer"

export function MyComponent() {
  return (
    <Stack size={150} gap={10} direction={"horizontal"}>
      <Frame size={40} background={"#fff"} radius={40} />
      <Frame size={40} background={"#fff"} radius={40} />
      <Frame size={40} background={"#fff"} radius={40} />
    </Stack>
  )
}
```


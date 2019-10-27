# File

**ControlType.File**

这个类型控制让用户可以选择一个文件地址。文件被选择后，文件地址会被传递到组件中作为一个属性的值。会在属性面板上出现一个文件选择的按钮，用户点击之后就可以选择自己要使用的视频，注意allowedFileTypes的设置，你只能选择设置中的有的扩展名文件类型。

```jsx
import * as React from "react"
import { Frame, addPropertyControls, ControlType } from "framer"

export function MyComponent(props) {
    return (
        <Frame size={"100%"}>
            <video
                style={{
                    objectFit: "contain",
                    width: props.width,
                    height: props.height,
                }}
                src={props.filepath}
                controls
            />
        </Frame>
    )
}

MyComponent.defaultProps = {
    width: 300,
    height: 200,
}

addPropertyControls(MyComponent, {
    filepath: {
        type: ControlType.File,
        allowedFileTypes: ["mov"],
    },
})
```


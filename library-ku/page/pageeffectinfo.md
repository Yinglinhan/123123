# PageEffectInfo

页面效果对象的具体信息。

**direction:** PageDirection

页面的滑动方向，"horizontal"或者"vertical"



**gap:** number

页面之间的间隔，单位是px



i**ndex:** number

当前页面的index，第一个页面是0，第二个页面是1，然后以此类推



**normalizedOffset:** number

页面的偏移数，举个例子，比如说每个页面是200px宽，我们当前在index为1的这个页面，那么index为0的页面的normalizedOffset就是-1



**offset:** number

页面偏移量，从容器的最左侧开始测量，单位是px



**pageCount**：number

总共页面数量



**size:** Size

页面的尺寸


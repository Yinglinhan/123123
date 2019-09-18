---
description: 这个名字是我自己意译的，直译过来不是这个意思
---

# Variants 动画状态组

通过variants这个属性可以更方便的管理你动画的不同状态。

**variants:** Variants

你可以自行定义一个对象，我这里把它也同样取名为variants，然后你在这个对象里面有两个属性，属性名分别就是两个不同的状态的参数。你可以通过animate属性来驱动你想要的那个状态的动画。

你可以在variants这个变量中定义某个状态的时候，同时设置一下transition这个参数，可以使用delayChildren和staggerChildren这个两个属性来实现子元素的分步动画效果。

你可以把定义好的variants这个变量运用到不同的Frame上，当你把它赋值给Frame的variants属性上时，你可以通过animate，initial，whileTap和whileHover等属性来驱动Frame去实现你想要的其中一种动画状态。

```jsx
const variants = {
  active: {
    backgroundColor: "#f00"
  },
  inactive: {
    backgroundColor: "#fff",
    transition: { duration: 2 }
  }
}

<Frame variants={variants} animate="active" />
```






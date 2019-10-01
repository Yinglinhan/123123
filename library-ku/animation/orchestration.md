# Orchestration

这个参数可以创建序列或者分步的动画效果。

**delay:** number

让动画推迟一定时间才开始，单位是秒。默认是0。

```jsx
const transition = {
  delay: 0.2
}
```



**delayChildren:** number

使用variants属性时，在里面设置这个delayChilren的属性，能使所有子元素的动画效果推迟开始。你也可以直接在Frame标签上加transition属性，并且在里面设置delayChildren。但是如果你使用variants这个属性来设置delayChildren，会显得更灵活一些。

```jsx
const container = {
  hidden: { opacity: 0 },
  show: {
    opacity: 1,
    transition: {
      delayChildren: 0.5
    }
  }
}

const item = {
  hidden: { opacity: 0 },
  show: { opacity: 1 }
}

return (
  <Frame
    variants={container}
    initial="hidden"
    animate="show"
  >
    <Frame variants={item} size={50} />
    <Frame variants={item} size={50} />
  </Frame>
)
```



**staggerChildren:** number

当使用variants属性来设置staggerChildren属性时，可以实现子元素动画的分布执行，单位是秒。

举个例子来说，当你设置的值是0.01，那么第二个会0.02秒之后执行，第三个就会在0.03秒之后，前后两者之间就会间隔0.01秒。

```jsx
const container = {
  hidden: { opacity: 0 },
  show: {
    opacity: 1,
    transition: {
      staggerChildren: 0.5
    }
  }
}

const item = {
  hidden: { opacity: 0 },
  show: { opacity: 1 }
}

return (
  <Frame
    variants={container}
    initial="hidden"
    animate="show"
  >
    <Frame variants={item} size={50} />
    <Frame variants={item} size={50} />
  </Frame>
)
```



**staggerDirection:**  1 \| -1

这是设置分步动画的顺序，是从前到后还是从后到前

值为1的时候是从前到后，值为-1是从后到前

```jsx
const container = {
  hidden: { opacity: 0 },
  show: {
    opacity: 1,
    transition: {
      staggerChildren: 2,
      staggerDirection: -1
    }
  }
}

const item = {
  hidden: { opacity: 0 },
  show: { opacity: 1 }
}

return (
  <Frame
    variants={container}
    initial="hidden"
    animate="show"
  >
    <Frame variants={item} size={50} />
    <Frame variants={item} size={50} />
  </Frame>
)
```



**when:** false \| "beforeChildren" \| "afterChildren" \| string

这是用来描述动画本身的过渡效果与子元素动画之间关系的一个属性。默认设置是false。

当使用variants属性时，如果设置''beforeChildren'，那么元素本身的动画会先于子元素动画开始，在元素过渡效果结束后，子元素的动画效果才会开始，"afterChildren"则是在子元素的动画结束后才会开始元素本身的过渡变化效果。

```jsx
const container = {
  hidden: {
    opacity: 0,
    transition: { when: "afterChildren" }
  }
}

const item = {
  hidden: {
    opacity: 0,
    transition: { duration: 2 }
  }
}

return (
  <Frame variants={container} animate="hidden">
    <Frame variants={item} size={50} />
    <Frame variants={item} size={50} />
  </Frame>
)
```








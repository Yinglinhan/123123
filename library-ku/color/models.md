# Models

## ColorMixModelType

Color对象中有不少方法，比如说Color.mix和Color.interpolate，都可以使用其中一种颜色对象模型来决定颜色如何混合。

```jsx
const newColor = Color.mix(Color("red"), Color("blue"), {model: ColorMixModelType.HSL})
```



### ColorMixModelType.HSL

HSL的色彩空间，不带透明度值

```jsx
const newColor = Color.mix(Color("red"), Color("blue"), {model: ColorMixModelType.HSL})
```



### ColorMixModelType.HSLA

HSL的色彩空间，带透明度值

```jsx
const newColor = Color.mix(Color("red"), Color("blue"), {model: ColorMixModelType.HSLA})
```



### ColorMixModelType.HUSL

使用HSLuv的色彩模式

```jsx
const newColor = Color.mix(Color("red"), Color("blue"), {model: ColorMixModelType.HUSL})
```



### ColorMixModelType.RGB

使用RGB色彩空间模型，不带透明度

```jsx
const newColor = Color.mix(Color("red"), Color("blue"), {model: ColorMixModelType.RGB})
```



### ColorMixModelType.RGBA

使用RGB色彩空间模型，带透明度

```jsx
const newColor = Color.mix(Color("red"), Color("blue"), {model: ColorMixModelType.RGBA})
```










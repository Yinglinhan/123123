# Render Target

## 组件当前的运行环境，一般来说是canvas或者是Framer X的preview

组件可以使用**RenderTarget.current\( \)**方法来检查当前的运行环境，然后实现不同的渲染方式。最典型的情况就是为了在canvas中环境中提高渲染表现，当组件渲染太慢时会用占位符暂时代替。**RenderTarget.hasRestrictions\(\)**方法用来查看是否对渲染过久时情况进行限制。














# 原生 html + css 练手页面

### 总结

- 发现 a 标签默认无法继承父级的字体和颜色

    - 参考 https://blog.csdn.net/weixin_43007680/article/details/82319434

    - 原因:
        - 层叠样式表的优先级中，浏览器为用户设置的样式优先于开发者设置的样式。而浏览器已经为用户设置了一个默认样式，所以a标签里的内容没有继承父级。

    - 解决方法:
      - 使用子代选择器
      - 加一句样式a{color:inherit; font:inherit;}

- 发现父元素的第一个子元素的上边距 margin-top 如果碰不到有效的 border 或者 padding，就会发生子元素的 margin 和父元素的 margin 重叠的问题。
- w3school中解释为: 当两个垂直外边距相遇时，它们将形成一个外边距，合并后的外边距的高度等于两个发生合并的外边距的高度中的较大者。
- 解决办法如下

    - 为父元素设置内边距 padding，来代替给子元素设置 margin-top
    - 为父元素设置边框 border
    - 为父元素设置 overflow: hidden
    - 其实父元素或子元素浮动了或定位了，也都不会有垂直 margin 重叠的问题，但是会影响布局，不推荐这么做

- 块级元素单行文本设置行高 line-height 就可以省去 height

- 子元素浮动导致父元素塌陷问题
  - 父元素开启 BFC 即可，overflow: hidden;

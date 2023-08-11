## 总体思路

制作一个渐变背景, ，渐变背景大致是一个光束，通过改变背景的 position 来实现加载的效果

## 值得关注的知识点

### linear-gradient

正常来说是从上到下做渐变的, 可以在第一个参数改变渐变的角度

### 当 background-position 为百分比的时候，position 的计算

计算公式为: (元素本身的长/宽 - 背景的长/宽) \* 百分比
(container width - image width) \* (position x%) = (x offset value)
(container height - image height) \* (position y%) = (y offset value)

容易知道如果背景图的长/宽比本身的长/宽大，且 position 的值也是正数, 那么背景就呈现向左移动的效果

### background 的 repeat 默认为 repeat

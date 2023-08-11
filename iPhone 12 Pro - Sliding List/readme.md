## 总体思路

通过滚动的百分比计算出某个元素的缩放和大小
在此例中总共有 7 个元素, 那么
在滚动的距离为(0 / 7)% ~ (1 / 7)%时, 第一个元素的缩放应从 0 变成 1，按百分比来算
在滚动的距离为(1 / 7)% ~ (2 / 7)%时, 第二个元素的缩放应从 0 变成 1，按百分比来算
以此类推
最大为 1, 最小为 0

## 值得关注的知识点

### mask-image

### scrollTop、scrollHeight、clientHeight

```javascript
// 判断滚动的比例0~1
// html.scrollHeight - html.clientHeight为总的可滚动高度
// 常用的判断是否滚动到底底部: Math.abs(element.scrollHeight - element.clientHeight - element.scrollTop) < 1; element换成HTMLElement
let scrolled = html.scrollTop / (html.scrollHeight - html.clientHeight);
```

### 通过改变元素上的变量的值来改变样式

```javascript
element.style.setProperty("--progress", progress);
```

```css
* {
  transform: scale(calc(1.8 - (0.8 * var(--progress)))) translateY(
      calc(-60px * (1 - var(--progress)))
    );
  opacity: var(--progress);
}
```

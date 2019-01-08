## 瀑布流新闻网站
预览地址
https://emilyhexue.github.io/waterfall-sinanews/index.html
### 懒加载原理
先将img标签中的src链接设为同一张图片（空白图片），将其真正的图片地址存储再img标签的自定义属性中（比如data-src）。当js监听到该图片元素进入可视窗口时，即将自定义属性中的地址存储到src属性中，达到懒加载的效果。

### 瀑布流原理
- 瀑布流布局要求要进行布置的元素等宽，然后计算元素的宽度与浏览器宽度之比，得到需要布置的列数。
- 创建一个数组，长度为列数，里面的值为已布置元素的总高度（最开始为0）
- 然后将未布置的元素依次布置到高度最小的那一列，就得到了瀑布流布局。

### 实现原理
- 获取数据
- 把数据拼装成dom节点放到页面上
- 使用瀑布流布局方式摆放dom位置

进入页面，监听 scroll 事件，执行` checkShow() `；` checkShow() `调用` isShow() `来判断元素是否进入可视窗口，当元素进入可视窗口执行` dosth() `函数；

` dosth() `通过ajax获取数据，当数据获取成功执行` render($nodes) `；

` renderData() `给每条数据都拼装成DOM，渲染到` #pic-ct `上，返回` $nodes `；

` render($nodes) ` 瀑布流实现。


# html5-learn

## <a>
### 锚点
+ <a>标签实现(当前页面内跳转 或 在跳转其他页面时跳转到其他页面指定位置),a标签实现锚点定位没有动画效果

```
<a href="指定位置id选择器"> </a>
或
<a href="url#dis"></a>

```
### base标签
+ 统一指定页面上所有的超链接的打开方式(默认_self 或 _blank)),此时不需要新开窗口的超链接单独设置target属性为_self即可
## <label>
+ 默认情况下，文字和输入框是没有关联的，即点击输入框旁边的文字，输入框是不会聚焦的，但是使用label标签包含文本，则可以使得文本和输入框关联
+ 方法1：label标签的for属性关联input标签的id即可（任意label包含的文字和任意id的input关联）
```
<label for="username">用户名:</label>
<input type="text" id="username" name="username" />
```
+ 方法2: 直接使用label标签包裹input标签和文字(不用使用for和id，仅限当前label包含的文字、input关联)
```
<label>
    用户名:<input type="text" name="username" />
</label>
```
## <datalist> 目前大多浏览器不支持
+ 实现类似下拉框 + 首字匹配
```
请输入车型：<input type="text" list="cars" />
<datalist id="cars"> 
    <option>奔驰</option>
    <option>宝马</option>
    <option>兰博基尼</option>
    <option>法拉利</option>
</datalist>
```

## css
### 字体
+ 英文字体不会影响中文，中文字体会影响英文，因此对于中英文混合的设置字体：英文字体在前，中文字体在后。
+ 英文字体单个单词不用加引号，中文字体需要加引号
### 文本缩进
```
# 首行缩进2个字
text-indent: 2em; 
```
### 颜色
+ rgb中让三种颜色值一样，就是灰色；值越小越黑，越大越白；
### 通配符选择器
+ 就是 * ，给页面所有标签设置样式
### 三大特性
#### 继承性
+ 子元素可以使用父元素的属性。只有以color-/text-/font-/line开头的属性才可以继承
+ a标签的文字颜色和下划线是不能继承的，即父元素不会影响到a标签的默认样式
+ h标签的文字大小是不能继承的
#### 层叠性
#### 优先级(权重)
+ id > class > 标签 > 通配符 > 继承 > 浏览器默认
### 背景
+ 背景图片background-image会覆盖背景颜色background-color(即z-index高于颜色)
+ 背景图片位置background-position: 水平方向 垂直方向;
+ 默认情况下背景图片会随着滚动条滚动而滚动；因此有了background-attachbackground-attachment属性，来关联背景图片和滚动条
#### background-image 和使用img标签(插入图片)两种实现背景图片的方式区别：
+ background-image不会占用父元素空间，而img作为子元素会占用父元素空间
+ 背景图片有定位属性，方便定位；而插入图片不方便定位
+ 插入图片的语义比背景图片的语义强，所以图片想要被搜索引擎收录，推荐使用插入图片
### 精灵图
css精灵图是一种图像合成技术，可以减少请求次数，降低服务器处理压力
#### 使用
就是将页面上所有图片组成一张大的图片，页面上使用图片时再定位到需要的图片进行显示即可

### 盒模型
HTML中所有的标签都是盒子
#### 内边距padding
边框和内容之间的距离
#### 外边距margin
标签和标签之间的距离
+ margin左右可以叠加，上下会重合（只有普通文档流中的块框的垂直外边距才会发生合并，行内框、浮动框或绝对定位之间的外边距不会合并）
### 三种宽度和高度
+ 内容的宽度和高度：width/height
+ 元素的宽度和高度：width/heigth + padding + border
+ 元素空间的宽度和高度： width/height + padding + border + margin
如果两个盒子是嵌套关系，那么设置了里面盒子的margin，则外面盒子也会有该margin的效果，可以通过给外面盒子添加border属性的方式，使外面盒子没有该margin效果

### 盒子居中和内容居中
#### text-align:center 和 margin: 0 auto的区别
+ 前者设置盒子中文字/图片水平居中
+ 后者设置盒子自己水平居中
#### 清除默认边距
+ 通配符会遍历页面所有的标签，性能不好
+ 推荐yui css reset 提供的css样式
#### 行高和字号
+ 默认文字在行高中是垂直居中的

### 浮动
#### 标准流
浏览器默认排版方式就是标准流(文档流)。 块级元素垂直排版，行内元素/行内块级元素水平排版。
#### 浮动流
+ 浮动流是一种“半脱离标准流”的排版方式
+ 浮动流只有一种水平排版方式(只有左对齐 和 右对齐)

# jQuery
## 属性选择器
+ ^value 以value开头； $value：以value结尾
+ *=value： 包含value的
## 子元素选择器
+ :first-child: 每一个标签中的第一个子元素
+ :nth-child(n): 每一个标签中的第几个子元素，n是从1开始的
+ :only-child: 仅有一个子元素的标签
## 表单属性
+ :checked
+ :selected
## 筛选
+ slice(start, end):  从开始到结尾，只传一个参数时，默认到最后
## 串联
+ add(): 
+ addSelf(): 拼接上自己
## 查找
+ children(): 通过父亲找孩子
+ find(): 通过祖先找后代
+ nextAll(): 后面所有的兄弟
+ siblings(): 前后所有的兄弟(不包含本身元素) 

+ .css(): 其实是添加style
+ .addclass(): 添加class
+  .toggleClass():  存在，则消失；不存在，则显示；

+ remove(): 移除元素及绑定的事件，返回一个对象，包含了移除的元素，以备后续使用，但事件不可再使用
+ detach(): 移除元素，返回一个对象，元素和绑定的事件都可以再使用

+ clone(): 仅仅克隆标签本身，不会克隆标签携带的事件
+ clone(true): 克隆本身，并且携带自己的事件
## CSS处理
+ 页面获取图片时需要注意，在加载完成之后才能获取到图片的信息
+ css(): 获取css样式
+ css({}): css样式赋值

如果本身绝对定位了，且父元素也是绝对定位，则本身是相对于父元素左上角进行定位的
+ offset():  根据别的元素位置定位新的元素的位置，该位置总是相对于浏览器左上角的位置
+ position(): 获取自身元素和父元素之间的位置，自身的margin也算自身元素
+ scrollTop(val):

+ innerHeight(): 实际宽高+padding 
+ innerWidth():
+ outerHeight(): 实际宽高 + padding + border
+ outerWidth():

### 三高
+ 可可视区域的高： $(window).height()
+ 文档总高度: $(document).height()
+ 滚动的高: $(window).scrollTop();兼容
## 事件
### 页面载入(Dom加载完毕和静态资源下载完毕)
```
# 页面上所有资源加载完毕
$(window).onload(function(){ })
```
+ ready(fn):
```
# 该写法基本不被使用了
$(document).ready(fn) 
```
+ $(fn): jquery中当所有dom加载完毕之后才执行fn
### 事件处理
 + bind()/unbind(event): 绑定事件和解除绑定事件
 + one()： 只绑定一次事件
 + &times; 关闭按钮的x号
### 事件委派
+ live(event, fn): 对于动态生成的标签，如普通的click有时候无法很好的绑定事件，这时，live方法会将事件绑定到每一个动态生成的标签上去
+ die(): 和live方法相反，取消绑定的事件
### 事件切换
+ hover()
+ toggle()
## 效果
+ slideDown() / slideUp(): 向下收起和向上收起动作
+ slideToggle() : 前两者的结合
+ fadeIn() / fadeOut(): 由无到有/由有到无
+ fadeTo(time, opacity): 淡出到指定不透明度
+ animate({}, time): 自定义动画  
## ajax请求
+ $.get(url, {params}, callback)
+ $.post(url, {params}, callback)
## 工具(jquery的静态方法)
+ $.isWindow(): 判断是不是window对象
+ $.isArray(arr): 判断是不是数组
+ $.isFunction(fn):判断是不是函数
+ $.isEmptyObject(obj): 判断是不是空对象
+ $.trim(str)
+ $.param(obj): 将json对象属性和属性值，通过&拼接成参数字符串
+ $.serialize(): 将表单的信息(name和value)组装成参数字符串
+ $.each(obj, (index, value)=>{}): 原生forEach方法只能遍历数组，不能遍历伪数组(key从0开始的对象，有length属性),jquery的each方法可以遍历伪数组和对象
+ $.map(obj, (value, index)=> {}): 原生js的map方法不能遍历伪数组,jquery的map方法可以
jquery中的each方法和map方法的区别：
+ each方法默认返回值是被遍历的数组或对象，map方法默认返回值是空数组
+ each方法不能对被遍历的对象进行处理，map方法可以对被遍历的数组进行处理，返回一个新的数组
静态方法：方法直接绑定到类上
实例方法：方法绑定到类的原型上，通过类的实例调用

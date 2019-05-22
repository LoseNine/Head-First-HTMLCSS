Head First HTML CSS

`读书笔记`

#### 介绍了最基本的HTML，包括`div`与`p`前者是常用的块级别元素，后者也是块级别元素，不过是用来标记段落的。所谓的块级别元素粗略来说就是独自一行的。
#### 内联元素
> 和其他元素在一行上
> 内外边距，宽和高不可变
#### 块级元素
> 总是在新的一行上显示
> 宽高，内外边距都是可以调节的
#### 常用的块元素
- div
- form
- h1234567
- p
- ol
- ul
- table
- hr
#### 常用的内联元素
- a
- img
- label
- input
- span
- select
#### 块元素和内联元素的主要差异是块元素是从新的一行开始。而内联元素一般显示在一行上。但是可以通过css的display属性将内联元素改变为块元素，（display：block） 也可以将块元素改变为内联元素（display：in-line）。
******
### WEB页面建设
#### `<q>`是引用标签，也就是加了双引号，可以用在`<p>`标签之内。`<blockquote>`也是引用，二者的区别是块和内联元素的区别。
#### `<br>`是换行标签，是一个块标签。
#### 元素总结
- a建立链接
- q短引用
- p一个段落
- ol有序列表
- ul无序列表
- code计算机代码
- em强调
- time日期
- li列表中的项目
- strong强调
- pre按照原样输出
- br换行
- img图片
- blockquote块引用
#### 可以用a标签指向id来进行跳转
#### 图片类型

JPEG|PNG|GIF
-|-|-|-
适合连续色调|单色调|单色调
文件小|文件大|比JPEG大
静态|静态|可动画


#### img图片里的alt是对图片的描述

#### `<meta>`指定编码格式
### 使用css
- 可以用`border-bottom`来做下划线，也可以用 `text-decorate`去除下划线使用下划线的时候，格式为1px solid black。
- 可以把css单独文档，之后引入，使用`<link ref='stylesheet' type='text/css' href='mycss'>`
####属性总结
- color文本元素字体颜色
- font-weight控制文本粗细
- left指定元素左边所在范围
- line-height设置文本行间距
- top元素顶部位置
- border边框
- padding内边距
- text-align文本对齐
- font-style设置斜体文本可以用
- list-style改变列表外观

###拓展词汇量
####font-weight文本粗细
- lighter
- normal
- bold
- bolder
####text-decoration下划线
- none
- underline
- overline
- lint-through
####font-style字体风格
- italic斜体
- oblique倾斜
#### 自定义font
```angular2html
@font-face{
  font-family:"TEST";
  src:url("http://test/1.tff"),
  src:url("http://test/1.woff");
 }
h1{
    font-family:"TEST",sans-serif;
}
```
###盒子模型
####border-style
- solid经典实心
- dotted虚线
- groove细线
- double双线
- inset内嵌
####可以指定某一边的`border-top-color``border-left-style`
###`border-radius`可以设置圆角边框，很常用
- border-top-left-radius
- border-bottom-right-radius

###根据不同的设备使用不同的css
```
<link rel="stylesheet" type="text/css" href="./test.css" media="screen and (min-device-width:500px)">
@media screen and (min-device-width:300px){
    p{
        color: red;
    }
}
@media screen and (min-device-width:500px){
    p{
        color:blue;
    }
}
```  

###关于div
####div很容易滥用，但是只要注意div里出现的是逻辑重复的就可以了，记住，div为的是可复用

##摆放与定位
###首先是流
####浏览器处理元素是从上到下，每个块元素占据一行，直到末尾；而内联元素就只能在一行之内
####如果屏幕比较窄，内联元素也只会在块元素中移动，从左上到右下
###其次是浮动
####浮动就是不属于流体了，在流体之外，其他的块元素会在他的下方，不过内联元素定位的时候回考虑浮动元素，围绕着它。
####切记，浮动的时候，如果希望它在某个元素后边，就要浮动元素的HTML，让它紧紧挨着那个元素
####要秉持左松右紧的原则，主题内容不固定，浮动内容必须固定宽度。之后可以在主体内容的margin-right中设置适当的宽度
####用clear可以禁止浮动漂浮在自己上方
####有两个布局
- 流体布局，不要把整个页面包含在一个div里，头部，中间，尾部各一个div
- 凝胶布局，整体在一个div里，设置div宽度，之后margin：0 auto居中。
###
####绝对定位-会随着页面移动，不过已经不再流体上了
```angular2html
position:absolute;
top:100px;
right:200px;
width:280px;
```
#####需要注意的是，绝对定位可以使用z-index决定谁在前边，数值大的在前
#####但是使用绝对定位的话，就会覆盖在其他上边，clear不起作用....
####固定定位-固定在屏幕上
```angular2html
position:fixed;
top:100px;
right:200px;
```
###table框架
####避免各种position的方法是使用一个框架table，每一行为row，框架的display为table，row的display为table-row，之后里边的每一个div是一个display：table-cell，然后可以不再使用margin，改用vertical-align：center

###HTML5
- time     可能包含一个日期或者时间
- nav      页面导航
- header   放在页面某个区域的顶部
- footer   页面某个区域的地步
- article  一个页面独立部分，一个博客帖子，新闻
- section  一个主题性内容分组，包含头尾
- video    视屏媒体

###列表样式
- list-style-type
- circle
- disc
- square
- none没有前缀
- 定制`list-style-image:url()`

###table样式
- table的border-collapse: collapse;
- tr的nth:child(odd event)
- rowspan

###form表单可以用table框架解决

###css选择器
- img[height="300"]{border:1px solid black}
- h1+p兄弟选择器
- div>p子类选择器

###css新特性
- transition: all 1s ease 2s;全部，几秒，效果，延迟
- transform属性应用于元素的2D或3D转换。这个属性允许你将元素旋转，缩放，移动，倾斜等。
- transform:rotate();旋转
- transform:translateX(x)移动
- transform:scaleX(20)拉长多少倍
- transform:skewY(90deg)沿着给定的轴斜切多少度
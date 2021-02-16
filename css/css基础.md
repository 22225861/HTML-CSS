# 文字样式属性
````
font-style:italic 倾斜 normal 正常
font-weight:(单词取值)bold 加粗 bolder 比加粗还要粗，（默认）细线
font-size:number+单位
font-family:"微软雅黑"，（字体主题）必须是安装的字体
缩写 font:italic bold 10px '楷体' size和family不能省略 size在family前面，一起放在最后
````
# 文本属性
````
text-decoration:underline 下划线 line-through 删除线 overline 上划线 none 用于取消a标签的下划线
text-align:right右 center中 left 左
text-indent：2em  em代表一个文字宽度
````
# 颜色
````
color:red(颜色英文) rgb( ) rgba( )比rgb多一个透明属性 #+16进制
````
# 标签选择器
作用：根据指定的标签名称，在当前界面中找到所有该名称的标签，然后设置属性
格式
````
标签名称 {
	属性：值
}
````
### 注意点
1.标签选择器选中的是当前页面中所有的标签,而不能单独选中某一个标签<br>
2.标签选择器无论标签藏得多深都能选中<br>
3.只要是HTML的标签就可以作为标签选择器<br>
(h/a/img/ol/ul/input...)
# id选择器
作用：根据指定的id名称，找到对应的标签，然后设置属性<br>
````
#id名称{
	属性：值
}
````
如果仅仅为了设置样式，我们不会使用id，因为在前端开发中id是留给js使用
### 注意点
1.每个HTML标签都有一个属性叫做id,也就是说每个标签都可以设置id<br>
2.在同一界面中id的名称是不可以重复的<br>
3.在编写id选择器一定要在id名称前面加上#<br>
4.id的名称只能由字母，数字，下划线组成且不能以数字开头，id名称不能是HTML名称<br>
# 类选择器
作用：根据指定的类名，找到对应的标签，然后设置属性
````
.类名{
	属性：值
}
````
### 注意点
1.每个HTML标签都有一个属性叫做class,也就是说每个标签都可以设置类名<br>
2.在同一界面中class的名称是不可以重复的<br>
3.在编写class选择器一定要在class名称前面加上.<br>
4.同id选择器命名规范<br>
5.类名就是专门用来给某个特定的标签设置样式的<br>
6.在HTML中一个标签可以同时绑定多个类名<br>
格式
````
<标签名称 class='类名1 类名2 ...'>
````

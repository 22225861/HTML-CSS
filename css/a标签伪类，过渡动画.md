# a标签的伪类选择器
作用：是用来专门修改a标签不同状态的样式<br>
格式
````
a:link {} 修改从未被访问过状态的样式
a:visited{} 修改被访问过的状态下的样式
a:hover{} 修改鼠标悬停在a标签上状态下的样式
a:active {} 修改鼠标长按状态下的样式
````
### 注意点
a标签的伪类选择器如果一起出现，那么有严格的顺序要求，顺序为 l(link)ov(visited)e h(hover)a(active)te

# 过渡效果三要素
必须要有属性发生变化<br>
必须告诉系统哪个属性需要执行过渡效果<br>
必须告诉系统过渡效果持续时长
### 注意点
 当多个属性需要同时执行过渡效果时用逗号隔开即可<br>
 ````
 transition-property:width,background-color；(需要过渡的属性)
 transition-duration：5s，5s；(过渡持续时间)
 transition-delay:2s(延迟2秒开始)
 transition-timing-function(过渡动画的运动速度):linear(匀速),ease(逐渐慢下来) ease-in(加速),ease-out(减速),ease-in-out(先加速后减速)
 transition:property duration delay timing-function    delay和timing-function可以省略
 如果多个属性运动的速度/延迟时间/持续时间都一样，可以简写为 transition：all 0s

```` 
# transform:rotate(45deg)
 旋转45度 deg是单位，代表多少度
 # transform:translate(0px,-50px)
第一个参数：水平方向，第二个参数：垂直方向
# transform：scale(1.5,1.5)
第一个参数：水平方向，第二个参数：垂直方向<br>
如果取值为一 不变，大于1，则放大，小于1 则缩放。<br>
水平方向和垂直方向值一样，可以简写为一个参数
#综合
如果需要进行多个转换，那么用空格隔开，2D的转换模块会修改元素的坐标系，所以旋转之后再平移就不是水平平移<br>
transform:rotate(45deg),translate(0px,-50px),scale(1.5,1.5)
# transform-origin：0px 0px;(具体值，百分比，特殊关键字)
 默认情况下所有的元素都是以自己的中心点作为参考来旋转的，我们可以通过形变中心点属性来修改它的参考点
第一个参数：水平方向，第二个参数：垂直方向
# transform:rotateX/rotateY/rotateZ(45deg)
沿x轴/y轴/z轴旋转
# 透视(perspective：具体值)
近大远小，透视属性必须添加到呈现近大远小效果元素的父元素上

# 盒子阴影
box-shadow：水平偏移 垂直偏移 模糊度 阴影扩展 阴影颜色 内外阴影<br>
默认阴影颜色随盒子内容颜色一致
#文字阴影
text-shadow：水平偏移 垂直偏移 模糊度 阴影颜色 <br>
默认阴影颜色随盒子内容颜色一致
 
 #过渡与动画的异同
 ## 不同点
 过渡必须人为的触发才能执行动画<br>
 动画不需要认为的触发就能执行动画
 ````
  div {
	  animation-name:name;(执行哪个动画)
	  animation-duration:3s;(持续的时长)
	  animation-delay:2s;（延迟）
	  animation-timing-function: 取值与过渡一样 (运动速度)
	  animation-iternation-count:3;（动画执行3次）
	  animation-direction：normal(默认，执行完后回到起点继续执行下一次) alternate（往返一次算执行了一次）
	  animation:running（执行动画）paused（暂停动画）
	  动画由一定状态： 等待状态，执行状态，结束状态
	  animation-fill-mode:none（默认）backwards（让元素等待状态的时候显示动画第一帧的样式）
		   forwards(元素结束状态的时候显示动画最后一帧的样式)
		   both forwards+backwords(指定动画等待状态和结束状态的样式)
	  animation:动画名称 动画时长 动画运动速度 延迟时间 执行次数 往返动画
       
	  }
	  
  @keyframes name {
	  from {
		  margin-left:0px;
	  }
	  to{
		  margin-left:500px
	  } (div从0到500px)
  }
   @keyframes name {
	   0% {
		   left:0;
		   top:0;
	   }
	   25% {
		   let:300px;
		   top:0;
	   }
	   50%{
		   left:300px ;
		   top:300px
	   }
	   75%{
		   left:0;
		   top:300px
	   }
	   100%{
		   left:0;
		   top:0;
	   }
   }(div走了一个矩形 如果使用left top需要在div设置定位属性)
 ````
 
 # 3D 转换
 ## 2D与3D
 2D就是一个平面，只有宽高，没有厚度<br>
 3D就是一个立体，有宽高和厚度<br>
 默认情况下所有的元素都是2D展现的
 ## 如何让某个元素3D展现
 和透视一样，想看到某个元素的3D效果，只需要给他的父元素添加一个transform-style属性，然后设置为preserve-3d即可
 # 背景尺寸属性
 ````
 第一个参数 ：宽度，第二个参数：高度
 background-size:200px/100% 100px/100%
 cover含义：告诉系统图片需要等比拉伸，告诉系统图片需要拉伸到宽度和高度都填满元素
 background-size：cover
 contain含义：告诉系统图片需要等比拉伸，告诉系统图片需要拉伸到宽度或高度填满元素
 background-size：contain
 
 background-origin 告诉系统图片从什么区域开始显示
padding-box 从padding区域开始显示
border-box 从border区域开始显示
content-box  从content区域开始显示                                                                            
background-origin:padding-box/border-box/content-box
 
 
 
 ````
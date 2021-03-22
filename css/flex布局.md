````
写在父元素上的
display:flex (块级元素) inline-flex（行内元素）
按照主轴方向分布排列元素flex-direction:
					row (默认 主轴从左到右) 
					row-reverse(主轴从右到左) 
					column(主轴从上到下)
					column-reverse(主轴从下到上)
决定子元素在主轴的排列方式justify-content:
						flex-start(默认) 
						flex-end(与主轴结束点对齐)
						center (居中对齐)
						space-between(一个元素在主轴开始，一个元素在主轴结束，其他的在中间分布)
						space-evenly(平均分布)
						space-around(第一个元素和最后一个元素距离边界是其他元素之间距离的一半)
在交叉抽的排列方式align-items:
				normal stretch (在交叉抽方向的大小设置为auto 会自动拉伸填充)
				flex-start (从交叉轴顶部开始排列)
				flex-end (从交叉轴尾部开始排列)
				center (从交叉轴中部开始排列)
				baseline  (从第一个元素的基线对齐 )
默认情况下，所有的子元素都会在同一行显示  超出父元素宽高会压缩所有子元素
flex-wrap ：
			nowrap(不换行)
			wrap(换行)
			wrap-reverse(对比wrap 交叉轴与wrap交叉轴相反)
flex-flow是flex-direction || flex-wrap的简写
多行在交叉轴的排列方式align-content
					flex-start(从交叉轴顶点开始排列) 
					flex-end(效果可以理解为先从交叉轴顶点开始排列 然后下移到最后一行位于交叉轴尾部)
					center (居中排列)
				    space-between(一行元素在交叉轴顶部开始，一行元素在交叉轴尾部，其他的在中间分布)
					space-evenly(平均分布)
					space-around(第一行元素和最后一行元素距离边界是其他行之间距离的一半)
					
````

````
写在子元素
决定子元素排布顺序 order
					可以设置任意整数，值越小就越排在前面
					默认是0
align-self 覆盖父元素设置的align-items  align-self：
										auto  遵从align-items的设置
										stretch flex-start flex-end center baseline  效果与align-items一致
flex-grow :
		可以设置非负数字，默认值是0;
		当父元素在主轴方向上还有剩余空间时，flex-grow才会生效
		如果所有的子元素里面的flex-grow总和超过1 每个子元素扩展的size为 父元素剩余空间*flex-grow/总和
		如果所有的子元素里面的flex-grow总和不超过1 每个子元素扩展的size为 父元素剩余空间*flex-grow
flex-shrink 决定子元素如何收缩
		可以设置任意非负数字 默认值为1
		子元素所占的空间大于父元素空间 flex-shrink才会生效
		如果所有的子元素里面的flex-shrink总和超过1 每个子元素扩展的size为 超出范围*收缩比例/所有收缩比例之和
		如果所有的子元素里面的flex-shrink总和不超过1 
						base size 是原设置的大小 收缩比例=flex-shrink*base size
						超出范围*flex-shrink总和*收缩比例/所有收缩比例之和
flex-basis 设置base size
决定base size的因素，优先级高到低
						max-width/min-width/max-height/min-height
						flex-basis
						width/height
						内容本身size
flex 是flex-grow|| flex-shrink||flex-basis简写 
flex:
	无单位数 会被视为<flex-grow>的值
	有单位数 会被是为<flex-basis>的值
	关键字 none auto initial
										
										
````
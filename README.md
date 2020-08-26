 同程艺龙-多种模式日历插件,支持标准选择模式、酒店入住离开模式、飞机往返模式，可自定义主题色
 * Calendar.vue 可以传参设置主题色，如theme-color="#ff6600 或 #f60"（依赖less），如用sass可在源代码style标签内修改

  ![](https://file.40017.cn/tcyp/tz/11.png)
  ![](https://file.40017.cn/tcyp/tz/22.png)
  ![](https://file.40017.cn/tcyp/tz/33.png)

  
  
```diff
+ 为了及时响应大家的各种功能需求，可谓不遗余力
+ 所以希望能在上面github链接里点个star，也算是鼓励一下了！
+ 同时有什么新的需求和建议可以继续联系我，我及时更新...
```

github链接
[链接名称](https://github.com/tanagang/mobile-calendar-simple)


### 使用方法
若在vue-cli项目中安装：npm install mobile-calendar-simple -S （若使用uniapp的工具HBuilderX导入，可以忽略此步骤）
```javascript
<template>
<div>
	<!--用法一：start-date省略即默认当天 -->
	<calendar :is-show="true" :start-date='startDate'  @callback="getDate" /> 
	<!--用法二：当mode=2、3的模式下分别为（酒店\往返）的离开日期-->
	<calendar :is-show="true" :start-date="startDate" :end-date="endDate" mode="2" @callback="getDate" />
	<!--用法三：可以操作的日期范围-->
	<calendar :is-show="true" :between-start="startDate" :between-end="endDate" @callback="getDate" />
	<!--设置动画transition="'slide'"且目前仅支持slide -->
	<calendar :is-show="true" :transition="'slide'"  @callback="getDate" />
	<!--设置主题色-->
	<calendar  :is-show="true" :theme-color="'#FF6600'"  @callback="getDate" />
	<!--如果需要solt-->
	<calendar :is-show="true">
		...此处也支持slot注入（不需要可以忽略）
		<template v-slot:header>
			<div>我是头部</div>
		</template>
		<template v-slot:footer>
			<div>我是脚部</div>
		</template>
	</calendar>
</div>
</template>
<script>
	import Calendar from 'mobile-calendar-simple'
	export default {
		data(){
			return {//日期均为yyyy-mm-dd或者yyyy/mm/dd格式
				startDate:'',
				endDate:'',
				betweenStart:'',
				betweenEnd:'',
			}
		},
		methods:{
			//获取回调的日期数据
			getDate(date){
				console.log(date)
			}
		},
		components:{
			Calendar
		}
	}
</script>
```
### 参数如下
  *  is-show 控制控件的显示隐藏，模式false
  *  start-date 默认当天,当mode=2、3的模式下分别为（酒店\往返）的出发日期
  *  end-date 当mode=2、3的模式下分别为（酒店\往返）的离开日期
  *  between-start 和 between-end 可以操作的日期范围
  *  theme-color 日历的主题色，例 '#FF6600'或者简写'#f60'(默认#1C75FF)
  *  mode 模式选择（默认1标准模式），2酒店模式，3往返模式
  *  transition 支持动画，属性为slide
  *  init-month 初始月份数（默认6个月）最小1个月
  *  title 日历顶部的一段文本
  *  is-fixed 日历是否定位全屏显示，默认true


### 回调函数
  *  @callback：日期选择后获取到的数据（所有你想要的都有）
***



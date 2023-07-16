# 一级标题



## 二级标题



### 1.配置（视频2.1）

* ```vue
  空白页面
  
  <template>
  	<view class="box">
  
  	</view>
  </template>
  
  <script>
  	export default {
  		
  	}
  </script>
  
  <style>
  	
  </style>
  
  ```

  ```vue
  <template>
  	<!--Vue2中 只有一个盒子 这里用view 只能写一个view-->
  	<view class="box">
  		<h1>uniappstu</h1>
  		<h2>uniappstu2</h2>
  	</view>
  </template>
  
  <script>
  	export default {
  		
  	}
  </script>
  
  <!-- 以下为css样式 预装插件 scss样式可以在一个 .box里进行编辑-->  
  <style lang="scss">
  .box{
  	width:100px;
  	height:100px;
  	background:pink
  	h1{
  		font-size: 40px;
  	}
  }
  	
  </style>
  ```
  
  


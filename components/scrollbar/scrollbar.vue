<template>
	<view>
		<div class="test test-1" :style="{height:height}">
		      <div class="scrollbar">
				 <slot></slot>
			  </div>
		</div>
	</view>
</template>

<script>
	export default {
		name:"scrollbar",
		props:{
			height:{
				type:String,
				default:'100px'
			}
		},
		data() {
			return {
				
			};
			
		}
	}
</script>

<style lang="scss">
 .test {
	  width   : 100%;
	  height  : 600rpx;
	  overflow: auto;
	  float   : left;
	  margin  : 5px;
	  border  : none;
	  }
	  .scrollbar {
	  width : 100%;
	  height: 300px;
	  margin: 0 auto;
	  }
	  .test-1::-webkit-scrollbar {
	  /*滚动条整体样式*/
	  width : 0px;  /*高宽分别对应横竖滚动条的尺寸*/
	  height: 0px;
	  }
	  .test-1::-webkit-scrollbar-thumb {
	  /*滚动条里面小方块*/
	  border-radius: 10px;
	  box-shadow   : inset 0 0 5px rgba(0, 0, 0, 0.2);
	  background   : #535353;
	  }
	  .test-1::-webkit-scrollbar-track {
	  /*滚动条里面轨道*/
	  box-shadow   : inset 0 0 5px rgba(0, 0, 0, 0.2);
	  border-radius: 10px;
	  background   : #ededed;
	  }
</style>

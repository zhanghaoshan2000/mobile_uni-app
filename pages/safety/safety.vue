<template>
	<view class="safety">
		<u-overlay :show="show">
			<view class="warp">
				<view class="rect" >
					<view class="content">
						<text class="title">{{msg}}</text>
						<scrollbar height="600rpx">
							数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据
							数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据数据
						</scrollbar>
					</view>
						<u-button type="primary"  text="已阅读" class="btn"  @click="read()">已阅读</u-button>
				</view>
			</view>
		</u-overlay>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				value:60,
				show: true,
				disabled: true,
				msg:"工程实施安全注意事项"
			}
		},
		methods: {
			read(){
				uni.navigateTo({
					url: '../index/index',
				});
			},	
			
		}
	}
</script>

<style lang="scss" scoped>
	.warp {
		display: flex;
		align-items: center;
		justify-content: center;
		height: 100%;
	}

	.rect {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 80%;
		height: 900rpx;
		background-color: #fff;
		flex-direction: column;
		
	}
	.content{
		width: 90%;
		height: 600rpx;
	}
	.title{
		display: flex;
		justify-content: center;
		font-weight: 600;
	}
	.btn{
		margin-top: 100rpx;
		width: 200px;
		position:relative;
		
		
	}
	
</style>

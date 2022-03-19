<template>
	<view class="user">
		<u--image :showLoading="true" :src="src" width="180rpx" height="180rpx" @click="click" shape="circle"
			class="img"></u--image>
		<view class="cell">
			<text class="iconfont icon-nianling"></text>
			<text class="name">姓名:</text>
			<text class="user_message">张三</text>
		</view>
		<view class="cell">
			<text class="iconfont icon-nianling"></text>
			<text class="name">年龄:</text>
			<text class="user_message">张三</text>
		</view>
		<view class="cell">
			<text class="iconfont icon-nianling"></text>
			<text class="name">昵称:</text>
			<text class="user_message">张三</text>
		</view>
		<view class="cell">
			<text class="iconfont icon-nianling"></text>
			<text class="name">账号:</text>
			<text class="user_message">123456456498456</text>
		</view>
		<view class="fuwu">
			<text class="fuwufont">企业服务</text>
		</view>
		<view class="cell">
			<text class="iconfont icon-nianling"></text>
			<text class="name">企业操作级别:</text>
			<text class="user_message">张三</text>
		</view>
		<u-button type="primary" text="退出登录" class="btn"></u-button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				src: 'https://cdn.uviewui.com/uview/album/1.jpg',
			}
		},
		methods: {
			click() {

			}
		}
	}
</script>

<style lang="scss" scoped>
	.user {
		display: flex;
		flex-direction: column;
		align-items: center;

		.img {
			padding: 40rpx;
		}
	}

	.iconfont {
		font-size: 40rpx;
		line-height: 40rpx;
		color: #596D76;
	}

	.cell {
		width: 90%;
		height: 60rpx;
		padding: 5px;
		border-bottom: 2rpx solid #DEDEE0;
		color: #596D76;

		margin-top: 16rpx;
		background-color: #fff;

		.name {
			font-weight: 600;
			margin-right: 16rpx;
			margin-left: 30rpx;
			letter-spacing: 4rpx;
		}
	}

	.fuwu {
		display: flex;
		font-size: 24rpx;
		padding: 20rpx;
		color: #596D76;
		background-color: #F8F8F8;
		width: 100%;

		.fuwufont {
			margin-left: 40rpx;
		}
	}
	.btn{
		width: 70%;
		margin-top: 40rpx;
	}
</style>

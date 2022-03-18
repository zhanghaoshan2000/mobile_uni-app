<template>
	<view class="content">
		<view class="img">
			<image :src="src1" mode="">
			</image>
		</view>
		<text class="fontTitle">智慧打桩</text>
		<view class="head">
			<view class="user">
				<u-avatar :src="src" shape="square" size="60"></u-avatar>
				<view class="title">
					<text class="font">名字</text>
					<text class="font2">项目名称</text>
				</view>
			</view>
			<view class="post">
				<u-button type="success" :plain="true" text="查看项目进度" class="btn"></u-button>
			</view>
		</view>
		<view class="tab-container">
			<view class="replace">
				<text class="name">智慧操作</text>
				<text class="iconfont icon-jiantou_zuoyouqiehuan"></text>
			</view>
			<u-row justify="space-between" gutter="10">
				<u-col span="3">
					<view class="demo-layout bg-purple">
						<view class="icon">
							<text class="iconfont icon-jihua"></text>
							<text class="font_icon">施工计划</text>
						</view>
					</view>
				</u-col>
				<u-col span="3">
					<view class="demo-layout bg-purple">
						<view class="icon">
							<text class="iconfont icon-kongzhiqi"></text>
							<text class="font_icon">设置控制</text>
						</view>
					</view>
				</u-col>
				<u-col span="3">
					<view class="demo-layout bg-purple">
						<view class="icon">
							<text class="iconfont icon-watuji-wajueji-chanche"></text>
							<text class="font_icon">设备信息</text>
						</view>
					</view>
				</u-col>
				<u-col span="3">
					<view class="demo-layout bg-purple">
						<view class="icon">
							<text class="iconfont icon-geren"></text>
							<text class="font_icon">个人信息</text>
						</view>
					</view>
				</u-col>
			</u-row>
			<u-row justify="space-between" gutter="10">
				<u-col span="3">
					<view class="demo-layout bg-purple">
						<view class="icon">
							<text class="iconfont icon-anquanxuzhiicn"></text>
							<text class="font_icon">安全须知</text>
						</view>
					</view>
				</u-col>
				<u-col span="3">
					<view class="demo-layout bg-purple">
						<view class="icon">
							<text class="iconfont icon-shezhi"></text>
							<text class="font_icon">普通数据设置</text>
						</view>
					</view>
				</u-col>
				<u-col span="3">
					<view class="demo-layout bg-purple">
						<view class="icon">

						</view>
					</view>
				</u-col>
				<u-col span="3">
					<view class="demo-layout bg-purple">
						<view class="icon">
						</view>
					</view>
				</u-col>
			</u-row>
			<u-swiper :list="list3" indicator indicatorMode="line" circular class="swiper"></u-swiper>
		</view>


	</view>
</template>

<script>
	export default {
		data() {
			return {
				src1: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.61980.cn%2F20321%2F2021%2F0823%2F20210823nep1629708219.jpg&refer=http%3A%2F%2Fimg.61980.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1650177831&t=08398c558ea80129ad746544792849ce',
				src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fup.enterdesk.com%2Fedpic%2F4d%2F63%2Fbd%2F4d63bd0b3bf8cc9aa0dc3e1111646b1c.jpeg&refer=http%3A%2F%2Fup.enterdesk.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1650176073&t=d6ae7234b0bb8164676a78550c2ade9d',
				list3: [
					'https://cdn.uviewui.com/uview/swiper/swiper3.png',
					'https://cdn.uviewui.com/uview/swiper/swiper2.png',
					'https://cdn.uviewui.com/uview/swiper/swiper1.png',
				],
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.content {
		display: flex;
		/* justify-content: center; */
		flex-direction: column;
		align-items: center;
	}

	.img {
		width: 100%;

	}

	.img image {

		width: 100%;
		height: 300rpx;
		z-index: 1;
	}

	.head {
		display: flex;
		/* background-color: rgb(235, 237, 238); */
		background-color: #fff;
		padding: 20rpx 40rpx;
		width: 80%;
		justify-content: space-between;
		border-radius: 10rpx;
		margin-top: -60rpx;
		z-index: 2;
		box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.2);
	}

	.user {
		display: flex;
	}

	.title {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: flex-start;
		margin-left: 30rpx;
	}

	.font {
		font-size: 28rpx;
		font-weight: 600;
	}

	.font2 {
		font-size: 30rpx;
		color: #767A82;
	}

	.post {
		display: flex;
		align-items: center;

	}

	.btn {
		width: 200rpx;
		height: 50rpx;
		color: #F9AE3D;
	}

	.fontTitle {
		position: absolute;
		z-index: 5;
		font-size: 44rpx;
		font-weight: 600;
		color: #fff;
		letter-spacing: 8rpx;
		top: 160rpx;
		left: 40rpx;

	}

	.name {
		font-size: 40rpx;
		font-weight: 600;
	}

	.icon-jiantou_zuoyouqiehuan {
		font-size: 60rpx;
		font-weight: 600;
		color: #999999;
		vertical-align: middle;

	}

	.tab-container {
		width: 92%;
		display: flex;

		flex-direction: column;
	}

	.replace {
		display: flex;
		width: 100%;
		justify-content: space-between;
		margin-top: 30rpx;
	}

	.demo-layout {
		margin-top: 30rpx;
		// border-radius: 4px;
		text-align: center;
	}

	.icon {
		display: flex;
		flex-direction: column;

		.iconfont {
			font-size: 60rpx;
			font-weight: 500;
			margin-bottom: 10rpx;
		}
	}

	.font_icon {
		font-size: 26rpx;
	}
	.swiper{
		margin-top: 20rpx;
	}
</style>

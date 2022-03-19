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
				<u-button type="success" :plain="true" text="查看项目进度" class="btn" @click="gotoplan()"></u-button>
			</view>
		</view>
		<view class="tab-container">
			<view class="replace">
				<text class="name">智慧操作</text>
				<text class="pattern"> {{isShow?"专家模式":"普通模式"}}</text>
				<text class="iconfont icon-jiantou_zuoyouqiehuan" @click="bn()"></text>
			</view>
			<u-transition :show="show" class="transition1" mode="slide-left" :duration="duration2">
				<u-row justify="space-between" gutter="10">
					<u-col span="3">
						<view class="demo-layout bg-purple">
							<view class="icon" @click="gotoplan()">
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
							<view class="icon" @click="gotomech()">
								<text class="iconfont icon-watuji-wajueji-chanche"></text>
								<text class="font_icon">设备信息</text>
							</view>
						</view>
					</u-col>
					<u-col span="3">
						<view class="demo-layout bg-purple">
							<view class="icon" @click="gotosuer()">
								<text class="iconfont icon-geren"></text>
								<text class="font_icon">个人信息</text>
							</view>
						</view>
					</u-col>
				</u-row>
				<u-row justify="space-between" gutter="10">
					<u-col span="3">
						<view class="demo-layout bg-purple">
							<view class="icon" @click="gotoSafe()">
								<text class="iconfont icon-anquanxuzhiicn"></text>
								<text class="font_icon">安全须知</text>
							</view>
						</view>
					</u-col>
					<u-col span="3">
						<view class="demo-layout bg-purple">
							<view class="icon" @click="gotoUsework()">
								<text class="iconfont icon-shezhi"></text>
								<text class="font_icon">普通数据设置</text>
							</view>
						</view>
					</u-col>
					<u-col span="3">
						<view class="demo-layout bg-purple">
							<view class="icon " v-show="isShow" @click="gotowork()">
								<text class="iconfont icon-shebei"></text>
								<text class="font_icon">专家数据设置</text>
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
			</u-transition>
			<u-transition :show="show" class="transition1" mode="slide-left" :duration="duration1">
				<u-swiper :list="list3" indicator indicatorMode="line" circular class="swiper"></u-swiper>
			</u-transition>
		</view>
		<scrollbar height="340rpx" style="width: 100%; padding: 0;margin-left: -10px;">
			<u-transition :show="show" class="transition" mode="slide-left" :duration="duration">
				<view v-for="item in arr" :key="item.id">
					<view class="card">
						<view class="card_top">
							<view class="title_card">
								<text class="name_card">打桩机</text>
								<text class="time_card">2022-02-24</text>
							</view>
							<view class="plan_card">
								<text class="plan_card">设备工作进度</text>
							</view>
						</view>
						<view class="bottom">
							<view class="img_card">
								<image :src="src2" mode="" style="width:100rpx ;height:100rpx ;"></image>
							</view>

							<view class="percent_card">
								<view class="squar_card">
									<u-line-progress :percentage="percentage" activeColor="#19BE6B"
										style="background-color: red;"></u-line-progress>
								</view>
								<text class="font_card" v-model="percentage">
									已完成{{percentage}}%
								</text>
								<u-button type="primary" :plain="true" text="项目进度" class="statBtn" size="mini"></u-button>
							</view>
						</view>
					</view>
				</view>
			</u-transition>
		</scrollbar>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				src2: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fm.xbgj58.com%2Fuploadfiles%2Fpictures%2Fnews%2F20200506102255_2240.jpg&refer=http%3A%2F%2Fm.xbgj58.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1650177831&t=1240d7cf2747e0d29965f3999a5a7c60',
				src1: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg.61980.cn%2F20321%2F2021%2F0823%2F20210823nep1629708219.jpg&refer=http%3A%2F%2Fimg.61980.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1650177831&t=08398c558ea80129ad746544792849ce',
				src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fup.enterdesk.com%2Fedpic%2F4d%2F63%2Fbd%2F4d63bd0b3bf8cc9aa0dc3e1111646b1c.jpeg&refer=http%3A%2F%2Fup.enterdesk.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1650176073&t=d6ae7234b0bb8164676a78550c2ade9d',
				list3: [
					'https://cdn.uviewui.com/uview/swiper/swiper3.png',
					'https://cdn.uviewui.com/uview/swiper/swiper2.png',
					'https://cdn.uviewui.com/uview/swiper/swiper1.png',
				],
				isShow: false,
				show: true,
				duration2: 900,
				duration1: 1000,
				duration: 1200,
				percentage: 60,
				arr: [1, 2, 3]
			}
		},
		onLoad() {

		},
		methods: {
			bn() {
				this.isShow = !this.isShow
			},
			gotoplan() {
				uni.navigateTo({
					url: '../projectDetails/projectDetails'
				});
			},
			gotomech() {
				uni.navigateTo({
					url: '../projectDetails/projectDetails'
				});
			},
			gotosuer() {
				uni.navigateTo({
					url: '../user/user'
				});
			},
			gotoSafe() {
				uni.navigateTo({
					url: '../safety/safety'
				});
			},
			gotoUsework() {
				uni.navigateTo({
					url: '../userworker/userworker'
				});
			},
			gotowork() {
				uni.navigateTo({
					url: '../work/work',

				});
			}
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

	.swiper {
		margin-top: 20rpx;
	}

	.transition {
		width: 100%;
		display: flex;
		justify-content: center;
		margin-left: 5%;
	}

	.transition1 {
		width: 100%;
		display: flex;
		justify-content: center;

	}

	.card {
		margin: 20rpx 0;
		width: 85%;
		// height: 190rpx;
		padding: 20rpx;
		background-color: #fff;
		box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.2);
		border-radius: 10rpx;

	}

	.card_top {
		display: flex;
		width: 100%;
		justify-content: space-between;

		.title_card {
			display: flex;
			flex-direction: column;

			.name_card {
				font-size: 26rpx;

			}

			.time_card {
				margin-top: 10rpx;
				font-size: 14rpx;
				color: #909399;
			}
		}

		.plan_card {
			display: flex;
			font-size: 26rpx;
			align-items: center;
		}

	}

	.bottom {
		display: flex;
		justify-content: space-between;

		.img_card {
			width: 100rpx;
			height: 100rpx;
			background-color: red;
			margin-top: 10rpx;
			border-radius: 10rpx;
		}

		.percent_card {
			display: flex;
			align-items: end;
			flex-direction: column;

		}

		.squar_card {
			width: 400rpx;
			height: 80rpx;
			display: flex;
			align-items: center;

		}

		.font_card {
			font-size: 20rpx;
			color: #666666;
		}

	}

	.pattern {
		position: relative;
		font-size: 22rpx;
		margin-top: 10rpx;
		margin-left: 300rpx;
		font-weight: 600;
		color: #007AFF;
	}
	.statBtn{
		margin-top: 20rpx;
		
		height: 50rpx;
		// transform: translateX(60rpx);
	}
</style>

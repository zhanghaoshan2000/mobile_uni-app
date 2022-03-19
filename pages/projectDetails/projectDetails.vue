<template>
	<view class="project">
		<view class="title">
			<u-icon name="map-fill"></u-icon>
			<text class="font">温州市瓯海区茶山街道</text>
		</view>
		<u-transition :show="show" class="transition" mode="slide-left" :duration="duration">
			<view class="user_project">
				<view class="user">
					<image :src="src" mode=""></image>
				</view>
				<view class="user_projectx">
					<view class="project_name">
						<text class="name">温州打桩项目</text>
						<view class="percent">
							<u-line-progress :percentage="percentage" activeColor="#19BE6B"></u-line-progress>
						</view>
						<text class="project_number" v-model="number">已完成个{{number}}小项目</text>
					</view>
					<view class="project_time">
						<text class="project_number">2022.02.05开始</text>
						<u-button type="primary" text="联系主要负责人" class="btn"></u-button>
					</view>
				</view>
			</view>
		</u-transition>
		<u-transition :show="show" class="transition" mode="slide-left" :duration="duration1">
			<view class="user_message"  @click="gotosuer()">
				<text class="font" >个人信息</text>
				<u-icon name="arrow-right" color="#F09D1B"></u-icon>
			</view>
		</u-transition>
		<view class="sub">
			<u-subsection :list="list" :current="current" @change="sectionChange">
			</u-subsection>
			<u-transition :show="show" class="transition" mode="slide-left" :duration="duration2">
				<view v-show="current === 0">
					<view class="project_card" v-for="item in arr" :key="item.id">
						<view class="project_content">
							<text class="card_name">桩定位、及送桩</text>
							<text class="card_time">预计完成时间</text>
							<text class="card_state" v-model="state">完成状态：{{state}}</text>
						</view>
						<view class="project_user">
							<text class="user" v-model="name">负责人签名:{{name}}</text>
						</view>
					</view>
				</view>
			</u-transition>
			<u-transition :show="show" class="transition" mode="slide-left" :duration="duration2">
				<view v-show="current === 1">
					<view class="project_card" v-for="item in arr" :key="item.id">
						<view class="project_content">
							<text class="card_name">桩定位、及送桩</text>
							<text class="card_time">预计完成时间</text>
							<text class="card_state" v-model="state">完成状态：{{state}}</text>
						</view>
						<view class="project_user">
							<text class="user" v-model="name">负责人签名:{{name}}</text>
						</view>
					</view>
				</view>
			</u-transition>
			<u-transition :show="show" class="transition" mode="slide-left" :duration="duration2">
				<view v-show="current === 2">
					<view class="project_card" v-for="item in arr" :key="item.id">
						<view class="project_content">
							<text class="card_name">桩定位、及送桩</text>
							<text class="card_time">预计完成时间</text>
							<text class="card_state" v-model="state">完成状态：{{state}}</text>
							<text class="card_time" v-model="percentage1">工作完成度{{percentage1}}%</text>
						</view>
						<view class="project_user">
							
						<view class="line" v-model="percentage1">
							{{percentage1}}    %
						</view>
							<text class="user" v-model="name">负责人签名:{{name}}</text>
						</view>
					</view>
				</view>
			</u-transition>
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				src: 'https://cdn.uviewui.com/uview/album/1.jpg',
				percentage: 30,
				number: 3,
				list: ['项目进度', '施工计划', '设备详情'],
				// 或者如下，也可以配置keyName参数修改对象键名
				// list: [{name: '未付款'}, {name: '待评价'}, {name: '已付款'}],
				current: 0,
				name: 'yyt',
				arr: [1, 2, 3, 4],
				state: '已完成',
				show: true,
				duration: 1000,
				duration1: 1200,
				duration2: 1400,
				percentage1:40,
			}
		},
		methods: {
			sectionChange(index) {
				this.current = index;
			},
			gotosuer(){
				uni.navigateTo({
					url: '../user/user'
				});
			},


		}
	}
</script>

<style lang="scss" scoped>
	.project {
		padding: 14rpx;
		display: flex;
		flex-direction: column;
	}

	.title {
		padding: 20rpx;
		display: flex;
		justify-content: start;

		.font {
			margin-left: 15rpx;
			font-size: 22rpx;
			color: #909193;
		}

	}

	.user_project {

		padding: 20rpx;
		display: flex;
		width: 100%;
		height: 190rpx;
		background-color: #fff;


		.user {
			display: flex;
			width: 160rpx;
			height: 190rpx;
			align-items: center;

			// background-color: red;
			image {
				width: 150rpx;
				height: 150rpx;
				border-radius: 50%;
			}
		}

		.user_projectx {
			display: flex;

			align-items: center;
			justify-content: center;
			height: 190rpx;

			.project_name {
				display: flex;
				margin-left: 18rpx;
				flex-direction: column;
				justify-content: space-around;
				height: 190rpx;
			}

			.name {
				font-size: 34rpx;
				font-weight: 600;
				letter-spacing: 6rpx;
			}

			.percent {
				display: flex;
				align-items: center;
				width: 210rpx;
				height: 60rpx;

			}

			.project_number {
				color: #585858;
				font-size: 16rpx;
			}

		}

		.project_time {
			height: 190rpx;
			display: flex;
			flex-direction: column;
			justify-content: space-around;
			margin-left: 20rpx;

			.project_number {
				font-size: 14rpx;
				color: #585858;
			}

			.btn {
				width: 100%;
				height: 60rpx;

			}
		}

	}

	.user_message {
		display: flex;
		justify-content: space-between;
		border-radius: 10rpx;
		padding: 20rpx;
		color: #F4C570;
		background-color: #FCF7E4;

		.font {
			font-size: 24rpx;
		}
	}

	.sub {
		margin-top: 20rpx;
	}

	.project_card {
		display: flex;
		padding: 20rpx 10rpx;
		justify-content: space-between;
		background-color: #fff;
		box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
		border-radius: 10rpx;
		margin: 20rpx 0;

		.project_content {
			display: flex;
			flex-direction: column;

			.card_name {
				font-size: 36rpx;
				font-weight: 600;
				letter-spacing: 4rpx;
				padding: 6rpx;
			}

			.card_time {
				font-size: 22rpx;
				color: #808080;
				padding: 4rpx;
			}

			.card_state {
				font-size: 22rpx;
				color: #808080;
				padding: 4rpx;
			}
		}
	}

	.project_user {
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
		margin-right: 25rpx;
		font-size: 22rpx;
		color: #808080;
		padding: 4rpx;
	}
	.line{
		display: flex;
		width:200rpx;
		height: 100rpx;
		align-items: center;
		font-size: 60rpx;
		justify-content: center;
		
	}

</style>

<template>
	<view class="eqp">
		<view class="top">
			<image :src="src" mode=""></image>
			<view class="ipt">
				<text>已工作:
				</text>
				<u--input border="surround" v-model="value1" @change="change" class="input"></u--input>天
				<u--input border="surround" v-model="value2" @change="change" class="input"></u--input>天
				<u--input border="surround" v-model="value3" @change="change" class="input"></u--input>天
			</view>
		</view>
		<view class="number">
			<view class="can_namber">
				<view class="can_row">
					<text>参数组:</text>
					<u-number-box :min="1" :max="10" class="add" v-model="value4"></u-number-box>
					<text>组</text>
				</view>
				<view class="prenct">
					<u-line-progress :percentage="value4*10" activeColor="#19BE6B"></u-line-progress>
				</view>
			</view>
		</view>
		<view class="number">
			<view class="can_namber">
				<view class="can_row">
					<text>电机功率:</text>
					<u-number-box :min="1" :max="10" class="add" v-model="value5"></u-number-box>
					<text>次</text>
				</view>
				<view class="prenct">
					<u-line-progress :percentage="value5*10" activeColor="#19BE6B"></u-line-progress>
				</view>
			</view>
		</view>
		<view class="btn_opt">
			<view class="top">
				<text class="iconfont icon-anniu_jiantoushouqi"></text>
				<text class="block">送绳</text>
			</view>
			<view class="middle">
				<!-- <view class="block"> -->

				<text class="iconfont icon-anniu_jiantouxiangzuo"></text>
				<text class="block">送绳</text>
				<!-- </view> -->
				<u-button type="success" text="启动" shape="circle" class="btn"></u-button>
				<text class="block">送绳</text>
				<text class="iconfont icon-anniu-jiantouxiangyou"></text>
			</view>
			<view class="bottom">
				<u-button type="primary" text="确定" size="small" class="bottom_btn"></u-button>
				<view class="bottom_zhankai">
					<text class="block">送绳</text>
					<text class="iconfont icon-anniu_jiantouzhankai"></text>
				</view>
				<u-button type="primary" text="确定" size="small" class="bottom_btn"></u-button>
			</view>
		</view>
		<u-cell-group class="cel">
			<u-cell title="磁钢" arrow-direction="down" v-model="value6">
				<u-icon slot="icon" size="32" right-icon class="iconfont icon-watuji-wajueji-chanche"></u-icon>
			</u-cell>
			<u-cell icon="clock" title="电机运行" v-model="value6"></u-cell>
			<u-cell icon="clock" title="起锥" v-model="value6"></u-cell>
		</u-cell-group>
		<u-button type="primary" text="确定" class="btns"></u-button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				value1: '',
				value2: '',
				value3: '',
				value4: 2,
				value5: 4,
				value6: '进行中',
				src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg000.hc360.cn%2Fk2%2FM07%2F14%2F57%2FvT8c1c276f625548f6E92fBABD9A79Bcf0.jpg&refer=http%3A%2F%2Fimg000.hc360.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1650354478&t=3dd55bac0ec25b6e410d2713a611ba7b'
			}
		},
		methods: {
			valChange(e) {
				console.log('当前值为: ' + e.value)
			}
		}
	}
</script>

<style lang="scss" scoped>
	.eqp {
		display: flex;
		flex-direction: column;
		padding: 18rpx;
		align-items: center;

		.top {
			display: flex;
			flex-direction: row;

			image {
				width: 120rpx;
				height: 120rpx;
				margin: 40rpx;
				border-radius: 10rpx;
			}
		}
	}

	.ipt {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.input {
		border: 1px solid rgba(0, 0, 0, 0.2);
		width: 40rpx;
		height: 40rpx;
		margin: 10rpx;

	}

	.number {
		display: flex;
		align-items: center;

		.add {
			padding: 16rpx 40rpx;
			// background-color: red;
		}

		.can_row {
			display: flex;
			align-items: center;
		}

		.can_namber {
			display: flex;
			flex-direction: column;
		}

		.prenct {
			display: flex;
			align-items: center;
			width: 450rpx;
			height: 40rpx;
		}
	}

	.btn_opt {
		display: flex;
		flex-direction: column;
		margin-top: 20rpx;
		width: 600rpx;
		height: 500rpx;

		.iconfont {
			font-size: 120rpx;
			color: #1685FA;
		}

		.block {
			font-size: 26rpx;

		}

		.top {
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
			flex: 1.2;
		}

		.middle {
			display: flex;
			flex: 1.2;

			align-items: center;
			justify-content: center;

			.btn {
				width: 40%;
			}

			.iconfont {
				font-size: 120rpx;
				color: #1685FA;
			}

			.block {
				font-size: 26rpx;

			}
		}

		.bottom {
			display: flex;
			align-items: center;
			justify-content: center;
			flex: 1.2;

		}

		.bottom_zhankai {
			display: flex;
			justify-content: center;
			align-items: center;
			flex-direction: column;
		}

		.bottom_btn {
			width: 100rpx;
		}
	}

	.cel {
		width: 90%;
	}
	.btns{
		margin-top:30rpx ;
		width: 60%;
	}
</style>

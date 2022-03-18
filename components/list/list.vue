<template>
	<view>
		<view class="list">
			<text class="font">
				<slot name="title">
				</slot>
			</text>
			<u--input class="input" placeholder="请输入内容" type="number" border="surround" v-model="value"></u--input>
			<text class="font">
				<slot name="unit">
				</slot>
			</text>
		</view>
	</view>
</template>

<script>
	export default {
		name: "list",
		data() {
			return {
				value:''
			};
		}
	}
</script>

<style lang="scss">
	.list {
		display: flex;
		justify-content: center;
		align-items: center;	
		margin-top: 20rpx;

	}

	.input {
		justify-content: center;
		align-items: center;
		/* width: 160rpx; */
		border: 1px solid #C6C7CB;
		margin: 0 20rpx;
	}

	.font {
		line-height: 76rpx;
	}
</style>

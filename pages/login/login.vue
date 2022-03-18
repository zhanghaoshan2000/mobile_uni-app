<template>
	<view class="login">
		<view class="content">
			<view class="user">
				<u--image :showLoading="true" :src="src" width="80px" height="80px" @click="click" shape="circle">
				</u--image>
			</view>
			<u--input placeholder="请输入用户名" border="surround" class="userlogin"></u--input>
			<u--input placeholder="请输入密码" border="surround"  class="userlogin"password="password"></u--input>
			<u-button type="primary" text="登录" class="btn" @click="login"></u-button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				src: 'https://cdn.uviewui.com/uview/album/1.jpg',
				value: '',
				password:'false'
			}
		},
		methods: {
			click() {

			},
			login(){
				uni.navigateTo({
					url: '../safety/safety'
				});
			}

		}
	}
</script>

<style lang="scss">
	.login {
		width: 100%;
		height: 100vh;
		background: linear-gradient(to right bottom, #E9AB7A, #EE7A6D, #F7DE9C, #A0DBA1);
		overflow-y: hidden;

		.content {
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			flex-direction: column;
			padding: 20rpx 80rpx;
		}

		.user {
			display: flex;
			width: 100%;
			padding: 200rpx 0 100rpx 0;
			justify-content: center;
		}
	}
	.userlogin{
		background-color: #fff; 
		width: 94%;
		margin: 30rpx 0;
	}
	.btn{
		margin-top: 20rpx;
	}
		
</style>

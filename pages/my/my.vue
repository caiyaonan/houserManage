<template>
	<view class="my-container">
		<view v-if="pageStatus == 'reg'" class="reg-container">
			<view class="reg-title">
				注册账号
			</view>
			<view class="reg-content">
				<uni-forms ref="regForm" :modelValue="regFormData">
					<uni-forms-item label="用户类型" name="user_type">
						<uni-data-checkbox v-model="userTypeVal" :localdata="userTypeRange" @change="change"></uni-data-checkbox>
					</uni-forms-item>
					<uni-forms-item label="用户名" name="username">
						<uni-easyinput type="text" placeholder="请输入6-16位用户名" />
					</uni-forms-item>
					<uni-forms-item label="邮箱" name="email">
						<uni-easyinput type="text" placeholder="请输入邮箱" />
					</uni-forms-item>
					<uni-forms-item label="手机号" name="mobile">
						<uni-easyinput type="text" placeholder="请输入手机号" />
					</uni-forms-item>
					<uni-forms-item label="密码" name="password">
						<uni-easyinput type="password" placeholder="请输入6-16位密码" />
					</uni-forms-item>
					<uni-forms-item label="确认密码" name="confirm_password">
						<uni-easyinput type="password" placeholder="请输入6-16位密码" />
					</uni-forms-item>
				</uni-forms>
				<button @click="regForm" size="mini">注册</button>
			</view>
			<view class="reg-bottom">
				<a href="">已有账号，点击前往登录</a>
			</view>
		</view>
		<view v-if="pageStatus == 'login'" class="login-container">
			<view class="login-title">
				登录账号
			</view>
			<view class="login-content">
				<uni-forms ref="loginForm" :modelValue="loginFormData">
					<uni-forms-item label="用户名" name="username">
						<uni-easyinput type="text" v-model="loginFormData.username" placeholder="请输入用户名" />
					</uni-forms-item>
					<uni-forms-item label="密码" name="password">
						<uni-easyinput type="password" v-model="loginFormData.password" placeholder="请输入密码" />
					</uni-forms-item>
				</uni-forms>
				<button @click="loginForm" size="mini">登录</button>
			</view>
			<view class="login-bottom">
				<a href="">暂无账号，点击前往注册</a>
			</view>
		</view>
		<view v-if="pageStatus == 'info'" class="info-container">
			<view class="info-header">
				<view class="info-header-avatar">
					<image src="../../static/img/touxiang.png" mode="scaleToFill"></image>
				</view>
				<view class="info-header-name">
					用户名
				</view>
			</view>
			<view class="info-content">
				<uni-list>
					<uni-list-item title="个人资料" clickable link @click="onPeopleInfo" ></uni-list-item>
					<uni-list-item title="浏览记录" clickable link @click="onReviewHistory"></uni-list-item>
					<uni-list-item title="发布房屋" clickable link to="../publish/publish"></uni-list-item>
					<uni-list-item title="退出登录" clickable link @click="onQuite"></uni-list-item>
				</uni-list>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				pageStatus: 'info',
				loginFormData: {
					username: 'test0001',
					password: 'test0001'
				},
				regFormData: {},
				userTypeVal: 0,
				userTypeRange: [{"value":0,"text":"租客"},{"value":1, "text": "房东"}]
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
.my-container {
	.reg-container {
		width: 750rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100vh;
		.reg-title {
			font-size: 30px;
			// border: 1px solid red;
		}
		.reg-content {
			// border: 1px solid red;
			margin-top: 20px;
			margin-bottom: 10px;
			padding: 10px 0px;
			width: 600rpx;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
		}
		.reg-bottom {
			// border: 1px solid red;
			font-size: 12px;
		}
	}
	
	.login-container {
		// border: 1px solid red;
		width: 750rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100vh;
		// border: 1px solid lightgray;
		.login-title {
			// border: 1px solid red;
			font-size: 30px;
		}
		.login-content {
			margin-top: 20px;
			margin-bottom: 10px;
			padding: 10px 0px;
			width: 600rpx;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
		}
		.login-bottom {
			font-size: 12px;
		}
	}
	
	.info-container {
		.info-header {
			width: 750rpx;
			height: 400rpx;
			// border: 1px solid red;
			display: flex;
			justify-content: center;
			align-items: center;
			flex-direction: column;
			.info-header-avatar {
				width: 250rpx;
				height: 250rpx;
				image {
					width: 100%;
					height: 100%;
				}
			}
			.info-header-name {
				margin-top: 10px;
				color: gray;
			}
		}
		.info-content {
			
		}
	}
}
</style>

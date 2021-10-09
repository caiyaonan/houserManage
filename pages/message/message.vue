<template>
	<view class="msg-contianer">
		<view class="msg-content">
			<uni-forms ref="msgForm" :modelValue="msgFormData">
					<uni-easyinput type="textarea" autoHeight v-model="msgText" placeholder="请输入留言内容" />
			</uni-forms>
			<button @click="msgForm">发布留言</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				msgFormData: {},
				msgText: ''
			};
		}
	}
</script>

<style lang="scss">
.msg-contianer {
	display: flex;
	justify-content: center;
	align-items: center;
	.msg-content{
		width: 700rpx;
	}
}
</style>

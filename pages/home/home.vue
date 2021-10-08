<template>
	<view class="home-container">
		<view class="search">
			<uni-search-bar @confirm="search" @input="input"></uni-search-bar>
		</view>
		<view class="search-content">
		</view>
		<view class="home-content">
			<view v-for="(item,index) in 10" :key="index" class="home-content-item">
				
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			upper: function(e) {
				console.log(e)
			},
			lower: function(e) {
				console.log(e)
			},
			scroll: function(e) {
				console.log(e)
				this.old.scrollTop = e.detail.scrollTop
			},
			goTop: function(e) {
				this.scrollTop = this.old.scrollTop
				this.$nextTick(() => {
					this.scrollTop = 0
				});
				uni.showToast({
					icon:"none",
					title:"纵向滚动 scrollTop 值已被修改为 0"
				})
			}
		}
	}
</script>

<style lang="scss">
.home-content {
	background-color: #F0AD4E;
	display: flex;
	justify-content: center;
	align-items: center;
	.home-content-item {
		
	}
}
</style>

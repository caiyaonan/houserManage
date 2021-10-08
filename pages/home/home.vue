<template>
	<view class="home-container">
		<view class="search">
			<uni-search-bar @confirm="search" @input="input" @focus="focus" @blur="blur"></uni-search-bar>
		</view>
		<view v-if="isSearch" class="search-content">
		</view>
		<view class="screen-content">
			    <uni-data-picker class="screen-area" v-model="areaValue" :localdata="items" popup-title="地区选择" @change="onAreaChange" @nodeclick="onAreaNodeClick"></uni-data-picker>

		</view>
		<view v-if="!isSearch" class="home-content">
			<view v-for="(item,index) in 10" :key="index" class="home-content-item">
				<image src="../../static/img/house_1.jpg" mode="scaleToFill"></image>
				<view class="text-area">
					<view class="text-area-name  text-overflow">
						房屋名称
					</view>
					<view class="text-area-desc text-overflow">
						房屋描述描述描述描述描述描述描述描述描述描述描述描述描述描述
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import address from '@/static/address.json';
	
	export default {
		data() {
			return {
				isSearch: false,
				items: [],
				areaValue: '全部',
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
			},
			focus: function() {
				this.isSearch = true;
			},
			blur: function() {
				this.isSearch = false;
			},
			onAreaChange: function(e) {
				console.log(e)
			},
			onAreaNodeClick: function(e) {
				console.log(e)
			}
		},
		created() {
			console.log(address);
			this.items = address;
		}
	}
</script>

<style lang="scss">
.screen-content {
	margin-left: 10px;
	margin-bottom: 20px;
	display: flex;
	justify-content: center;
	align-items: left;
	flex-direction: column;
	.screen-area {
		// ma
		// width: 200rpx;
	}
}
.home-content {
	// background-color: #F0AD4E;
	display: flex;
	justify-content: center;
	align-items: center;
	flex-direction: column;
	.home-content-item {
		margin-bottom: 20rpx;
		width: 700rpx;
		height: 400rpx;
		border: 1px solid lightgray;
		border-radius: 20px;
		position: relative;
		image {
			border-radius: 20px;
			width: 100%;
			height: 100%;
		}
		.text-area {
			position: absolute;
			z-index: 2;
			bottom: 0px;
			width: 100%;
			border-bottom-left-radius: 20px;
			border-bottom-right-radius: 20px;
			background-color: #d4d4d470;
			.text-area-name {
				color: #4f4f4f;
				margin-left: 10px;
			}
			.text-area-desc {
				margin-left: 10px;
				font-size: 12px;
				line-height: 20px;
				height: 20px;
				color: #5f5f5f;
			}
		}
	}
}
</style>

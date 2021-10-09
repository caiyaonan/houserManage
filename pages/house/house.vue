<template>
	<view class="house-container">
		<view class="house-content">
			<view class="house-base">
				<view class="house-img">
					<image src="../../static/img/house_1.jpg" mode="scaleToFill"></image>
				</view>
				<view class="house-name">
					房屋名称
				</view>				
			</view>
			<view class="house-details">
				<view class="details-title">
					详细配置
				</view>
				<view class="details-list">
					<view class="details-item">
						<view class="details-item-label">
							房屋类型：
						</view>
						<view class="details-item-text">
							商品房
						</view>
					</view>
					
					<view class="details-item">
						<view class="details-item-label">
							房屋户型：
						</view>
						<view class="details-item-text">
							三室两厅一卫
						</view>
					</view>
					
					<view class="details-item">
						<view class="details-item-label">
							房屋面积：
						</view>
						<view class="details-item-text">
							120平方
						</view>
					</view>
					
					<view class="details-item">
						<view class="details-item-label">
							房屋楼层：
						</view>
						<view class="details-item-text">
							12楼
						</view>
					</view>
					
					<view class="details-item">
						<view class="details-item-label">
							房屋朝向：
						</view>
						<view class="details-item-text">
							坐北朝南
						</view>
					</view>
					
					<view class="details-item">
						<view class="details-item-label">
							装修情况：
						</view>
						<view class="details-item-text">
							毛坯
						</view>
					</view>
					
					<view class="details-item">
						<view class="details-item-label">
							配置设施：
						</view>
						<view class="details-item-text">
							无
						</view>
					</view>
					
					<view class="details-item">
						<view class="details-item-label">
							房屋年龄：
						</view>
						<view class="details-item-text">
							10年
						</view>
					</view>
					
					<view class="details-item">
						<view class="details-item-label">
							房屋产权：
						</view>
						<view class="details-item-text">
							70年
						</view>
					</view>
					
					<view class="details-item">
						<view class="details-item-label">
							联系方式：
						</view>
						<view class="details-item-text">
							138xxxxxxxx
						</view>
					</view>
				</view>
			</view>
		</view>
		
		<view class="msg-content">
			<view class="msg-header">
				<view class="msg-tit">
					留言列表
				</view>
				<view class="msg-btn">
					<button type="default" size="mini" @click="onMessage">发布留言</button>
				</view>
			</view>
			<view class="msg-body">
				<view class="msg-lsit">
					
					<view class="msg-item">
						<view class="msg-item-header">
							<view class="name">
								我爱吃苦瓜
							</view>
							<view class="publish-time">
								2021-10-09 12:00:00
							</view>
						</view>
						<view class="msg-item-content">
							这个房子还不错
						</view>
					</view>
					
					<view class="msg-item">
						<view class="msg-item-header">
							<view class="name">
								我爱吃西瓜
							</view>
							<view class="publish-time">
								2021-10-09 12:00:00
							</view>
						</view>
						<view class="msg-item-content">
							我也觉得这个房子还可以
						</view>
					</view>
					
					<view class="msg-item">
						<view class="msg-item-header">
							<view class="name">
								孙悟空
							</view>
							<view class="publish-time">
								2021-10-09 12:00:00
							</view>
						</view>
						<view class="msg-item-content">
							房子不错，知道还在不。
						</view>
					</view>
					
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods: {
			onMessage: function() {
				uni.navigateTo({
					url: '../message/message'
				})
			}
		}
	}
</script>

<style lang="scss">
.house-container {
	width: 750rpx;
	.house-content {
		width: 750rpx;
		margin-top: 10px;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		.house-base {
			width: 700rpx;
			font-size: 14px;
			image{
				border-radius: 20px;
				width: 100%;
			}
		}
		.house-details {
			width: 700rpx;
			margin-top: 10px;
			.details-title {
				font-size: 16px;
				font-weight: bold;
				line-height: 30px;
				height: 30px;
				// border-top: 1px dashed gray;
				border-bottom: 1px solid gray;
			}
			.details-list {
				margin-top: 10px;
				display: flex;
				flex-direction: row;
				flex-wrap: wrap;
				.details-item {
					width: 350rpx;
					line-height: 24px;
					height: 24px;
					display: flex;
					.details-item-label {
						font-size: 14px;
						font-weight: bold;
					}
					.details-item-text {
						font-size: 12px;
						color: gray;
					}
				}
			}
		}
	}
	
	.msg-content {
		margin-top: 20px;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		.msg-header {
			width: 700rpx;
			display: flex;
			justify-content: space-between;
			align-items: center;
			border-bottom: 1px solid gray;
			height: 40px;
			.msg-tit {
				font-size: 16px;
				font-weight: bold;
			}
			.msg-btn {
				width: 100px;
				height: 30px;
			}
		}
	
		.msg-body {
			margin-top: 20px;
			.msg-lsit {
				width: 700rpx;
				.msg-item {
					border-bottom: 1px dashed lightgray;
					margin-bottom: 20px;
					// height: 60px;
					.msg-item-header {
						display: flex;
						justify-content: space-between;
						height: 25px;
						font-size: 12px;
						color: gray;
					}
					.msg-item-content {
						font-size: 14px;
						line-height: 30px;
					}
				}
			}
		}
	}
}
</style>

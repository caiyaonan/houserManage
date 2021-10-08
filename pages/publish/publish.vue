<template>
	<view class="publish-container">
		<view class="publish-content">
		<uni-segmented-control :current="publishTypeCurrent" :values="publishTypeOptions" @clickItem="onClickItem" styleType="button" activeColor="#55aaff"></uni-segmented-control>
		<view class="content">
			<view class="rent-content" v-show="publishTypeCurrent === 0">
				<uni-forms ref="rentForm" :modelValue="rentFormData">
						<uni-forms-item label="地区" name="city">
							<uni-data-picker class="screen-area" v-model="areaValue" :localdata="items" popup-title="地区选择" @change="onAreaChange" @nodeclick="onAreaNodeClick"></uni-data-picker>
						</uni-forms-item>
						<uni-forms-item label="详细地址" name="address">
							<uni-easyinput type="text" placeholder="请输入详细地址" />
						</uni-forms-item>
						<uni-forms-item label="房屋类型" name="username">
							<uni-easyinput type="text" placeholder="请输入房屋类型" />
						</uni-forms-item>
						<uni-forms-item label="房屋户型" name="email">
							<uni-easyinput type="text" placeholder="请输入房屋户型" />
						</uni-forms-item>
						<uni-forms-item label="房屋面积" name="mobile">
							<uni-easyinput type="text" placeholder="请输入房屋面积" />
						</uni-forms-item>
						<uni-forms-item label="房屋楼层" name="password">
							<uni-easyinput type="text" placeholder="请输入房屋楼层" />
						</uni-forms-item>
						<uni-forms-item label="房屋朝向" name="confirm_password">
							<uni-easyinput type="text" placeholder="请输入房屋朝向" />
						</uni-forms-item>
						<uni-forms-item label="装修情况" name="confirm_password">
							<uni-easyinput type="text" placeholder="请输入装修情况" />
						</uni-forms-item>
						<uni-forms-item label="房屋设施" name="confirm_password">
							<uni-easyinput type="text" placeholder="请输入房屋设施" />
						</uni-forms-item>
						<uni-forms-item label="房屋年龄" name="confirm_password">
							<uni-easyinput type="text" placeholder="请输入房屋年龄" />
						</uni-forms-item>
						<uni-forms-item label="房屋产权" name="confirm_password">
							<uni-easyinput type="text" placeholder="请输入房屋产权" />
						</uni-forms-item>
						<uni-forms-item label="房屋租金" name="confirm_password">
							<uni-easyinput type="text" placeholder="请输入房屋租金" />
						</uni-forms-item>
						<uni-forms-item label="联系方式" name="confirm_password">
							<uni-easyinput type="text" placeholder="请输入联系方式" />
						</uni-forms-item>
					</uni-forms>
					<button @click="rentForm" size="mini">发布</button>
				</view>
			</view>
			<view class="sale-content" v-show="publishTypeCurrent === 1">
				
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				publishTypeCurrent: 0,
				publishTypeOptions: ['出租','出售']
			};
		},
		methods: {
			onClickItem: function(e) {
				console.log(e);
				this.publishTypeCurrent = e.currentIndex;
			}
		}
	}
</script>

<style lang="scss">
.publish-container{
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	.publish-content{
		width: 700rpx;
		.content{
			margin-top: 20px;
			.rent-content {
				display: flex;
				flex-direction: column;
			}
		}
	}
}
</style>

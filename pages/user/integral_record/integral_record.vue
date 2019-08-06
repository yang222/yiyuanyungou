<template>
	<view class="integral_record">
		<view class="remark">
			我的积分：<text class="color">0.00</text>
			<navigator url="" class="r">充值</navigator>
		</view>
		<view class="nodata">
			没有积分记录，赶快<navigator url="" class="color">去充值</navigator>吧!
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.integral_record{
	.remark{
		padding: 20upx 40upx;
		font-size: 24upx;
		.r{
			color: #ff4c42;
		}
	}
	.nodata{
		padding-top: 100upx;
		font-size: 24upx;
		color: #666;
		text-align: center;
		.color{display: inline;margin: 0 10upx;}
	}
}
</style>

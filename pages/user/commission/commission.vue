<template>
	<view class="commission">
		<view class="nodata">
			没有佣金记录，赶快<navigator url="../spread/spread" class="color">去邀请</navigator>吧!
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
.commission{
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

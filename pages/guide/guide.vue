<template>
	<view class="guide">
		<image src="../../static/images/xs2.png" mode="" class="img1"></image>
		<image src="../../static/images/xs1.png" mode="" class="img2"></image>
		<image src="../../static/images/xs3.png" mode="" class="img3"></image>
		<image src="../../static/images/xs4.png" mode="" class="img4" @tap="toshop"></image>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods:{
			toshop(){
				uni.switchTab({
					url:"../classify/classify"
				})
			}
		}
	}
</script>

<style lang="scss">
.guide{
	font-size: 0;
	image{
		width: 100%;
	}
	.img1{
		height: 1436upx;
	}
	.img2{
		height: 1438upx;
	}
	.img3{
		height: 1020upx;
	}
	.img4{
		height: 1516upx;
	}
}
</style>

<template>
	<view class="problem">
		<navigator url="../guide/guide">
			<image src="../../static/images/wt2.png" class="img1" mode=""></image>
		</navigator>
		<navigator url="problem_detail?wt=1">
			<image src="../../static/images/wt3.png" class="img2"  mode=""></image>
		</navigator>
		<navigator url="problem_detail?wt=2">
			<image src="../../static/images/wt4.png" class="img3" mode=""></image>
		</navigator>
		<navigator url="../lucky/lucky">
			<image src="../../static/images/wt5.png" class="img4" mode=""></image>
		</navigator>
		<navigator url="problem_detail?wt=4">
			<image src="../../static/images/wt6.png" class="img5" mode=""></image>
		</navigator>
		<navigator url="problem_detail?wt=4">
			<image src="../../static/images/wt7.png" class="img6" mode=""></image>
		</navigator>
		<image src="../../static/images/wt1.png" class="img7" mode=""></image>
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
.problem{
	font-size: 0;
	image{width: 100%;}
	.img1{
		height: 158.4upx;
	}
	.img2{
		height: 48.84upx;
	}
	.img3{
		height: 56.76upx;
	}
	.img4{
		height: 51.48upx;
	}
	.img5{
		height: 50.16upx;
	}
	.img6{
		height: 157.08upx;
	}
	.img7{
		height: 1421.64upx;
	}
}
</style>

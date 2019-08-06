<template>
	<view class="nodata">{{text}}</view>
</template>

<script>
export default{
	data(){
		return{
			
		}
	},
	props:["text"],
}
</script>
<style>
	.nodata{
		font-size: 24upx;
		color: #999;
		text-align: center;
		padding-top: 100upx;
	}
</style>

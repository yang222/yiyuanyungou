<template>
	<view class="problem_detail">
		<view class="detail" v-if="wt == 1">
			活动的所有商品均为一元云购平台确认的第三方商家提供及发货，100%正品，可享受厂家所提供的全国联保服务。
		</view>
		<view class="detail" v-if="wt == 2">
			若某件商品的云购号码从开始分配之日起60天未分配完毕，则一元云购有权取消该件商品的云购活动，并向参与的用户退还云购币，所退还云购币将在3个工作日内退还至用户账户中。
		</view>
		<view class="" v-if="wt == 4">
			<image src="../../static/images/wt8.png" mode=""></image>
		</view>
	</view>
</template>

<script>
export default{
	data(){
		return{
			wt:"",
		}
	},
	onLoad(options) {
		this.wt = options.wt;
	}
}
</script>

<style lang="scss">
.problem_detail{
	.detail{
		padding: 30upx;
		font-size: 28upx;
		color: #666;
		
	}
	image{
		width: 100%;
		height: 568upx;
	}
}
</style>

<template>
	<view class="address">
		<nodata :text="text" v-if="newlist.length == 0"></nodata>
		<view class="address-list" v-else>
			<view class="address-item" @tap="change">
				<view class="tit">
					<text class="name l">杨凯</text>
					<text class="tel r">18300708738</text>
				</view>
				<view class="cont">
					<text class="def">[默认]</text>广东省 深圳市 宝安区 西乡街道麻布新村12箱子
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import nodata from "../../../component/nodata.vue";
	export default {
		components:{
			nodata
		},
		data() {
			return {
				text:"暂无收货地址！",
				newlist:["1"],
			}
		},
		onNavigationBarButtonTap(e) {
			uni.navigateTo({
				url:"add_address"
			})
		},
		methods: {
			change(){
				uni.navigateTo({
					url:"add_address?id=1"
				})
			}
		}
	}
</script>

<style lang="scss">
.address{
	.address-list{
		.address-item{
			border-bottom: 1upx solid #eee;
			padding: 20upx;
			cursor: pointer;
			.tit{
				height: 60upx;
				line-height: 60upx;
				font-size: 30upx;
				.name{
					color: #233;
				}
				.tel{
					color: #666;
				}
			}
			.cont{
				font-size: 28upx;
				color: #999;
				padding-top: 10upx;
				.def{
					color: #FF4C42;
					margin-right: 10upx;
				}
			}
		}
	}
}
</style>

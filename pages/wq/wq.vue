<template>
	<view class="wq">
		<view class="scroll_bottom_list">
			<view class="recorded">
				<view class="recorded-tit">
					<navigator url="../item_detail/item_end">期号：1907300013(揭晓时间：2019-08-02 13:28:15)</navigator>
				</view>
				<view class="recorded-cont">
					<view class="img">
						<image src="../../static/images/cz.png" mode=""></image>
					</view>
					<view class="content">
						<view class="name">获奖者：<text class="b_color">养家</text></view>
						<view class="address">(河北省邯郸市武安县IP：110.248.142.101)</view>
						<view class="id"> 用户ID：431538(唯一不变标识)</view>
						<view class="num">幸运号码：<text class="color">100045485</text></view>
					</view>
				</view>
			</view>
			<view class="recorded">
				<view class="recorded-tit">
					<navigator url="../item_detail/item_end">期号：1907300013(揭晓时间：2019-08-02 13:28:15)</navigator>
				</view>
				<view class="recorded-cont">
					<view class="img">
						<image src="../../static/images/cz.png" mode=""></image>
					</view>
					<view class="content">
						<view class="name">获奖者：<text class="b_color">养家</text></view>
						<view class="address">(河北省邯郸市武安县IP：110.248.142.101)</view>
						<view class="id"> 用户ID：431538(唯一不变标识)</view>
						<view class="num">幸运号码：<text class="color">100045485</text></view>
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
				
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
.wq{
	.scroll_bottom_list{
		padding: 20upx;
	}
	.recorded{
		border: 1px solid #eee;
		margin-bottom: 20upx;
		.recorded-tit{
			height: 55upx;
			line-height: 55upx;
			background: #eee;
			color: #6e7d8b;
			font-size: 26upx;
			padding:  0 20upx
		}
		.recorded-cont{
			display: flex;
			padding:20upx;
			.img{
				width: 120upx;
				image{
					width: 100upx;
					height: 100upx;
					border-radius: 50%;
				}
			}
			.content{
				flex: 1;
				font-size: 28upx;
				color: #666;
				view{margin-bottom: 10upx;}
				.name{
					font-size: 28upx;
					color: #666;
				}
				.address{
					color: #528d00;
				}
			}
		}
	}
}
</style>

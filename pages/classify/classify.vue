<template>
	<view class="classify">
		<view class="classify_list">
			<text>手机数码</text>
			<text>手机数码</text>
			<text>手机数码</text>
			<text>手机数码</text>
			<text>手机数码</text>
			<text>手机数码</text>
			<text>手机数码</text>
			<text>手机数码</text>
			<text>手机数码</text>
			<text>手机数码</text>
		</view>
		<view class="item_nav">
			<view class="nav active">人气商品</view>
			<view class="nav">最新上架</view>
			<view class="nav">即将满员</view>
			<view class="nav">总需人次 <view class="px"><text class="top">升</text><text class="bot">降</text></view></view>
		</view>
		<view class="items">
			<view class="item-cont">
				<view class="imgs"></view>
				<view class="name">
					<navigator url="../hello/hello" open-type="navigate">
					     苹果iPhone XR 64GB全网通6.1英寸双卡双待4G手机 （颜色随机）
					</navigator>
				</view>
				<view class="prog">
					<view class="porgress">
						<text>购买进度 <text class="bf">11.3%</text></text>
						<view class="bg">
							<view class="cover"></view>
						</view>
					</view>
					<view class="cart">加购物车</view>
				</view>
			</view>
			<view class="item-cont">
				<view class="imgs"></view>
				<view class="name">
					<navigator url="../hello/hello" open-type="navigate">
					     苹果iPhone XR 64GB全网通6.1英寸双卡双待4G手机 （颜色随机）
					</navigator>
				</view>
				<view class="prog">
					<view class="porgress">
						<text>购买进度 <text class="bf">11.3%</text></text>
						<view class="bg">
							<view class="cover"></view>
						</view>
					</view>
					<view class="cart">加购物车</view>
				</view>
			</view>
		</view>
		<view class="line"></view>
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
.classify{
	.classify_list{
		font-size: 0;
		text-align: center;
		padding: 20upx 0 0;
		border-bottom: 1upx solid #eee;
		text{
			display: inline-block;
			vertical-align: top;
			width: 17%;
			margin: 0 1.5%;
			font-size: 24upx;
			height: 60upx;
			line-height: 60upx;
			border-radius: 20upx;
			background: #ff4c42;
			color: #fff;
			margin-bottom: 20upx;
		}
	}
	.item_nav{
		text-align: center;
		height: 80upx;
		line-height: 80upx;
		border-bottom: 1upx solid #eee;
		.nav{
			padding: 0upx 15upx;
			vertical-align: top;
			height: 80upx;
			display: inline-block;
			font-size: 30upx;
			color: #000;
			box-sizing: border-box;
			margin: 0 10upx;
			&.active{
				color: #ea4c4d;
				border-bottom: 4upx solid #ea4c4d;
			}
			.px{
				display: inline-block;
				height: 100%;
				width: 40upx;
				vertical-align: top;
				text{
					display: block;
					line-height: 40upx;
					height: 40upx;
					font-size: 24upx;
				}
			}
		}
	}
	.items{
		font-size: 0;
		text-align: left;
		background: #fff;
		.item-cont{
			padding: 20upx;
			display: inline-block;
			width: 50%;
			box-sizing: border-box;
			border-right: 1upx solid #eee;
			border-bottom: 1upx solid #eee;
			&:nth-child(2){
				border-right: none;
			}
			.imgs{
				height: 300upx;
				text-align: center;
				image{height: 100%;}
			}
			.name{font-size: 28upx;color: #000;line-height: 40upx;height: 80upx;overflow: hidden;padding: 6upx 0;}
			.prog{
				display: flex;
				padding-top: 10upx;
				.porgress{
					flex: 1;
					padding-right: 30upx;
					text{font-size: 0.32upx;color: #333;
						.bf{color: #119bfb;}
					}
					.bg{
						height: 16upx;
						margin-top: 6upx;
						background: #ddd;
						border-radius: 6upx;
						overflow: hidden;
						position: relative;
						.cover{
							position: absolute;
							height: 16upx;
							top: 0;
							left: 0;
							background: linear-gradient(left,#fcca37,#fc8a37);
							transition: width 1s ease;
							width: 11.3%;
	
						}
					}
						
				}
				.cart{
					width: 120upx;
					height: 56upx;
					line-height: 56upx;
					text-align: center;
					border: 1upx solid #ea4c4d;
					border-radius: 6upx;
					font-size: 24upx;
					color: #ea4c4d;
				}
			}
		}
	}
}
</style>

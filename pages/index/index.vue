<template>
	<view class="index">
		<view class="page-section swiper">
			<view class="page-section-spacing">
				<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration" indicator-color="#fff" indicator-active-color="#ea4c4d">
					<swiper-item>
						<view class="swiper-item">
							<image src="../../static/images/bzqf.png" mode=""></image>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							<image src="../../static/images/iphoex.png" mode=""></image>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							<image src="../../static/images/xyzp.png" mode=""></image>
						</view>
					</swiper-item>
				</swiper>
			</view>
		</view>
		<view class="lists">
			<view class="list_item">
				<navigator url="../guide/guide">
					<image src="../../static/images/xs.png" mode=""></image>
					<text>新手指引</text>
				</navigator>
			</view>
			<view class="list_item" @tap="tojb">
				<image src="../../static/images/xr.png" mode=""></image>
				<text>金币专区</text>
			</view>
			<view class="list_item">
				<navigator url="../recharge/recharge">
				<image src="../../static/images/cz.png" mode=""></image>
				<text>充100送100</text>
				</navigator>
			</view>
			<view class="list_item">
				<image src="../../static/images/yq.png" mode=""></image>
				<text>推广赚钱</text>
			</view>
			<view class="list_item">
				<navigator url="../problem/problem">
				<image src="../../static/images/wt.png" mode=""></image>
				<text>常见问题</text>
				</navigator>
			</view>
			<view class="list_item">
				<navigator url="../see/see">
					<image src="../../static/images/mj.png" mode=""></image>
					<text>一定要看</text>
				</navigator>
				
			</view>
			<view class="list_item">
				<image src="../../static/images/xz.png" mode=""></image>
				<text>下载APP</text>
			</view>
			<view class="list_item">
				<navigator url="../problem/problem">
				<image src="../../static/images/kf.png" mode=""></image>
				<text>联系客服</text>
				</navigator>
			</view>
		</view>
		<view class="page-zj swiper">
			<view class="lb">
				<image src="../../static/images/toutiao_6efe7c3.png" mode=""></image>
			</view>
			<view class="page-section-spacing">
				<swiper class="swiper" :indicator-dots="false" :circular="true" :autoplay="true" :interval="3000" :duration="500">
					<swiper-item>
						<view class="swiper-item">
							某某某中了啥<text>奖励某某某</text> 中了啥奖励某某某中了啥奖励某某某中了啥奖励某某某中了啥奖励
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							某某某中<text>奖励某某某</text> 了啥奖励
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							某某某中<text>奖励某某某</text> 了啥奖励
						</view>
					</swiper-item>
				</swiper>
			</view>
		</view>
		<view class="line"></view>
		<view class="nearprize-list">
			<view class="nearprize-item" @tap="toend">
				<view class="imgs">
					<image src="" mode=""></image>
				</view>
				<view class="item_name">小米对讲机</view>
				<view class="user_name">坑爹啊222</view>
				<view class="user_order">111554454</view>
			</view>
			<view class="nearprize-item">
				<view class="imgs">
					<image src="" mode=""></image>
				</view>
				<view class="item_name">小米对讲机</view>
				<view class="user_name">坑爹啊222</view>
				<view class="user_order">111554454</view>
			</view>
			<view class="nearprize-item">
				<view class="imgs">
					<image src="" mode=""></image>
				</view>
				<view class="item_name">小米对讲机</view>
				<view class="user_name">坑爹啊222</view>
				<view class="user_order">111554454</view>
			</view>
		</view>
		<view class="item_nav">
			<view class="nav active">人气商品</view>
			<view class="nav">最新上架</view>
			<view class="nav">即将满员</view>
			<view class="nav">总需人次 <view class="px"><text class="top iconfont iconGroup-"></text><text class="bot iconfont iconGroup-"></text></view></view>
		</view>
		<view class="items">
			<view class="item-cont">
				<view class="imgs" @tap="todetail"></view>
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
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500
			}
		},
		onNavigationBarButtonTap(e) {
			if(e.text == "分类"){
				uni.switchTab({
					url:"../classify/classify"
				})
			}
		},
		onLoad() {

		},
		methods: {
			toindex2(){
				uni.navigateTo({
					url: 'index2'
				});
			},
			todetail(){
				uni.navigateTo({
					url: '../item_detail/item_detail'
				});
			},
			tojb(){
				uni.switchTab({
					url:"../classify/classify"
				})
			},
			toend(){
				uni.navigateTo({
					url: '../item_detail/item_end'
				});
			},

		}
	}
</script>
<style lang="scss">
.index{
	.page-section{
		height: 350upx;
		.page-section-spacing{height: 100%;}
		.uni-swiper-dot-active{
			background: #ea4c4d;
		}
		uni-swiper{
			height: 100% !important;
		}
	}
	.swiper-item{
		height: 100%;
		image{width: 100%;height: 100%}
	}
	.line{height: 20upx;background: #eee;width: 100%;}
	.lists{
		font-size: 0;
		border-bottom: 1upx solid #eee;
		.list_item{
			display: inline-block;
			vertical-align: top;
			padding: 10upx 0;
			text-align: center;
			width: 25%;
			image{
				width: 80upx;
				height: 80upx;
			}
			text{font-size: 24upx;color: #000;display: block;padding-top: 10upx;}
		}
	}
	.page-zj{
		padding-left: 80upx;
		border-bottom: 1upx solid #eee;
		height: 70upx;
		line-height: 70upx;
		padding-right: 20upx;
		position: relative;
		.swiper,.page-section-spacing{height: 100%;}
		.swiper-item{
			height: 100%;
			font-size: 24upx;text-overflow: ellipsis;white-space: nowrap;overflow: hidden;color: #000;
			text{
				color: #119bfb;
			}
		}
		.lb{
			width: 70upx;
			height: 70upx;
			position: absolute;
			top: 0;
			left: 10upx;
			text-align: center;
			image{height: 50upx;width: 50upx;margin-top: 10upx;}
		}
	}
	.nearprize-list{
		font-size: 0;
		border-bottom:1upx solid #eee;
		.nearprize-item{
			display: inline-block;
			width: 33.3%;
			vertical-align: top;
			box-sizing: border-box;
			border-right: 1upx solid #eee;
			&:last-child{
				border: none;
			}
			padding: 10upx 16upx;
			.imgs{
				text-align: center;
				height: 120upx;
				image{height: 100%;}
			}
			.item_name{font-size: 28upx;text-align: left;color: #000;padding: 4upx 0;text-overflow: ellipsis;overflow: hidden;white-space: nowrap;}
			.user_name{font-size: 28upx;text-align: left;color: blue;padding: 4upx 0; text-overflow: ellipsis;overflow: hidden;white-space: nowrap;}
			.user_order{font-size: 24upx;text-align: left;color: #ea4c4d;padding: 4upx 0;}
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
					font-size: 32upx;
				}
				.bot{
					transform: rotate(180deg);
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

<template>
	<view class="lucky">
		<view class="guide-info">
			<ul>
				<li>幸运<br>号码</li>
				<li>=</li>
				<li class="li_3">
					<view class="halfline">数值<span class="guide-single">A</span></view>
					<view>商品总需人<span class="guide-single">数</span> </view>
				</li>
				<li>
					<span class="guide-quote">(</span><br>取<br>余<br>数<br><span class="guide-quote">)</span>
				</li>
				<li>+</li>
				<li>10000001</li>
			</ul>
		</view>
		<view class="line"></view>
		<view class="guide-list">
			<view class="guide-title">
				<span class="guide-single">A</span>
				<span class="guide-charequals">=</span>
				截至该商品开奖时间点前全站最后50个参与记录的时间数值之和
			</view>
			<view class="guide-desc">
				<span class="guide-charequals">=</span>
				<span class="primary-cnt">5361876706</span>
				<span class="guide-btn b_color">展开↓</span>
			</view>
		</view>
		<view class="lists">
			<view class="list-tit">
				<text class="l">下单时间</text>
				<text class="r">用户账户</text>
			</view>
			<view class="list-cont">
				<view class="time">
					2019-15-15 15:15:15 <text class="color">→ 110935025</text>
				</view>
				<view class="name">yg佛法无边无量</view>
			</view>
			<view class="list-cont">
				<view class="time">
					2019-15-15 15:15:15 <text class="color">→ 110935025</text>
				</view>
				<view class="name">yg佛法无边无量</view>
			</view>
		</view>
		<view class="line"></view>
		<view class="guide-list">
			<view class="guide-title">
				<span class="guide-single">数</span>
				<span class="guide-charequals">=</span>
				商品总需人数
			</view>
			<view class="guide-desc">
				<span class="guide-charequals">=</span>
				<span class="primary-cnt">3188</span>
			</view>
		</view>
		<view class="line"></view>
		<view class="guide-result">
			<view class="tit">计算结果</view>
			<view class="result">10001823</view>
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
.uni-body{
	background: #eee;
}
.lucky{
	.guide-info{
		background: #fff;
		overflow: hidden;
		padding: 40upx 0;
		text-align: center;
		font-size: 32upx;
		position: relative;
		ul,li{
			list-style: none;
			padding: 0;
		}
		li{
			display: inline-block;
			vertical-align: top;
			height: 128upx;
			line-height: 128upx;
			&:first-child{
				line-height: 128upx;
				color: #fff;
				width:128upx;
				vertical-align: middle;
				padding: 20upx;
				font-size: 32upx;
				box-sizing: border-box;
				letter-spacing: 10upx;
				border-radius: 6upx;
				background: #ff4c42;
				line-height: 46upx;
			}
			&:nth-child(2){
				padding: 0 10upx;
			}
			&:nth-child(6){
				color: #ff4c42;
			}
			&:nth-child(4){
					line-height: 28upx;
					padding: 0 20upx;
					font-size: 24upx;
					.guide-quote{
						transform: rotate(90deg) translateY(-.08rem);
						display: inline-block;
					}
			}
			&.li_3{
				border: 1upx dotted #ddd;
				line-height: 62upx;
				font-size: 28upx;
				padding:  0 20upx;
				.halfline{
					border-bottom: 1px solid #ddd;
				}
				.guide-single{
					display: inline-block;
					width: 45upx;
					height: 45upx;
					line-height: 45upx;
					border-radius: 50%;
					background: #ff4c42;
					color: #fff;
					margin-left: 10upx;
				}
			}
		}
	}
	.guide-list{
		padding: 0 30upx;
		border-bottom: 1upx solid #eee;
		.guide-title{
			font-size: 28upx;
			color: #666;
			padding: 20upx 0;
			border-bottom: 1px solid #eee;
			.guide-single{
				display: inline-block;
				width: 45upx;
				height: 45upx;
				line-height: 45upx;
				background: #ff4c42;
				color: #fff;
				text-align: center;
				border-radius: 50%;
				
			}
		}
		.guide-charequals{
			font-size: 32upx;
			margin: 0 10upx;
		}
		.guide-desc{
			padding:20upx 0;
			color: #666;
			font-size: 30upx;
			padding-left: 50upx;
			
			.primary-cnt{
				color: #ff4c42;
			}
			.guide-btn{
				margin-left: 10upx;
			}
			
		}
		
	}
	.lists{
		.list-tit{
			height: 60upx;
			line-height: 60upx;
			border-bottom: 1upx solid #eee;
			font-size: 30upx;
			padding: 0 20upx;
		}
		.list-cont{
			display: flex;
			height: 60upx;
			line-height: 60upx;
			padding: 0 20upx;
			border-bottom: 1px solid #eee;
			.time{
				flex: 1;
				font-size: 24upx;
				color: #999;
				.color{
					font-weight: 600;
				}
			}
			.name{
				width: 300upx;
				font-size: 28upx;
				color: #999;
				text-align: right;
			}
		}
	}
	.guide-result{
		.tit{
			font-size: 32upx;
			padding: 20upx;
			padding-left: 50upx;
		}
		.result{
			color: #ff4c42;
			padding: 20upx;
			text-align: center;
		}
	}
}
</style>

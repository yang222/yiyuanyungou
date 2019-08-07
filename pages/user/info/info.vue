<template>
	<view class="info">
		<view class="list">
			<view class="item awa">
				头像
				<view class="img">
					<image src="../../../static/images/cz.png" mode=""></image>
				</view>
			</view>
			<view class="item">
				用户ID
				<view class="id">
					4788525
				</view>
			</view>
			<view class="item">
				昵称
				<view class="id b_color" @tap="isshow=true">
					大柚子
				</view>
			</view>
			<view class="item">
				手机号
				<view class="id b_color">
					1824488445
				</view>
			</view>
			<view class="item">
				<navigator url="../address/address">
					我的收货地址
					<view class="more iconfont iconyou-">
						
					</view>
				</navigator>
			</view>
		</view>
		<view class="lay" v-show="isshow">
			<view class="lay_cont">
				<view class="tit">请输入您的新昵称</view>
				<view class="content">
					<input type="text" value="" placeholder="新昵称" />
				</view>
				<view class="btn">
					<view class="cancel" @tap="isshow=false">取消</view>
					<view class="sure">确认</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isshow:false,
			};
		}
	}
</script>

<style lang="scss">
.info {
	.list{
		.item{
			font-size: 28upx;
			padding: 0 30upx;
			height: 80upx;
			line-height:80upx;
			border-bottom: 1upx solid #ddd;
			&.awa{
				height: 140upx;
				line-height: 140upx;
			}
			.img{
				float: right;
				width: 120upx;
				height: 120upx;
				border-radius: 10upx;
				margin-top: 10upx;
				overflow: hidden;
				image{
					width: 100%;
					height: 100%;
				}
			}
			.id{
				float: right;
			}
			.more{
				float: right;
				font-size: 40upx;
			}
		}
	}
	.lay{
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(0,0,0,0.6);
		.lay_cont{
			position: absolute;
			width: 60%;
			top: 50%;
			left: 50%;
			transform: translate(-50%,-50%);
			background: #fff;
			border-radius: 10upx;
			.tit{
				height: 70upx;
				line-height: 70upx;
				color: #666;
				border-bottom: 1upx solid #ddd;
				text-align: center;
				font-size: 30upx;
			}
			.content{
				padding: 30upx;
				input{
					height: 70upx;
					line-height: 70upx;
					border: 1upx solid #ddd;
					margin:  0 auto;
					padding-left: 10upx;
					text-align: left;
					font-size: 28upx;
					width: 300upx;
				}
				border-bottom: 1upx solid #ddd;
			}
			.btn{
				display: flex;
				height: 70upx;
				line-height: 70upx;
				text-align: center;
				view{
					flex: 1;
					font-size: 28upx;
					&.cancel{
						color: #666;
						border-right: 1upx solid #ddd;
					}
					&.sure{
						color: #ff4c42;
					}
				}
			}
		}
	}
}
</style>

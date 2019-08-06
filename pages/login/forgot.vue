<template>
	<view class="login">
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isopen:false,
				form:{
					acc:"",
					pw:""
				}
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	body{
		background: #eee;
		height:100%;
	}
	uni-page-body{
		height: 100%;
	}
	.login{
		height: 100%;
		position: relative;
		background: rgba(234,76,77,0.8);
		.oth{
			position: absolute;
			bottom: 60upx;
			left: 0;
			width: 100%;
			box-sizing: border-box;
			height: 40upx;
			padding: 0 60upx;
			line-height: 40upx;
			.left{
				float: left;
				color: #eee;
				font-size: 28upx;
			}
			.right{
				float: right;
				color: #eee;
				font-size: 28upx;
			}
		}
		.form{
			padding: 60upx;
			padding-top: 60upx;
			position: absolute;
			top: 40%;
			left: 50%;
			box-sizing: border-box;
			border-radius: 10upx;
			width: 90%;
			background: #fff;
			transform: translate(-50%,-50%);
			.form-item{
				display: flex;
				height: 70upx;
				margin-bottom: 20upx;
				border-bottom: 1upx solid #eee;
				position: relative;
				image{width: 40upx;height: 40upx;margin-top: 15upx;}
				.uni-input{flex: 1;margin-left: 20upx;font-size: 28upx;line-height: 70upx;height: 70upx;border: none;background: none;outline: none;}
				.eye{
					position:absolute;
					height: 70upx;
					width: 70upx;
					background: url("../../static/images/eye.png") no-repeat center center;
					background-size: 49upx  30upx;
					top: 0;
					right: 0;
					&.act{
						background: url("../../static/images/open_eye.png") no-repeat center center;
						background-size: 49upx  30upx;
					}
				}
				.i_code{
					position: absolute;
					top: 0;
					right: 0;
					height: 70upx;
					width: 200upx;
					font-size: 28upx;
					text-align: center;
				}
				.g_code{
					position: absolute;
					top: 6upx;
					right: 0;
					height: 56upx;
					width: 200upx;
					border-radius: 6upx;
					line-height: 56upx;
					background: #ea4c4d;
					color: #fff;
					font-size: 28upx;
					text-align: center;
				}
			}
			.btn{margin-top: 80upx;height: 70upx;line-height: 70upx;font-size: 32upx;}
			
		}
	}
</style>

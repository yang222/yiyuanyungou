<template>
	<view class="login">
		<view class="login_de" v-if="istype == 1">
			<view class="form">
				<view class="form-item">
					<image src="../../static/images/acc.png" mode=""></image>
					<input class="uni-input" type="number" v-model="form.acc" maxlength="11" placeholder="账户" />
				</view>
				<view class="form-item">
					<image src="../../static/images/pw.png" mode=""></image>
					<input class="uni-input" :type="isopen?'text':'password'" v-model="form.pw" maxlength="10" placeholder="密码"  />
					<text class="eye" :class="{'act':isopen}" @tap="isopen= !isopen"></text>
				</view>
				<button type="warn" class="btn">登录</button>
			</view>
			<view class="oth">
				<text @tap="check(3)" class="left">免费注册</text>
				<text @tap="check(2)"  class="right">忘记密码?</text>
			</view>
		</view>
		<view class="forgot" v-if="istype == 2">
			<view class="form">
				<view class="form-item">
					<image src="../../static/images/acc.png" mode=""></image>
					<input class="uni-input" type="number" v-model="form.acc" maxlength="11" placeholder="请输入手机号" />
				</view>
				<view class="form-item">
					<image src="../../static/images/pw.png" mode=""></image>
					<input class="uni-input" :type="isopen?'text':'password'" v-model="form.pw" maxlength="10" placeholder="请输入新密码"  />
					<text class="eye" :class="{'act':isopen}" @tap="isopen= !isopen"></text>
				</view>
				<view class="form-item">
					<image src="../../static/images/code.png" mode="" style="height: 50upx;"></image>
					<input class="uni-input" :type="isopen?'text':'password'" v-model="form.pw" maxlength="4" placeholder="请输入图形验证码"  />
					<text class="i_code">45654</text>
				</view>
				<view class="form-item">
					<image src="../../static/images/code.png" mode="" style="height: 50upx;"></image>
					<input class="uni-input" :type="isopen?'text':'password'" v-model="form.pw" maxlength="4" placeholder="收到的验证码"  />
					<text class="g_code">获取验证码</text>
				</view>
				<button type="warn" class="btn">修改密码</button>
			</view>
			<view class="oth">
				<text @tap="check(1)" class="left">马上登录</text>
				<text @tap="check(3)" class="right">立即注册！</text>
				
			</view>
		</view>
		<view class="register" v-if="istype == 3">
			<view class="form">
				<view class="form-item">
					<image src="../../static/images/acc.png" mode=""></image>
					<input class="uni-input" type="number" v-model="form.acc" maxlength="11" placeholder="手机注册" />
				</view>
				<view class="form-item">
					<image src="../../static/images/pw.png" mode=""></image>
					<input class="uni-input" :type="isopen?'text':'password'" v-model="form.pw" maxlength="10" placeholder="请输入密码"  />
					<text class="eye" :class="{'act':isopen}" @tap="isopen= !isopen"></text>
				</view>
				<view class="form-item">
					<image src="../../static/images/code.png" mode="" style="height: 50upx;"></image>
					<input class="uni-input" :type="isopen?'text':'password'" v-model="form.pw" maxlength="4" placeholder="请输入图形验证码"  />
					<text class="i_code">45654</text>
				</view>
				<view class="form-item">
					<image src="../../static/images/code.png" mode="" style="height: 50upx;"></image>
					<input class="uni-input" :type="isopen?'text':'password'" v-model="form.pw" maxlength="4" placeholder="请输入短信验证码"  />
					<text class="g_code">获取验证码</text>
				</view>
				<button type="warn" class="btn">注册</button>
			</view>
			<view class="oth">
				<text @tap="check(1)" class="left">马上登录</text>
				<text @tap="check(2)" class="right">忘记密码?</text>
				
			</view>
		</view>
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
				},
				istype:1,
			}
		},
		methods: {
			check(type){
				this.istype = type;
			}
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
		background: #f7f7f7;
		.login_de{
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
					color: #ff4c42;
					font-size: 28upx;
				}
				.right{
					float: right;
					color: #ff4c42;
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
				}
				.btn{margin-top: 80upx;height: 70upx;line-height: 70upx;font-size: 32upx;}
				
			}
		}
		.forgot{
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
					color: #ff4c42;
					font-size: 28upx;
				}
				.right{
					float: right;
					color: #ff4c42;
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
		.register{
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
					color: #ff4c42;
					font-size: 28upx;
				}
				.right{
					float: right;
					color: #ff4c42;
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
	}
</style>

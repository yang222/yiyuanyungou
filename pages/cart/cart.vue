<template>
	<view>
		<login></login>
	</view>
</template>

<script>
	import login from "../login/login"
	export default {
		components: {
			login
		},
		data() {
			return {
				islogin:false,
			}
		},
		onLoad() {
			const value = uni.getStorageSync('id');
			if(!value){
				this.islogin = true;
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
body{
	height:100%;
}
uni-page-body{
	height: 100%;
	uni-view{
		height: 100%;
	}
}
</style>

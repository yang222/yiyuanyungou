<template>
	<view>
		<nodata :text="text"></nodata>
	</view>
</template>

<script>
	import nodata from"../../../component/nodata.vue"
	export default {
		components:{
			nodata
		},
		data() {
			return {
				text:"没有通知消息！"
			};
		}
	}
</script>

<style lang="scss">

</style>

<template>
	<view>
		<view class="header">
			<view class="bg"></view>
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

<style>
	.bg {
		width: 100%;
		height: 257px;
		background-image: url(../../static/play/15.png);
		background-size: 100% 257px;
		overflow: hidden;
		z-index: 0;
	}

	.header {
		height: 25px;
		background: #E5E5E5;
		font-size: 12px;
		text-align: center;
		line-height: 25px;
		font-weight: 400;
		color: rgba(55, 59, 65, 1);
		z-index: 9999;
		position: static;
	}
</style>

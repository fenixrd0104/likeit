<template>
	<view class="bg">
		<view class="bg1">
			
		</view>
		<u-switch v-model="checked" :loading="loading"></u-switch>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				checked: true,
				loading: false,
				// 中间变量，避免在watch中多次回调，造成无限循环
				controlStatus: false
			};
		},
		watch: {
			checked(val) {
				// 等于false，意味着用户手动关闭了switch
				if (val == false) {
					if (this.controlStatus == true) {
						this.controlStatus = false;
						return;
					}
					// 重新打开switch，并让它处于加载中的状态
					this.checked = true;
					this.loading = true;
					// 模拟向后端发起请求
					this.getRestultFromServer();
				}
			}
		},
		methods: {
			// switch打开或者关闭时触发，值为true或者false
			change(status) {
				// console.log(status);
			},
			getRestultFromServer() {
				// 通过定时器模拟向后端请求
				setTimeout(() => {
					this.controlStatus = true;
					// 后端允许用户关闭switch，设置checked为false，结束loading状态
					this.loading = false;
					this.checked = false;
				}, 1500);
			}
		}
	};
</script>
<style>
	.bg {
		width: 100vw;
		height: 50px;
		position: absolute;
		background-color: #f8c750;
	}
	.bg1 {
		width: 20vw;
		height: 50px;
		position: absolute;
		background-color: #000000;
	}
</style>

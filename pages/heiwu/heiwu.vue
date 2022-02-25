<template>
	<view class="u-wrap">
		<view class="taobao">
			<view class="ticket">
				<view class="left">
					<image class="picture" src="/static/image/service_user.png" mode="widthFix"></image>
					<view class="introduce">
						<view class="top">
							剩余天数84天
						</view>
						<view class="type">1913566XXXXXX</view>
						<view class="date u-line-1"></view>
						<text class="big">拉黑处罚:</text>
					</view>
				</view>
				<view class="right">
					<view class="use immediate-use" :round="true">封禁中</view>
				</view>

			</view>
		</view>
		<view class="taobao">
			<view class="ticket">
				<view class="left">
					<image class="picture" src="/static/image/service_user.png" mode="widthFix"></image>
					<view class="introduce">
						<view class="top">
							剩余天数84天
						</view>
						<view class="type">1913566XXXXXX</view>
						<view class="date u-line-1"></view>
						<text class="big">拉黑处罚:</text>
					</view>
				</view>
				<view class="right">
					<view class="use immediate-use" :round="true">封禁中</view>
				</view>
		
			</view>
		</view>
		<view class="taobao">
			<view class="ticket">
				<view class="left">
					<image class="picture" src="/static/image/service_user.png" mode="widthFix"></image>
					<view class="introduce">
						<view class="top">
							剩余天数84天
						</view>
						<view class="type">1913566XXXXXX</view>
						<view class="date u-line-1"></view>
						<text class="big">拉黑处罚:</text>
					</view>
				</view>
				<view class="right">
					<view class="use immediate-use" :round="true">封禁中</view>
				</view>
		
			</view>
		</view>
		<view class="taobao">
			<view class="ticket">
				<view class="left">
					<image class="picture" src="/static/image/service_user.png" mode="widthFix"></image>
					<view class="introduce">
						<view class="top">
							剩余天数84天
						</view>
						<view class="type">1913566XXXXXX</view>
						<view class="date u-line-1"></view>
						<text class="big">拉黑处罚:</text>
					</view>
				</view>
				<view class="right">
					<view class="use immediate-use" :round="true">封禁中</view>
				</view>
		
			</view>
		</view>
		<view class="taobao">
			<view class="ticket">
				<view class="left">
					<image class="picture" src="/static/image/service_user.png" mode="widthFix"></image>
					<view class="introduce">
						<view class="top">
							剩余天数84天
						</view>
						<view class="type">1913566XXXXXX</view>
						<view class="date u-line-1"></view>
						<text class="big">拉黑处罚:</text>
					</view>
				</view>
				<view class="right">
					<view class="use immediate-use" :round="true">封禁中</view>
				</view>
		
			</view>
		</view>
	</view>
</template>

<script>
	export default {

	};
</script>

<style lang="scss" scoped>
	page {
		height: 100%;
		background-color: rgb(244, 244, 244);
	}

	.u-wrap {
		padding: 24rpx;
	}
	.taobao {
		margin-top: 10rpx;
		width: 700rpx;
		background-color: white;
		padding: 10rpx 20rpx 20rpx;
		border-radius: 20rpx;

		.title {
			display: flex;
			align-items: center;
			justify-content: space-between;
			margin-bottom: 20rpx;
			font-size: 30rpx;

			.left {
				display: flex;
				align-items: center;
			}

			.store {
				font-weight: 500;
			}

			.buddha {
				width: 70rpx;
				height: 70rpx;
				border-radius: 10rpx;
				margin-right: 10rpx;
			}

			.entrance {
				color: $u-type-info;
				border: solid 2rpx $u-type-info;
				line-height: 48rpx;
				padding: 0 30rpx;
				background: none;
				border-radius: 15px;
			}
		}

		.ticket {
			display: flex;

			.left {
				width: 70%;
				padding: 10rpx 20rpx;
				background-color: rgb(255, 245, 244);
				border-radius: 10rpx;
				border-right: dashed 2rpx rgb(224, 215, 211);
				display: flex;

				.picture {
					width: 172rpx;
					border-radius: 20rpx;
				}

				.introduce {
					margin-left: 10rpx;

					.top {
						color: $u-type-warning;
						font-size: 28rpx;

						.big {
							font-size: 60rpx;
							font-weight: bold;
							margin-right: 10rpx;
							background-color: #DD524D;
						}
					}

					.type {
						font-size: 28rpx;
						color: $u-type-info-dark;
					}

					.date {
						margin-top: 10rpx;
						font-size: 20rpx;
						color: $u-type-info-dark;
					}
				}
			}

			.right {
				width: 30%;
				padding: 40rpx 20rpx;
				background-color: rgb(255, 245, 244);
				border-radius: 5rpx;
				display: flex;
				align-items: center;

				.use {
					height: auto;
					padding: 0 20rpx;
					font-size: 24rpx;
					border-radius: 40rpx;
					color: #ffffff !important;
					background-color: $u-type-warning !important;
					line-height: 40rpx;
					color: rgb(117, 142, 165);
					margin-left: 20rpx;
				}
			}
		}
	}
</style>

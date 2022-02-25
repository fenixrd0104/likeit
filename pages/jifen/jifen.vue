<template>
	
	<view class="wrap">
		<u-navbar :is-back="true" title="邀请好友" :background="{
					backgroundColor: '#563EDC'
				}" :border-bottom="false"
		 :is-fixed="true" title-color="#FFFFFF">
			<template v-slot:right="">
				<view class="mr-3" @click=""><text style="color: #FFFFFF;">兑换记录</text></view>
			</template>
		</u-navbar>
		<view class="header">
			<view class="">
			</view>
		</view>
		<!-- 轮播图 -->
		<view style="padding:15rpx 30rpx 15rpx 30rpx;">
			<u-swiper :list="swiper" :active-color="'#f8c750'" mode="dot" indicator-pos="bottomRight" :border-radius="18" height="280"
			 @click=""></u-swiper>
		</view>
		<!-- 商品列表 -->
		<u-waterfall v-model="flowList" ref="uWaterfall">
			<template v-slot:left="{leftList}">
				<view class="demo-warter" v-for="(item, index) in leftList" :key="index">
					<u-lazy-load threshold="-450" border-radius="10" :image="item.image" :index="index"></u-lazy-load>
					<view class="demo-title">
						{{item.title}}
					</view>
					<view class="demo-price">
						{{item.price}}元
					</view>
					<view class="demo-tag">
						<view class="demo-tag-owner">
							正品
						</view>
						<view class="demo-tag-text">
							放心购
						</view>
					</view>
					<view class="demo-shop">
						{{item.shop}}
					</view>
					<u-icon name="close-circle-fill" color="#fa3534" size="34" class="u-close" @click="remove(item.id)"></u-icon>
				</view>
			</template>
			<template v-slot:right="{rightList}">
				<view class="demo-warter" v-for="(item, index) in rightList" :key="index">
					<u-lazy-load threshold="-450" border-radius="10" :image="item.image" :index="index"></u-lazy-load>
					<view class="demo-title">
						{{item.title}}
					</view>
					<view class="demo-price">
						{{item.price}}元
					</view>
					<view class="demo-tag">
						<view class="demo-tag-owner">
							正品
						</view>
						<view class="demo-tag-text">
							放心购
						</view>
					</view>
					<view class="demo-shop">
						{{item.shop}}
					</view>
					<u-icon name="close-circle-fill" color="#fa3534" size="34" class="u-close" @click="remove(item.id)"></u-icon>
				</view>
			</template>
		</u-waterfall>
		<!-- <u-loadmore bg-color="rgb(240, 240, 240)" :status="loadStatus" @loadmore="addRandomData"></u-loadmore> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				loadStatus: 'loadmore',
				flowList: [],
				list: [{
						price: 7891,
						title: '须晴日，看红装素裹，分外妖娆',
						shop: '',
						image: 'https://g-search1.alicdn.com/img/bao/uploaded/i4/i1/2472401524/O1CN01yZCARJ1N82EsplxLM_!!2472401524.jpg_250x250.jpg_.webp',
					},
					{
						price: 2341,
						shop: '',
						title: '江山如此多娇，引无数英雄竞折腰',
						image: 'https://g-search2.alicdn.com/img/bao/uploaded/i4/i4/1019961538/O1CN01mNYFgT1NERnpac5vK_!!1019961538.jpg_250x250.jpg_.webp',
					},
				],
				swiper: [{
						image: '../../static/integral/4.png',
						url: 'http://baidu.com'
					},
					{
						image: '../../static/image/3df24492d3cfd2a07d5b06523ecc4aed.jpeg',
						url: 'http://baidu.com'
					},
					{
						image: '../../static/image/3df24492d3cfd2a07d5b06523ecc4aed.jpeg',
						url: 'http://baidu.com'
					}
				],
			}
		},
		onLoad() {
			this.addRandomData();
		},
		onReachBottom() {
			this.loadStatus = 'loading';
			// 模拟数据加载
			setTimeout(() => {
				this.addRandomData();
				this.loadStatus = 'loadmore';
			}, 1000)
		},
		methods: {
			addRandomData() {
				for (let i = 0; i < 4; i++) {
					let index = this.$u.random(0, this.list.length - 1);
					// 先转成字符串再转成对象，避免数组对象引用导致数据混乱
					let item = JSON.parse(JSON.stringify(this.list[index]))
					item.id = this.$u.guid();
					this.flowList.push(item);
				}
			},
			remove(id) {
				this.$refs.uWaterfall.remove(id);
			},
			clear() {
				this.$refs.uWaterfall.clear();
			}
		}
	}
</script>

<style>
	/* page不能写带scope的style标签中，否则无效 */
	page {
		background-color: rgb(240, 240, 240);
	}
</style>

<style lang="scss" scoped>
	.demo-warter {
		border-radius: 8px;
		margin: 5px;
		background-color: #ffffff;
		padding: 8px;
		position: relative;
	}

	.u-close {
		position: absolute;
		top: 32rpx;
		right: 32rpx;
	}

	.demo-image {
		width: 100%;
		border-radius: 14px;
	}

	.demo-title {
		font-size: 30rpx;
		margin-top: 5px;
		color: $u-main-color;
	}

	.demo-tag {
		display: flex;
		margin-top: 5px;
	}

	.demo-tag-owner {
		background-color: $u-type-error;
		color: #FFFFFF;
		display: flex;
		align-items: center;
		padding: 4rpx 14rpx;
		border-radius: 50rpx;
		font-size: 20rpx;
		line-height: 1;
	}

	.demo-tag-text {
		border: 1px solid $u-type-primary;
		color: $u-type-primary;
		margin-left: 10px;
		border-radius: 50rpx;
		line-height: 1;
		padding: 4rpx 14rpx;
		display: flex;
		align-items: center;
		border-radius: 50rpx;
		font-size: 20rpx;
	}

	.demo-price {
		font-size: 30rpx;
		color: $u-type-error;
		margin-top: 5px;
	}

	.demo-shop {
		font-size: 22rpx;
		color: $u-tips-color;
		margin-top: 5px;
	}

	.header {
		width: 100%;
		height: 140px;
		position: fixed;
		background-color: #563EDC;
		border-bottom-left-radius: 60% 15%;
		border-bottom-right-radius: 60% 15%;

	}
</style>

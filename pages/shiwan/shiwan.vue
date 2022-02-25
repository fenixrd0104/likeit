<template>
    <view>
        <web-view :webview-styles="webviewStyles" src="https://yuwan.xinliangxiang.com/?platform=1&deviceIdentity=862495042304617&appId=2&mediaUserId=1186&sign=fw9djfdmcj6xsk7r48xymjf0gp1tbeu5&oaid="></web-view>
    </view>
</template>

<script>
	var wv;//计划创建的webview
	var webviewId = "webviewId-index";
    export default {
        data() {
            return {
				isBackFlag : false,
				interval : null,
                webviewStyles: {
                    progress: {
                        color: '#000000'
                    }
                }
            }
        },
		onReady:function() {
			var currentWebview = this.$mp.page.$getAppWebview() //获取当前页面的webview对象
			var interval = setInterval(function() {
				wv = currentWebview.children()[0]
				if(wv){
					wv.id = webviewId;
					wv.setStyle({top:30, bottom:0})
					clearInterval(interval)
				}
			}, 100); //如果是页面初始化调用时，需要延时一下
		},
		onShow: function(){
			this.updateIsBackFlagTask()
		},
		onHide:function(){
			clearInterval(this.interval)
		},
		onBackPress: function(options){
			var _this = this;
			if(!this.isBackFlag){
				return false;
			}
			var isBackFlag = this.$unicorn.h5PageBack(webviewId);
			this.updateIsBackFlag(this);
			return isBackFlag;
		},
		 onLoad: function (options) {
		        setTimeout(function () {
		            console.log('start pulldown');
		        }, 1000);
		        uni.startPullDownRefresh();
		    },
			    onPullDownRefresh() {
			        console.log('refresh');
			        setTimeout(function () {
			            uni.stopPullDownRefresh();
			        }, 1000);
			    },
		methods: {
			updateIsBackFlagTask: function(){
				this.interval = setInterval(function(_this){
					_this.updateIsBackFlag(_this);
				}, 1000, this)
			},
			updateIsBackFlag: function(_this){
				_this.$unicorn.h5PageCanBack(_this.$unicorn.getWebViewById(webviewId))
				.then(res => {
					_this.isBackFlag = res;
				});
			}
		}
    }
</script>

<style>
	
</style>
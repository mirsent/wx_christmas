<template>
	<view>
		<image src="../../static/img/card4.jpg" mode="widthFix"></image>
		<view class="content">
			{{merry}}
		</view>
		<view class="back" @tap="back">
			back
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				merry: '圣诞节快乐~！'
			};
		},
		methods: {
			back() {
				uni.navigateBack({
					delta: 1
				});
			}
		},
		onLoad(e) {
			let info = JSON.parse(e.detailData);
			if (info.merry) {
				this.merry = info.merry;
			}
		},
		onShareAppMessage(res) {
			let title = this.merry;
			let detail = {
				merry: title
			}
			
			return {
				title: title,
				imageUrl: '../../static/img/4.png',
				path: '/pages/card-4/card-4?detailData=' + JSON.stringify(detail),
			}
		}
	}
</script>

<style>
	page{
		height: 100%;
		background: #fcfcfc;
	}
	image{
		width: 100%;
	}
	.back{
		color: #8f8f94;
		opacity: 0.5;
	}
	.content{
		color: #8f8f94;
		position: fixed;
		top: 1080upx;
	}
</style>

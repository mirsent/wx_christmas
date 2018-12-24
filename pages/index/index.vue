<template>
	<view class="wrap">
		<text class="title">{{title}}</text>
		<view class="cards">
			<image :src="card.url" v-for="(card,index) in cards" :key="index" :class="{on: card.page == onIndex}" @tap="choose(card.page)">
			</image>
		</view>
		<view class="btn-group">
			<textarea value="" placeholder="请输入祝福语..." @input="merryChange" />
			<button type="primary" @tap="make">制作贺卡</button>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Merry Christmas',
				onIndex: 1,
				merry: '',
				cards: [{
						page: 1,
						url: '../../static/img/1.png'
					},
					{
						page: 2,
						url: '../../static/img/2.png'
					},
					{
						page: 3,
						url: '../../static/img/3.png'
					},
					{
						page: 4,
						url: '../../static/img/4.png'
					}
				],

			}
		},
		onLoad() {

		},
		methods: {
			choose(e) {
				this.onIndex = e;
			},
			merryChange(e) {
				this.merry = e.detail.value;
			},
			make() {
				let detail = {
					merry: this.merry
				}
				uni.navigateTo({
					url: "../card-"+this.onIndex+"/card-"+this.onIndex+"?detailData=" + JSON.stringify(detail)
				})
			}
		},
		onShareAppMessage() {
			return {
				title: '想对你说声Merry Christmas',
				path: '/pages/index/index'
			}
		}
	}
</script>

<style>
	page {
		height: 100%;
	}

	.wrap {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		height: 100%;
		padding: 80px 20px 20px 20px;
		box-sizing: border-box;
	}

	.title {
		font-size: 42upx;
		font-weight: bold;
		background-image: -webkit-linear-gradient(left, #3498db, #f47920 10%, #d71345 20%, #f7acbc 30%,
			#ffd400 40%, #3498db 50%, #f47920 60%, #d71345 70%, #f7acbc 80%, #ffd400 90%, #3498db);
		color: transparent;
		-webkit-text-fill-color: transparent;
		-webkit-background-clip: text;
		background-size: 200% 100%;
		animation: masked-animation 4s infinite linear;
	}

	@keyframes masked-animation {
		0% {
			background-position: 0 0;
		}

		100% {
			background-position: -100% 0;
		}
	}

	.cards {
		width: 100%;
		display: flex;
		justify-content: space-between;
		align-items: center;
		flex-wrap: wrap;
	}

	.cards image {
		width: 330upx;
		height: 330upx;
		margin-bottom: 10upx;
		box-sizing: border-box;
	}

	.cards image.on {
		border: 2px solid #333;
		box-shadow: 1px 1px 6px #333;
	}

	.btn-group {
		width: 100%;
	}
	textarea{
		width: 100%;
		height: 200upx;
		color: #8f8f94;
	}
</style>

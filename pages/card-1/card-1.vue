<template>
	<view class="">
		<view id="christmas">
			<div class="flake large f-1"></div>
			<div class="flake large f-2"></div>
			<div class="flake large f-3"></div>
			<div class="flake large f-4"></div>
			<div class="flake large f-5"></div>
			<div class="flake large f-6"></div>
			<div class="flake large f-7"></div>
			<div class="flake large f-8"></div>
			<div class="flake large f-9"></div>
			<div class="flake large f-10"></div>
			<div class="flake large f-11"></div>
			<div class="flake large f-12"></div>
			<div class="flake large f-13"></div>
			<div class="flake large f-14"></div>
			<div class="flake large f-15"></div>
			<div class="flake large f-16"></div>
			<div class="flake large f-17"></div>
			<div class="flake f-18"></div>
			<div class="flake f-19"></div>
			<div class="flake f-20"></div>
			<div class="flake f-21"></div>
			<div class="flake f-22"></div>
			<div class="flake f-23"></div>
			<div class="flake f-24"></div>
			<div class="flake f-25"></div>
			<div class="flake f-26"></div>
			<div class="flake f-27"></div>
			<div class="flake f-28"></div>
			<div class="flake f-29"></div>
			<div class="flake f-30"></div>
			<div class="flake f-31"></div>
			<div class="tree left">
				<div class="snow"></div>
			</div>
			<div class="tree right">
				<div class="snow"></div>
			</div>
			<div class="ground"></div>
		</view>
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
				imageUrl: '../../static/img/1.png',
				path: '/pages/card-1/card-1?detailData=' + JSON.stringify(detail),
			}
		}
	}
</script>

<style>
	* {
		-moz-box-sizing: border-box;
		-webkit-box-sizing: border-box;
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}

	body {
		background: #35a66f;
		text-align: center;
	}

	#christmas {
		background: #162a4e;
		-moz-border-radius: 50%;
		-webkit-border-radius: 50%;
		border-radius: 50%;
		background-image: url('data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4gPHN2ZyB2ZXJzaW9uPSIxLjEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGRlZnM+PGxpbmVhckdyYWRpZW50IGlkPSJncmFkIiBncmFkaWVudFVuaXRzPSJvYmplY3RCb3VuZGluZ0JveCIgeDE9IjAuNSIgeTE9IjAuMCIgeDI9IjAuNSIgeTI9IjEuMCI+PHN0b3Agb2Zmc2V0PSIwJSIgc3RvcC1jb2xvcj0iIzBjMWQzOCIvPjxzdG9wIG9mZnNldD0iMTAwJSIgc3RvcC1jb2xvcj0iIzFhMzE1OCIvPjwvbGluZWFyR3JhZGllbnQ+PC9kZWZzPjxyZWN0IHg9IjAiIHk9IjAiIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIGZpbGw9InVybCgjZ3JhZCkiIC8+PC9zdmc+IA==');
		background-size: 100%;
		background-image: -webkit-gradient(linear, 50% 0%, 50% 100%, color-stop(0%, #0c1d38), color-stop(100%, #1a3158));
		background-image: -moz-linear-gradient(#0c1d38, #1a3158);
		background-image: -webkit-linear-gradient(#0c1d38, #1a3158);
		background-image: linear-gradient(#0c1d38, #1a3158);
		position: relative;
		width: 364upx;
		height: 364upx;
		margin: 300upx auto;
		overflow: hidden;
		/* iOS hack for border radius bleed with transforms */
		-webkit-mask-image: -webkit-radial-gradient(circle, white, black);
	}

	#christmas .ground {
		-moz-border-radius-topright: 260upx 80upx;
		-webkit-border-top-right-radius: 260upx 80upx;
		border-top-right-radius: 260upx 80upx;
		position: absolute;
		width: 266upx;
		height: 122upx;
		left: 0;
		bottom: 0;
		background: white;
	}

	#christmas .ground:before {
		-moz-border-radius: 50%;
		-webkit-border-radius: 50%;
		border-radius: 50%;
		content: " ";
		position: absolute;
		width: 260upx;
		height: 200upx;
		top: 20upx;
		right: -120upx;
		background: white;
	}

	#christmas .ground:after {
		-moz-border-radius: 50%;
		-webkit-border-radius: 50%;
		border-radius: 50%;
		content: " ";
		position: absolute;
		width: 140upx;
		height: 140upx;
		top: 10upx;
		right: -150upx;
		background: white;
	}

	#christmas .tree {
		position: absolute;
		width: 0;
		height: 0;
		border-style: solid;
		border-color: transparent transparent #23915b transparent;
	}

	#christmas .tree:before {
		content: " ";
		position: absolute;
		width: 0;
		height: 0;
		border-style: solid;
		border-color: transparent transparent #23915b transparent;
	}

	#christmas .tree:after {
		content: " ";
		position: absolute;
		width: 0;
		height: 0;
		border-style: solid;
		border-color: transparent transparent #23915b transparent;
	}

	#christmas .tree.left {
		left: 56upx;
		bottom: 156upx;
		border-width: 0 36upx 48upx 36upx;
	}

	#christmas .tree.left:before {
		top: 20upx;
		left: -42upx;
		border-width: 0 42upx 56upx 42upx;
	}

	#christmas .tree.left:after {
		top: 44upx;
		left: -48upx;
		border-width: 0 48upx 64upx 48upx;
	}

	#christmas .tree.left .snow {
		-moz-border-radius: 50%;
		-webkit-border-radius: 50%;
		border-radius: 50%;
		box-shadow: -4upx 4upx 0 0 white, 4upx 4upx 0 0 white, -6upx 6upx 0 0 white, 6upx 6upx 0 0 white, -24upx 28upx 0 0 white, -26upx 34upx 0 2upx white, -32upx 38upx 0 0 white, -18upx 32upx 0 0 white, -10upx 30upx 0 4upx white, -18upx 26upx 0 0 white, 12upx 30upx 0 4upx white, 0 26upx 0 2upx white, 22upx 28upx 0 2upx white, 26upx 34upx 0 2upx white, 30upx 38upx 0 0 white;
		position: absolute;
		top: 2upx;
		left: -6upx;
		width: 12upx;
		height: 12upx;
		background: white;
		z-index: 1;
	}

	#christmas .tree.left .snow:after {
		-moz-border-radius: 50%;
		-webkit-border-radius: 50%;
		border-radius: 50%;
		box-shadow: -28upx 28upx 0 0 white, -30upx 34upx 0 2upx white, -36upx 38upx 0 0 white, -18upx 32upx 0 0 white, -10upx 30upx 0 4upx white, -18upx 26upx 0 0 white, 12upx 30upx 0 4upx white, 0 26upx 0 2upx white, 24upx 34upx 0 6upx white, 32upx 34upx 0 2upx white, 36upx 38upx 0 0 white, 22upx 40upx 0 2upx white, 32upx 40upx 0 2upx white, 36upx 44upx 0 2upx white, 42upx 50upx 0 0 white, -4upx 54upx 0 2upx white;
		content: " ";
		position: absolute;
		top: 28upx;
		left: 0upx;
		width: 12upx;
		height: 12upx;
		background: white;
		z-index: 1;
	}

	#christmas .tree.right {
		left: 120upx;
		bottom: 90upx;
		border-width: 0 36upx 48upx 36upx;
	}

	#christmas .tree.right:before,
	#christmas .tree.right:after {
		display: none;
	}

	#christmas .tree.right .snow {
		-moz-border-radius: 50%;
		-webkit-border-radius: 50%;
		border-radius: 50%;
		box-shadow: -2upx 4upx 0 0 white, -4upx 6upx 0 0 white, 4upx 4upx 0 0 white, 6upx 6upx 0 0 white, 8upx 8upx 0 0 white, 12upx 12upx 0 0 white, 12upx 30upx 0 0 white, 16upx 32upx 0 0 white, 20upx 32upx 0 0 white, 22upx 32upx 0 0 white, -10upx 26upx 0 0 white, -14upx 24upx 0 0 white;
		position: absolute;
		top: 0;
		left: -6upx;
		width: 12upx;
		height: 12upx;
		background: white;
	}

	#christmas .flake {
		-webkit-animation: snow infinite linear 30s;
		-moz-animation: snow infinite linear 30s;
		-ms-animation: snow infinite linear 30s;
		-o-animation: snow infinite linear 30s;
		animation: snow infinite linear 30s;
		position: absolute;
		width: 2upx;
		height: 2upx;
		background: white;
	}

	#christmas .flake.large {
		-moz-border-radius: 50%;
		-webkit-border-radius: 50%;
		border-radius: 50%;
		width: 8upx;
		height: 8upx;
	}

	#christmas .flake.f-1 {
		-webkit-animation-duration: 20s;
		-moz-animation-duration: 20s;
		-ms-animation-duration: 20s;
		-o-animation-duration: 20s;
		animation-duration: 20s;
		left: 30upx;
		margin-top: 172upx;
	}

	#christmas .flake.f-2 {
		-webkit-animation-duration: 23s;
		-moz-animation-duration: 23s;
		-ms-animation-duration: 23s;
		-o-animation-duration: 23s;
		animation-duration: 23s;
		left: 64upx;
		margin-top: 104upx;
	}

	#christmas .flake.f-3 {
		-webkit-animation-duration: 32s;
		-moz-animation-duration: 32s;
		-ms-animation-duration: 32s;
		-o-animation-duration: 32s;
		animation-duration: 32s;
		left: 128upx;
		margin-top: 30upx;
	}

	#christmas .flake.f-4 {
		-webkit-animation-duration: 21s;
		-moz-animation-duration: 21s;
		-ms-animation-duration: 21s;
		-o-animation-duration: 21s;
		animation-duration: 21s;
		left: 138upx;
		margin-top: 68upx;
	}

	#christmas .flake.f-5 {
		-webkit-animation-duration: 24s;
		-moz-animation-duration: 24s;
		-ms-animation-duration: 24s;
		-o-animation-duration: 24s;
		animation-duration: 24s;
		left: 140upx;
		margin-top: 144upx;
	}

	#christmas .flake.f-6 {
		-webkit-animation-duration: 16s;
		-moz-animation-duration: 16s;
		-ms-animation-duration: 16s;
		-o-animation-duration: 16s;
		animation-duration: 16s;
		left: 180upx;
		margin-top: 194upx;
	}

	#christmas .flake.f-7 {
		-webkit-animation-duration: 34s;
		-moz-animation-duration: 34s;
		-ms-animation-duration: 34s;
		-o-animation-duration: 34s;
		animation-duration: 34s;
		left: 204upx;
		margin-top: 162upx;
	}

	#christmas .flake.f-8 {
		-webkit-animation-duration: 37s;
		-moz-animation-duration: 37s;
		-ms-animation-duration: 37s;
		-o-animation-duration: 37s;
		animation-duration: 37s;
		left: 204upx;
		margin-top: 80upx;
	}

	#christmas .flake.f-9 {
		-webkit-animation-duration: 35s;
		-moz-animation-duration: 35s;
		-ms-animation-duration: 35s;
		-o-animation-duration: 35s;
		animation-duration: 35s;
		left: 216upx;
		margin-top: 134upx;
	}

	#christmas .flake.f-10 {
		-webkit-animation-duration: 23s;
		-moz-animation-duration: 23s;
		-ms-animation-duration: 23s;
		-o-animation-duration: 23s;
		animation-duration: 23s;
		left: 180upx;
		margin-top: 22upx;
	}

	#christmas .flake.f-11 {
		-webkit-animation-duration: 27s;
		-moz-animation-duration: 27s;
		-ms-animation-duration: 27s;
		-o-animation-duration: 27s;
		animation-duration: 27s;
		left: 252upx;
		margin-top: 110upx;
	}

	#christmas .flake.f-12 {
		-webkit-animation-duration: 29s;
		-moz-animation-duration: 29s;
		-ms-animation-duration: 29s;
		-o-animation-duration: 29s;
		animation-duration: 29s;
		left: 262upx;
		margin-top: 54upx;
	}

	#christmas .flake.f-13 {
		-webkit-animation-duration: 24s;
		-moz-animation-duration: 24s;
		-ms-animation-duration: 24s;
		-o-animation-duration: 24s;
		animation-duration: 24s;
		left: 256upx;
		margin-top: 224upx;
	}

	#christmas .flake.f-14 {
		-webkit-animation-duration: 23s;
		-moz-animation-duration: 23s;
		-ms-animation-duration: 23s;
		-o-animation-duration: 23s;
		animation-duration: 23s;
		left: 292upx;
		margin-top: 144upx;
	}

	#christmas .flake.f-15 {
		-webkit-animation-duration: 19s;
		-moz-animation-duration: 19s;
		-ms-animation-duration: 19s;
		-o-animation-duration: 19s;
		animation-duration: 19s;
		left: 294upx;
		margin-top: 204upx;
	}

	#christmas .flake.f-16 {
		-webkit-animation-duration: 22s;
		-moz-animation-duration: 22s;
		-ms-animation-duration: 22s;
		-o-animation-duration: 22s;
		animation-duration: 22s;
		left: 332upx;
		margin-top: 200upx;
	}

	#christmas .flake.f-17 {
		-webkit-animation-duration: 18s;
		-moz-animation-duration: 18s;
		-ms-animation-duration: 18s;
		-o-animation-duration: 18s;
		animation-duration: 18s;
		left: 354upx;
		margin-top: 146upx;
	}

	#christmas .flake.f-18 {
		-webkit-animation-duration: 26s;
		-moz-animation-duration: 26s;
		-ms-animation-duration: 26s;
		-o-animation-duration: 26s;
		animation-duration: 26s;
		left: 44upx;
		margin-top: 158upx;
	}

	#christmas .flake.f-19 {
		-webkit-animation-duration: 20s;
		-moz-animation-duration: 20s;
		-ms-animation-duration: 20s;
		-o-animation-duration: 20s;
		animation-duration: 20s;
		left: 62upx;
		margin-top: 82upx;
	}

	#christmas .flake.f-20 {
		-webkit-animation-duration: 19s;
		-moz-animation-duration: 19s;
		-ms-animation-duration: 19s;
		-o-animation-duration: 19s;
		animation-duration: 19s;
		left: 76upx;
		margin-top: 112upx;
	}

	#christmas .flake.f-21 {
		-webkit-animation-duration: 31s;
		-moz-animation-duration: 31s;
		-ms-animation-duration: 31s;
		-o-animation-duration: 31s;
		animation-duration: 31s;
		left: 112upx;
		margin-top: 86upx;
	}

	#christmas .flake.f-22 {
		-webkit-animation-duration: 20s;
		-moz-animation-duration: 20s;
		-ms-animation-duration: 20s;
		-o-animation-duration: 20s;
		animation-duration: 20s;
		left: 178upx;
		margin-top: 114upx;
	}

	#christmas .flake.f-23 {
		-webkit-animation-duration: 18s;
		-moz-animation-duration: 18s;
		-ms-animation-duration: 18s;
		-o-animation-duration: 18s;
		animation-duration: 18s;
		left: 180upx;
		margin-top: 60upx;
	}

	#christmas .flake.f-24 {
		-webkit-animation-duration: 28s;
		-moz-animation-duration: 28s;
		-ms-animation-duration: 28s;
		-o-animation-duration: 28s;
		animation-duration: 28s;
		left: 200upx;
		margin-top: 238upx;
	}

	#christmas .flake.f-25 {
		-webkit-animation-duration: 29s;
		-moz-animation-duration: 29s;
		-ms-animation-duration: 29s;
		-o-animation-duration: 29s;
		animation-duration: 29s;
		left: 228upx;
		margin-top: 28upx;
	}

	#christmas .flake.f-26 {
		-webkit-animation-duration: 25s;
		-moz-animation-duration: 25s;
		-ms-animation-duration: 25s;
		-o-animation-duration: 25s;
		animation-duration: 25s;
		left: 254upx;
		margin-top: 168upx;
	}

	#christmas .flake.f-27 {
		-webkit-animation-duration: 26s;
		-moz-animation-duration: 26s;
		-ms-animation-duration: 26s;
		-o-animation-duration: 26s;
		animation-duration: 26s;
		left: 268upx;
		margin-top: 228upx;
	}

	#christmas .flake.f-28 {
		-webkit-animation-duration: 34s;
		-moz-animation-duration: 34s;
		-ms-animation-duration: 34s;
		-o-animation-duration: 34s;
		animation-duration: 34s;
		left: 290upx;
		margin-top: 98upx;
	}

	#christmas .flake.f-29 {
		-webkit-animation-duration: 29s;
		-moz-animation-duration: 29s;
		-ms-animation-duration: 29s;
		-o-animation-duration: 29s;
		animation-duration: 29s;
		left: 296upx;
		margin-top: 84upx;
	}

	#christmas .flake.f-30 {
		-webkit-animation-duration: 23s;
		-moz-animation-duration: 23s;
		-ms-animation-duration: 23s;
		-o-animation-duration: 23s;
		animation-duration: 23s;
		left: 314upx;
		margin-top: 140upx;
	}

	#christmas .flake.f-31 {
		-webkit-animation-duration: 18s;
		-moz-animation-duration: 18s;
		-ms-animation-duration: 18s;
		-o-animation-duration: 18s;
		animation-duration: 18s;
		left: 330upx;
		margin-top: 156upx;
	}

	@-webkit-keyframes snow {
		0% {
			-moz-transform: translateY(-110upx);
			-ms-transform: translateY(-110upx);
			-webkit-transform: translateY(-110upx);
			transform: translateY(-110upx);
		}

		100% {
			-moz-transform: translateY(160upx);
			-ms-transform: translateY(160upx);
			-webkit-transform: translateY(160upx);
			transform: translateY(160upx);
		}
	}

	@-moz-keyframes snow {
		0% {
			-moz-transform: translateY(-110upx);
			-ms-transform: translateY(-110upx);
			-webkit-transform: translateY(-110upx);
			transform: translateY(-110upx);
		}

		100% {
			-moz-transform: translateY(160upx);
			-ms-transform: translateY(160upx);
			-webkit-transform: translateY(160upx);
			transform: translateY(160upx);
		}
	}

	@-ms-keyframes snow {
		0% {
			-moz-transform: translateY(-110upx);
			-ms-transform: translateY(-110upx);
			-webkit-transform: translateY(-110upx);
			transform: translateY(-110upx);
		}

		100% {
			-moz-transform: translateY(160upx);
			-ms-transform: translateY(160upx);
			-webkit-transform: translateY(160upx);
			transform: translateY(160upx);
		}
	}

	@keyframes snow {
		0% {
			-moz-transform: translateY(-110upx);
			-ms-transform: translateY(-110upx);
			-webkit-transform: translateY(-110upx);
			transform: translateY(-110upx);
		}

		100% {
			-moz-transform: translateY(160upx);
			-ms-transform: translateY(160upx);
			-webkit-transform: translateY(160upx);
			transform: translateY(160upx);
		}
	}
</style>

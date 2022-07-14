<template>
	<view class="music-head" :style="{ color : color}">
		<view v-if="icon" class="music-head-icon" :class="{'music-head-iconblack' : iconblack }" >
			<text class="iconfont icon-zuojiantou" @tap="headleToBack"></text> | <text @tap="headleToHome"
				class="iconfont icon-shouye"></text>
		</view>
		{{title}}
	</view>
</template>

<script>
	export default {

		data() {
			return {

			};
		},
		props: ['title','icon','color','iconblack'],
		methods: {
			headleToBack() {
				uni.navigateBack()
			},
			headleToHome() {
				uni.navigateTo({
					url: '/pages/index/index'
				})
			}
		},
	}
</script>

<style lang="scss" scoped>
	.music-head {
		width: 100%;
		height: 75px;
		font-size: 16px;
		line-height: 80px;
		text-align: center;
		color: black;
		position: relative;
	
	.music-head-icon {
			position: absolute;
			left: 8px;
			top: 26px;
			width: 90px;
			height: 30px;
			background: rgba(0, 0, 0, 0.4);
			color: white;
			line-height: 31px;
			border-radius: 15px;
			display: flex;
			justify-content: space-evenly;
		}
		
		.music-head-iconblack {
			color: black;
			background-color: white;
			border: 1px solid #eaeaea;
		}
	}
</style>

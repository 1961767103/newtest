<template>
	<view class="app">
		<view class="info">
			非法访问，该链接无效
		</view>
	</view>
	
</template>

<script setup>
</script>

<style lang="scss">
	.app{
		position: absolute;
		height: 100vh;
		width: 100vw;
		background:
		linear-gradient(to bottom,rgba(0,0,0,0),#fff ),
		linear-gradient(to right,#beecd8 20%,#f4e2d8);
		.info{
			font-size: 50rpx;
			display: flex;
			justify-content: center;
			align-items: center;
			line-height: 100vh;
		}
	}
</style>

<template>
	<view class="classlist">
		<view class="content">
			<navigator url="" class="item" v-for="(index,item) in 7" :key="index">
				<image :src="'https://dg-self-bucket.oss-cn-shenzhen.aliyuncs.com/review/tt'+index+'.jpg'" mode="aspectFill"></image>
			</navigator>
		</view>
	</view>
</template>

<script setup>
	
</script>

<style lang="scss" scoped>
	.classlist{
		.content{
			display: grid;
			grid-template-columns: repeat(3,1fr);
			gap: 5rpx;
			padding: 5rpx;
			.item{
				height: 440rpx;
				image{
					width: 100%;
					height: 100%;
					display: block;
				}
			}
		}
	}
</style>
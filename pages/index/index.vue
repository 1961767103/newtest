<template>
	<view class="app">
		<uni-section class="select" title="本地数据" type="line">
		    <uni-data-select class="option"
				v-model="value"
		        :localdata="range"
				:clear="false"
		    ></uni-data-select>
		</uni-section>
	</view>
</template>

<script setup>
	import { ref } from 'vue';
	let value = ref();
	let range = ref([
          { value: 0, text: "篮球" },
          { value: 1, text: "足球" },
          { value: 2, text: "游泳" },
    ]);
</script>

<style lang="scss">
	.app{
		height: 100vh;
		background-color: pink;
		.select{
			.option{
				background: rgba(255, 255, 255, 0.5);
			}
		}
	}
</style>

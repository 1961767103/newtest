<template>
	<view class="app">
		<view class="title"><!-- 征婚公告 --></view>
		<view class="selecttitle">请选择您的姓名：</view>
		<uni-section class="select" type="line">
		    <uni-data-select class="option"
				v-model="namevalue"
		        :localdata="name"
				:clear="false"
		    ></uni-data-select>
		</uni-section>
		<hr/>
		<view class="selecttitle">请选择您的类型：</view>
		<uni-section class="select" type="line">
		    <uni-data-select class="option"
				v-model="value"
		        :localdata="range"
				:clear="false"
		    ></uni-data-select>
		</uni-section>
		<hr/>
		<view class="selecttitle">请输入您的资产：</view>
		<view class="select2">
			&InvisibleComma;
			&InvisibleComma;
			&InvisibleComma;
			<input class="rich" v-model="rich" type="number"/>
			<view class="wanyuan">
				万元
			</view>
		</view>
		<button @click="handleClick" style="background-color: rgba(255, 255, 255, 0.3);">开始匹配</button>
	</view>
</template>

<script setup>
	import { ref } from 'vue';
	let namevalue = ref();
	let value = ref();
	let showStatue = ref();
	let rich = ref(0);
	let name = ref([
	      { value: "陈紫啧", text: "陈紫啧" },
	      { value: "坐下姐", text: "坐下姐" }
	]);
	let range = ref([
	      { value: 0, text: "答辩型" },
	      { value: 1, text: "网瘾型" },
	      { value: 2, text: "暴躁型" },
	]);
	function handleClick(){
		console.log(rich.value)
		if(namevalue.value==null){
			alert("请先选择姓名！");
			return;
		}
		if(value.value==null){
			alert("请先选择类型！");
			return;
		}
		if(rich.value<50){
			alert("谈什么谈，赚钱去");
			return;
		}
		if(rich.value>=500){
			alert("我就说"+namevalue.value+"是富婆吧")
			return;
		}
		if(rich.value>=50){
			alert("我不信，除非你v我500");
			return;
		}
	}
</script>

<style lang="scss">
	.app{
		position: absolute;
		height: 100vh;
		background-color: pink;
		.title{
			font-size: 50rpx;
			display: flex;
			justify-content: center;
			align-items: center;
		}
		.selecttitle{
			display: inline-block;
			width: 40vw;
		}
		.select2{
			display: inline-block;
			width: 60vw;
			background-color: rgba(255, 255, 255, 0.5);
		}
		.rich{
			display: inline-block;
		}
		.wanyuan{
			display: inline-block;
			
		}
		.select{
			display: inline-block;
			width: 60vw;
			.option{
				background: rgba(255, 255, 255, 0.5);
			}
		}
	}
</style>

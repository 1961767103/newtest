<template>
	<view class="app">
		<view class="title">征婚匹配</view>
		<view class="selecttitle">请选择您的姓名：</view>
		<uni-section class="select" type="line" >
		    <uni-data-select class="option"
				v-model="namevalue"
		        :localdata="name"
				:clear="false"
				@change="nameChange"
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
			<view class="konge"></view>
			<input class="rich" v-model="rich" type="number"/>
			<view class="wanyuan">
				万元
			</view>
		</view>
		<button @click="handleClick" style="background-color: rgba(255, 255, 255, 0.3);">开始匹配</button>
		
		<view class="box" >
			<image v-if="namevalue=='彤彤咪'" class="pic" src="../../static/tt.jpg" mode="aspectFill"></image>
			<image v-if="namevalue=='静静咪'" class="pic" src="../../static/yj.jpg" mode="aspectFill"></image>
			<image v-if="namevalue=='宁宁咪'" class="pic" src="../../static/zn.jpg" mode="aspectFill"></image>
			<image v-if="namevalue=='轩轩咪'" class="pic" src="../../static/zx.jpg" mode="aspectFill"></image>
			<image v-if="showStatue==1" class="pic" src="../../static/ym.jpg" mode="aspectFill"></image>
		</view>
	</view>
	
</template>

<script setup>
	import { ref } from 'vue';
	let namevalue = ref();
	let value = ref();
	let showStatue = ref(0);
	let rich = ref(0);
	let name = ref([
	      { value: "彤彤咪", text: "彤彤咪" },
	      { value: "静静咪", text: "静静咪" },
	      { value: "宁宁咪", text: "宁宁咪" },
	      { value: "轩轩咪", text: "轩轩咪" }
	]);
	let range = ref([
	      { value: 0, text: "答辩型" },
	      { value: 1, text: "网瘾型" },
	      { value: 2, text: "暴躁型" },
	]);
	function handleClick(){
		showStatue.value=false;
		if(namevalue.value==null){
			alert("请先选择姓名！");
			return;
		}
		if(value.value==null){
			alert("请先选择类型！");
			return;
		}
		if(rich.value<10){
			alert("谈什么谈，赚钱去");
			return;
		}
		if(rich.value>=500){
			alert("我就说"+namevalue.value+"是富婆吧")
			return;
		}
		if(rich.value>=100){
			alert("我不信，除非你v我500");
			return;
		}
		else{
			showStatue.value=1;
			alert("匹配成功");
			return;
		}
	}
</script>

<style lang="scss">
	.app{
		position: absolute;
		height: 100vh;
		background:
		linear-gradient(to bottom,rgba(0,0,0,0),#fff ),
		linear-gradient(to right,#beecd8 20%,#f4e2d8);
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
			background: rgba(255, 255, 255, 0.8);
		}
		.konge{
			display: inline-block;
			width: 5vw;
		}
		.rich{
			display: inline-block;
			width: 45vw;
		}
		.wanyuan{
			display: inline-block;
			width: 10vw;
			
		}
		.select{
			display: inline-block;
			width: 60vw;
			.option{
				background: rgba(255, 255, 255, 0.8);
			}
		}
		.box{
			width: 300rpx;
			height: 330rpx;
			margin-right: 15rpx;
			position: absolute;
			top: 425rpx;
			left: 30%;
			.pic{
				height: 100%;
				width: 100%;
				border-radius: 10rpx;
			}
		}
	}
</style>

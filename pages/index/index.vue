<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="list" v-for="(item, index) in list" :key="index" @tap="clickItem(item)">
			<text>{{ item.title }}</text>
		</view>
	</view>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

type ItemType = {
	title: string;
	url: string;
};

const list = ref<ItemType[]>([
	{
		title: '按钮',
		url: '/pages/seeButton/index'
	}
]);

const clickItem = (item: ItemType) =>
	uni.navigateTo({
		url: item.url
	});
</script>

<style>
.content {
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
}

.logo {
	height: 200rpx;
	width: 200rpx;
	margin-top: 50rpx;
	margin-left: auto;
	margin-right: auto;
	margin-bottom: 50rpx;
}

.list {
	width: 100%;
	padding: 24rpx 48rpx;
	box-sizing: border-box;
	border: 1px #f1f1f1 solid;
}
</style>

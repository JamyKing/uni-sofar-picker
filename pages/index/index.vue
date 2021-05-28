<template>
	<view class="content">
		<view class="header">
			<view class="date-item">日期范围：{{dateValue[0]}} - {{dateValue[1]}}</view>
			<view class="date-item">参数值(Array)：{{dateValue}}</view>
		</view>
		<button class="date-btn" type="default" @click="openPicker">打开</button>
		<sofar-picker :visable.sync="pickerVisable" :defaultDate="defaultDate" @confirm="confirm"></sofar-picker>
	</view>
</template>

<script>
	import sofarPicker from '@/components/sofar-picker/sofar-picker.vue'
	export default {
		components: {
			sofarPicker
		},
		data() {
			return {
				pickerVisable: false,
				defaultDate: ['2020.1', '至今'],
				dateValue: []
			}
		},
		methods: {
			openPicker() {
				this.pickerVisable = true
			},
			confirm(date) {
				this.dateValue = date
			}
		}
	}
</script>

<style>
	.header {
		width: 100%;
		padding: 60rpx 30rpx;
		display: flex;
		flex-direction: column;
	}
	.date-item {
		margin-bottom: 30rpx;
	}
	.date-btn {
		width: 500rpx;
		height: 80rpx;
		line-height: 80rpx;
	}
</style>

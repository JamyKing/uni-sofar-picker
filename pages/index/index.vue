<template>
	<view class="content">
		<button type="default" @click="open">open</button>
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
		onLoad() {

		},
		methods: {
			open() {
				this.pickerVisable = true
			},
			confirm(date) {
				this.dateValue = date
			}
		}
	}
</script>

<style>
	
</style>

<template>
	<view>
		<picker mode="multiSelector" :value="index" :range="array" @columnchange='columnchange'>
			<view>
				{{array[0][index[0]]}}
				——————
				{{array[1][index[1]]}}
				——————
				{{array[2][index[2]]}}
			</view>
		</picker>
	</view>
</template>

<script>
	import {
		data
	} from './data.js'
	export default {
		computed: {
			// 过滤省
			shen() {
				return this.dataList.map(item => {
					return item.name
				})
			},
			// 过滤市
			shi() {
				return this.dataList[this.index[0]].city.map(item => {
					return item.name
				})
			},
			// 区
			qu() {
				return this.dataList[this.index[0]].city[this.index[1]].area.map(item => {
					return item
				})
			}
		},
		methods: {
			columnchange(e) {
				// column :滑动的是那一列
				// value :滑动的列的第几项
				const {
					column,
					value
				} = e.detail
				this.index[column] = value
				// 滑动的是第一项
				if (column === 0) {
					let a = []
					// 动态修改市
					a = this.dataList[this.index[0]].city.map(item => {
						return item.name
					})
					// 动态修改区
					let b = []
					b = this.dataList[this.index[0]].city[this.index[1]]?.area.map(item => {
						return item
					})
					this.array[1] = a
					this.array[2] = b
					// 通知Vue修改 index数组索引为1的值为0
					this.$set(this.index, 1, 0)
					// 通知Vue修改 index数组索引为2的值为0
					this.$set(this.index, 2, 0)
				} else
					// 滑动的是第二项
					if (column == 1) {
						// 通知Vue修改 index数组索引为2的值为0
						this.$set(this.index, 2, 0)
					}
			}
		},
		onLoad() {
			// 初始化
			this.array[0] = this.shen;
			this.array[1] = this.shi
			this.array[2] = this.qu
		},
		data() {
			return {
				index: [0, 0, 0],
				dataList: data,
				array: [
					[],
					[],
					[]
				]
			}
		}
	}
</script>

<style>
</style>

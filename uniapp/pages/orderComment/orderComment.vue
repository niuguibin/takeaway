<template>
	<view style="padding: 20rpx;">
		<view class="box">
			<uni-forms :modelValue="form" :rules="rules" ref="formRef" label-width="140rpx" label-align="right">
			  <uni-forms-item label="备注" name="comment">
			    <uni-easyinput type="textarea" v-model="comment" placeholder="请输入" />
			  </uni-forms-item>
			
			  <uni-forms-item>
			    <button type="primary" size="mini" @click="save">确 定</button>
			  </uni-forms-item>
			</uni-forms>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				comment: ''
			}
		},
		methods: {
			save() {
				let xmOrders = uni.getStorageSync('xm-orders') || {}//取出来
				xmOrders.comment = this.comment//写进去
				uni.setStorageSync('xm-orders', xmOrders)//再放进去
				uni.navigateBack()
			}
		}
	}
</script>

<style>

</style>

<template>
	<div v-if="visible">
		加载中。。。
	</div>
</template>

<script>
export default {
	name: 'Loading',
	data() {
		return { 
			visible: false 
		}
	},
	methods: {
		start() {
			this.visible = true
		},
		finish() {
			this.visible = false
			console.log("test")
		}
	}
}
</script>

<style scoped>

</style>
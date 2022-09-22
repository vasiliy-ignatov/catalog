<template>
	<button class="btn" @click="btnClick">{{ name }}</button>
</template>

<script>
export default {
	props: {
		name: {
			type: String,
			default: ''
		}
	},
	methods: {
		btnClick() {
			this.$emit('btnClick')
		}
	}
}
</script>

<style lang="scss">
	.btn {
		width: 100%;
		padding: 14px;
		padding-bottom: 15px;
		font-size: 16px;
		line-height: 21px;
		text-align: center;
		color: $white;
		outline: none;
		border: none;
		background: $black;
		border-radius: 8px;
		cursor: pointer;
	}
</style>
<template>
	<div class="rating">
		<div class="rating__icon">
			<div class="rating__icon-image"></div>
			<div
				class="rating__icon-fill"
				:style="{top: valOnPercent}"
			></div>
		</div>
		<div class="rating__counter">{{ value }}</div>
	</div>
</template>

<script>
export default {
	props: {
		value: {
			type: Number,
			default: 0
		}
	},
	computed: {
		valOnPercent() {
			const MAX_VAL = 100
			return MAX_VAL - (this.value * 20) + '%'
		}
	}
}
</script>

<style lang="scss">
	.rating {
		display: flex;
		align-items: center;

		&__icon {
			position: relative;
			width: 14px;
			height: 14px;
			margin-right: 4px;
		}
		&__icon-image {
			position: absolute;
			top: 0;
			left: 0;
			right: 0;
			bottom: 0;
			background-position: center;
			background-repeat: no-repeat;
			background-size: cover;
			background-image: url('~@/assets/img/icons/i-star.png');
			z-index: 2;
		}
		&__icon-fill {
			position: absolute;
			top: 5px;
			left: 0;
			right: 0;
			bottom: 0;
			background-color: $yellow;
			z-index: 1;
		}
		&__counter {
			font-size: 10px;
			line-height: 13px;
			color: $yellow;
		}
	}
</style>
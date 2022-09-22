<template>
	<div class="ui-input">
		<div class="ui-input__placeholder">Ваше имя</div>
		<input class="ui-input__input" type="text"/>
		<div class="ui-input__error">Поле обязательно для заполнения</div>
	</div>
</template>

<script>
export default {
	name: 'ui-input',
}
</script>

<style lang="scss">
	.ui-input {
		position: relative;
		width: 100%;
		font-size: 16px;
		line-height: 1;
		margin-bottom: 16px;
		background: $gray3;
		border-radius: 8px;

		&__input {
			width: 100%;
			border: none;
			position: relative;
			padding: 14px;
			background: transparent;
			color: $black;
			z-index: 2;
		}
		&__placeholder {
			position: absolute;
			padding: 14px;
			color: $gray2;
			z-index: 3;
			pointer-events: none;
		}
		&__error {
			position: absolute;
			top: calc(100% + 5px);
			left: 0;
			color: #f00;
			text-align: left;
			font-size: 11px;
			line-height: 11px;
		}
	}
</style>

<template>
	<div class="cart-form">
		<div class="cart-form__title">Оформить заказ</div>
		<ui-input v-bind="form.name"></ui-input>
	</div>
</template>

<script>
import UiInput from '@/components/ui/UiInput';
export default {
	name: 'CartForm',
	components: {
		UiInput
	},
	data() {
		return {
			
		}
	}
}
</script>

<style lang="scss">
	.cart-form {
		&__title {
			margin-bottom: 16px;
			font-size: 18px;
			line-height: 23px;
		}
	}
</style>
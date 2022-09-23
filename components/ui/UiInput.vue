<template>
	<div class="ui-input">
		<div class="ui-input__placeholder">{{ placeholder }}</div>
		<input class="ui-input__input" type="text" v-model="dataValue"/>
		<div class="ui-input__error" v-if="errorText && !$v.dataValue.required && this.$v.dataValue.$error">{{errorText}}</div>
	</div>
</template>

<script>
import { validationMixin } from 'vuelidate'
import { required } from 'vuelidate/lib/validators'

export default {
	name: 'ui-input',
	mixins: [validationMixin],
	props: {
		value: {
			type: String,
			default: ''
		},
		placeholder: {
			type: String,
			default: ''
		},
		errorText: {
			type: String,
			default: ''
		}
	},
	data() {
		return {
			dataValue: ''
		}
	},
	mounted() {
		this.dataValue = this.value
	},
	validations: {
		dataValue: {
			required
		}
	},
	methods: {
		showError() {
			console.log('blur');
			console.log(this.$v.dataValue.required, this.$v.dataValue.$error);
			if (this.$v.$invalid) {
				this.$v.$touch()
				return
			}
		}
	}
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

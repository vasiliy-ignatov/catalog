<template>
	<div class="select">
		<div 
			class="select__header"
			@click.stop="toggleSelect">Сортировать по: <span>{{selected}}</span></div>
		<div :class="['select__menu  menu-select', {'is-active': isOpen}]">
			<div class="menu-select__inner">
				<div class="menu-select__item" 
					v-for="selectVal, index in selectOptions"
					:key="index"
					@click.stop="chooseSelect(selectVal)">{{selectVal.name}}</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'UiSelect',
	props: {
		selectOptions: {
			type: Array,
			default() {
				return []
			}
		},
		selected: {
			type: String,
			default: ''
		}
	},
	data() {
		return {
			isOpen: false
		}
	},
	methods: {
		toggleSelect() {
			this.isOpen = !this.isOpen
		},
		chooseSelect(options) {
			this.isOpen = !this.isOpen
			this.$emit('select', options)
		},
		hideSelect() {
			this.isOpen = false
		}
	},
	mounted() {
		document.addEventListener('click', this.hideSelect)
	},
	beforeDestroy() {
		document.removeEventListener('click', this.hideSelect)
	}
}
</script>

<style lang="scss">
	.select {
		cursor: pointer;
		position: relative;
		user-select: none;
		z-index: 3;

		&__header {
			position: relative;
			padding-right: 9px;
			color: $black;

			&::after {
				content: '';
				position: absolute;
				width: 5px;
				height: 3px;
				background-size: cover;
				background-position: top center;
				background-repeat: no-repeat;
				background-image: url('~@/assets/img/icons/i-arrow.svg');
				right: 0;
				top: 50%;
				transform: translate(-50%);
			}
			span {
				margin-left: 6px;
				color: $gray;
			}
		}
	}
	.menu-select {
		position: absolute;
		// display: none;
		max-height: 0;
		width: 160px;
		top: calc(100% + 6px);
		right: 0;
		background: #FFFFFF;
		box-shadow: 0px 4px 16px rgba(0, 0, 0, 0.05);
		border-radius: 8px;
		overflow: hidden;

		&.is-active {
			max-height: 100px;
			transition: max-height .25s ease-in;
			// display: block;
		}
		&__inner {
			padding: 8px 0 12px;
		}
		&__item {
			padding: 4px 12px;
			font-size: 14px;
			line-height: 18px;
			color: $gray2;
			transition: all .25s ease-in;

			&:hover {
				color: $black;
				background-color: $gray3;
			}
		}
	}
</style>
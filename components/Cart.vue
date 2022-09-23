<template>
	<div class="cart-menu" v-if="isActive">
		<div class="cart-menu__overlay"></div>
		<div :class="['cart', {'is-active': isActive}]">
			<div class="cart__close"></div>
			<div class="cart__title">Корзина</div>

			<!-- <div class="cart__subtitle">Пока что вы ничего не добавили в корзину.</div>
			<ui-btn :name="'Перейти к выбору'" @btnClick="btnClick"></ui-btn> -->

			<div class="cart-list">
				<div class="cart-list__title">Товары в корзине</div>
				<div class="cart-list__item" v-for="item, i in 3">
					<div class="cart-product">
						<div class="cart-product__img">
							<div class="cart-product__picture"></div>
						</div>
						<div class="cart-product__info">
							<div class="cart-product__title">Рюкзак Louis Vuitton Discovery</div>
							<div class="cart-product__price">150 000 ₽</div>
							<div class="cart-product__rating">
								<ui-rating :value="3"></ui-rating>
							</div>
						</div>
						<div class="cart-product__btn">
							<svg><use xlink:href="#cart"></use></svg>
						</div>
					</div>
				</div>
			</div>
			
			<div class="cart-form">
				<div class="cart-form__title">Оформить заказ</div>
				<ui-input v-bind="form.name"></ui-input>
			</div>
		</div>
	</div>
</template>

<script>
import UiBtn from '@/components/ui/UiBtn'
import UiRating from '@/components/ui/UiRating'
import UiInput from '@/components/ui/UiInput'

export default {
	components: {
		UiBtn,
		UiRating,
		UiInput
	},
	props: {
		isActive: false
	},
	data() {
		return {
			form: {
				name: {
					value: '',
					placeholder: 'Ваше имя',
					errorText: 'Поле обязательно для заполнения'
				}
			}
		}
	},
	methods: {
		btnClick() {
		}
	}
}
</script>

<style lang="scss">
	.cart-menu {
		position: fixed;
		top: 0;
		right: 0;
		left: 0;
		bottom: 0;
		z-index: 11;

		&__overlay {
			position: absolute;
			top: 0;
			right: 0;
			left: 0;
			bottom: 0;
			background-color: $white;
			opacity: .8;
		}
	}
	.cart {
		position: absolute;
		width: 460px;
		right: 0;
		top: 0;
		bottom: 0;
		padding: 52px 48px;
		transform: translateX(100%);
		transition: transform .25s ease-in;
		background-color: $white;
		box-shadow: -4px 0px 16px rgba(0, 0, 0, 0.05);
		border-radius: 8px 0px 0px 8px;
		overflow-y: scroll;

		&.is-active {
			transform: translateX(0);
		}

		&__close {
			position: absolute;
			width: 24px;
			height: 24px;
			top: 60px;
			right: 48px;
			background-repeat: no-repeat;
			background-position: center;
			background-size: 14px 14px;
			background-image: url('~/assets/img/icons/i-close.svg');
			cursor: pointer;
		}
		&__title {
			margin-bottom: 24px;
			font-size: 32px;
			line-height: 41px;
			font-weight: 700;
		}
		&__subtitle {
			margin-bottom: 24px;
			font-size: 22px;
			line-height: 28px;
		}
	}
	.cart-list {
		margin-bottom: 20px;
		&__title {
			margin-bottom: 16px;
			font-size: 18px;
			line-height: 23px;
		}
		&__item {
			margin-bottom: 12px;
		}
	}
	.cart-product {
		display: flex;
		align-items: center;
		padding: 12px 16px 12px 25px;
		box-shadow: 0px 4px 16px rgba(0, 0, 0, 0.05);
		border-radius: 8px;
		background: $white;

		&__img {
			width: 70px;
			margin-right: 34px;
		}
		&__picture {
			padding-bottom: 128.57142%;
			background-repeat: no-repeat;
			background-position: center;
			background-size: cover;
			background-image: url('/img/pic-01.jpg');
		}
		&__info {
			max-width: 170px;
			padding-right: 20px;
		}
		&__title {
			margin-bottom: 6px;
			color: $gray;
		}
		&__price {
			font-weight: 700;
			margin-bottom: 16px;
		}
		&__btn {
			fill: $gray2;
			cursor: pointer;

			svg {
				width: 20px;
				height: 22px;
			}
		}
		&__btn:hover{
			fill: $black;
		}
	}
</style>
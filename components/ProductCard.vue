<template>
	<div class="product-card">
		
		<div class="product-card__rating">
			<ui-rating :value="4.3"></ui-rating>
		</div>
		<div class="product-card__basket">
			<svg><use xlink:href="#basket"></use></svg>
		</div>
		<div class="product-card__image">
			<div class="product-card__picture" :style="`background-image: url('img/pic-01.jpg')`"></div>
		</div>
		<div class="product-card__title">Рюкзак Louis Vuitton Discovery</div>
		<div class="product-card__price">150 000 ₽</div>
	</div>
</template>

<script>
import UiRating from '@/components/ui/UiRating'
export default {
	components: {
		UiRating
	}
}
</script>

<style lang="scss">
	.product-card {
		position: relative;
		min-height: 100%;
		padding: 18px 16px 16px;
		background: $white;
		box-shadow: 0px 4px 16px rgba(0, 0, 0, 0.05);
		border-radius: 8px;

		&__rating {
			position: absolute;
			left: 19px;
			top: 20px;
		}
		&__image {
			width: 61.20689%;
			margin: 0 auto;
			margin-bottom: 16px;
		}
		&__picture {
			padding-bottom: 126.76056%;
			background-repeat: no-repeat;
			background-size: cover;
			background-position: center;
			// background-color: red;
		}
		&__title {
			font-size: 14px;
			line-height: 18px;
			margin-bottom: 6px;
		}
		&__price {
			font-weight: 700;
			font-size: 14px;
			line-height: 18px;
		}
		&__basket {
			position: absolute;
			top: 18px;
			right: 18px;
			cursor: pointer;

			svg {
				width: 12px;
				height: 13px;
				fill: $gray2;
			}
			&:hover svg {
				fill: $black;
			}
		}
	}
</style>
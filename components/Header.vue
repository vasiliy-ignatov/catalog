<template>
	<header class="header">
		<div class="container">
			<div class="header__inner">
				<div class="header__logo">TestList</div>
				<div class="header__basket">
					<div class="basket">
						<svg><use xlink:href="#basket-lg"></use></svg>
						<div class="basket__counter">3</div>
					</div>
				</div>
			</div>
		</div>
	</header>
</template>

<script>
export default {

}
</script>

<style lang="scss">
	.header {
		position: fixed;
		height: 66px;
		top: 0;
		left: 0px;
		right: 0px;
		background: #FFFFFF;
		box-shadow: 0px 4px 16px rgba(0, 0, 0, 0.05);
		border-radius: 0px 0px 8px 8px;
		z-index: 10;

		&__inner {
			display: flex;
			justify-content: space-between;
			padding: 18px 0 20px;
		}
		&__logo {
			font-size: 22px;
			line-height: 28px;
			color: $gray;
			user-select: none;
			cursor: pointer;
			text-decoration: none;
			font-weight: 700;
		}
		&__basket {
			margin-right: 20px;
		}
	}
	.basket {
		position: relative;
		cursor: pointer;
		
		svg {
			width: 24px;
			height: 26px;
		}
		&__counter {
			position: absolute;
			width: 12px;
			height: 12px;
			top: -3px;
			right: -5px;
			font-size: 8px;
			line-height: 12px;
			border-radius: 50%;
			background-color: $gray2;
			color: $white;
			font-weight: 700;
			text-align: center;
		}
	}
</style>
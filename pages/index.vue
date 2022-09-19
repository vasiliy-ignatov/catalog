<template>
	<div>
		<div class="page-header">
			<div class="page-header__item">
				<h1 class="page-title">Каталог</h1>
			</div>
			<div class="page-header__item">
				<Select/>
			</div>
		</div>
		<div class="page-wrapper">
			<div class="page-wrapper__col page-wrapper__col--left">
				<Sidebar/>
			</div>
			<div class="page-wrapper__col page-wrapper__col--right">
				<div class="catalog">
					<div class="catalog__item" v-for="item in 12" :key="item">
						<ProductCard/>
					</div>
				</div>

				<div class="wrapper">
					<div class="block block-1">One</div>
					<div class="block block-2">Two</div>
					<div class="block block-3">Three</div>
					<div class="block block-4">Four</div>
					<div class="block block-5">Five</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>

export default {
	name: 'IndexPage',
}
</script>

<style lang="scss">
	.page-wrapper {
		display: flex;

		&__col--left {
			width: 160px;
		}
		&__col--right {
			width: calc(100% - 160px);
		}
	}
	p {
		margin: 0;
		padding: 0;
	}
	.page-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 24px;
	}

	.block {
		border: 2px solid #ffa94d;
		border-radius: 5px;
		background-color: #ffd8a8;
		padding: 1em;
		color: #d9480f;
	}
	.wrapper {
		display: grid;
		border: 2px solid #f76707;
		border-radius: 5px;
		background-color: #fff4e6;
		grid-template-columns: repeat(3, 1fr);
		grid-auto-rows: 140px;
		grid-gap: 16px;
	}
	.block-1 {
		grid-row: 1 / 3;
	}
	.block-2 {
		grid-column: 2 / 4;
	}
	.block-5 {
		grid-column: 1 / 4;
	}
	.catalog {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		grid-gap: 16px;
		// grid-auto-rows: 272px;
	}
</style>

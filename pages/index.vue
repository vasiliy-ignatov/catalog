<template>
	<div>
		<div class="page-header">
			<div class="page-header__item">
				<h1 class="page-title">Каталог</h1>
			</div>
			<div class="page-header__item">
				<ui-select
					v-bind="selectData"
					@select="chooseSelect"
				></ui-select>
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
			</div>
		</div>
	</div>
</template>

<script>
import UiSelect from '@/components/ui/UiSelect';

export default {
	name: 'IndexPage',
	components: {
		UiSelect
	},
	data() {
		return {
			selectData: {
				selectOptions: [
					{name: 'По цене', value: 1},
					{name: 'По популярности', value: 2},
				],
				selected: 'цене'
			}
		}
	},
	methods: {
		chooseSelect(options) {
			this.selectData.selected = options.name.split(' ')[1]
		}
	}
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
	.catalog {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		grid-gap: 16px;
	}
</style>

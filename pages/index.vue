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
				<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. In atque iste laboriosam magni officiis dolorem quos accusantium, expedita rem fugiat, eveniet iusto id aliquam dolore maiores non molestias cumque enim?</p>
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
			width: 161px;
		}
		&__col--right {
			width: calc(100% - 161px);
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
</style>

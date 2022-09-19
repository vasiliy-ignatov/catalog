<template>
	<div class="select">
		<div class="select__header">Сортировать по: <span>цене</span></div>
		<div class="select__menu  menu-select">
			<div class="menu-select__item">По цене</div>
			<div class="menu-select__item">По популярности</div>
		</div>
	</div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
	.select {
		cursor: pointer;
	}
	.menu-select {
		display: none;
	}
</style>
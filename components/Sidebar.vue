<template>
	<ul class="sidebar">
		<li 
			class="sidebar__item"
			v-for="item, index in catalogList"
			:key="index">
				{{item}}
		</li>
	</ul>
</template>

<script>
export default {
	data() {
		return {
			catalogList: ['Рюкзаки', 'Футболки', 'Рубашки']
		}
	}
}
</script>

<style lang="scss">
	.sidebar {
		padding: 0;
		margin: 0;
		list-style: none;

		&__item {
			margin-bottom: 16px;
			font-size: 16px;
			line-height: 21px;
			text-decoration: none;
			cursor: pointer;
		}
	}
</style>
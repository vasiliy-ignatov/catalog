<template>
	<ul class="sidebar">
		<li
			v-for="item, index in catalogList"
			:class="[
				'sidebar__item',
				{'is-active': index === 0}
			]"
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
			color: $gray2;
			cursor: pointer;
			transition: all .25s ease-in;

			&:hover {
				color: $gray;
				text-decoration: none;
			}
		}
		&__item.is-active {
			color: $black;
			cursor: default;
			text-decoration: underline;
		}
	}
</style>
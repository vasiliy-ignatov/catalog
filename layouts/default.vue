<template>
	<div>
		<ui-icons></ui-icons>
		<div class="container">
			<Header/>
			<main class="main">
				<Nuxt />
			</main>
		</div>
	</div>
</template>

<script>
import UiIcons from '@/components/ui/UiIcons';

export default {
	name: "default",
	components: {
		UiIcons
	}
}
</script>

<style>

</style>

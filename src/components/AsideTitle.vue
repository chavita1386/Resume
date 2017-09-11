<template>
	<div class="padding">
		<h2 class="info__title">{{title}}</h2>
	</div>
</template>

<script>
export default {
	props: ['title'],
	data() {
		return {

		}
	},
	computed: {
		css() {
			return "icon-" + this.icon;
		}
	}

}
</script>

<style lang="scss">

</style>


<template>
	<div class="title">
		<h4>{{title}}</h4>
	</div>
</template>

<script>
export default {
	props: ['title'],
	data() {
		return {

		}
	}
}
</script>

<style lang="scss">
.title {
	border: 0px solid yellow;
	text-align: center;
	margin-top: 20px;
	h4 {
		border: 1px solid darken(#e2e2e2, 30%);
		background-color: #333;
		margin: 0;
		width: 95%;
		font-weight: 600;
		color: #fff;
		padding: 7px;
	}
}
</style>


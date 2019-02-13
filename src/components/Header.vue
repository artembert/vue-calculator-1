<template>
	<header class="header">
		<div class="header__logo">Logo</div>
		<div class="header__cart">Total cost: <b>{{totalCost}}</b></div>
	</header>
</template>

<script>
	export default {
		name: "Header",
		computed: {
			totalCost () {
				return this.$store.state.totalCost
			}
		}
	}
</script>

<style scoped lang="stylus">
.header
	background-color #ffffff
	height 64px
	display flex
	justify-content space-between
	align-items center
	padding 0 20px
	box-shadow 0 1px 2px 0 rgba(60,64,67,.3), 0 2px 6px 2px rgba(60,64,67,.15)
	&__logo
		font-weight bold
		font-size 40px
		line-height 1
		font-family monospace
	&__cart
		padding 10px 20px
		background: #f1f3f4;
		color: #80868b;

</style>

<template>
	<div class="calculator-row">
		<p><b>{{title}}</b></p>
		<p>{{price}}</p>
		<p>{{priceUnit}}</p>
		<label>
			Введите количество
			<input type="text" class="calculator-row__title">
		</label>
	</div>
</template>

<script>


	export default {
		name: "Calculator-row",
		props: {
			title: String,
			price: Number,
			priceUnit: String,
		},
		data() {
			return {
			};
		},
		methods: {
		}
	}
</script>

<style scoped lang="stylus">
	.calculator-row
		display flex
		align-items center
		justify-content space-between
		padding 20px
		border 1px solid #eeeeee

		&__title
			font-weight bold

</style>

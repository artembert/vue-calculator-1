<template>
	<div class="calculator">
		<div class="calculator__inner">
			<CalculatorRow
				v-for="row in prices"
				:key="row.id"
				:title="row.title"
				:price="row.price"
				:priceUnit="row.priceUnit"
			/>
			<button type="button" @click="getData">getData()</button>
		</div>
	</div>
</template>

<script>
	import CalculatorRow from '@/components/Calculator-row.vue'

	export default {
		name: "Calculator",
		components: {
			CalculatorRow,
		},
		data() {
			return {
				pricesUrl: 'https://my-json-server.typicode.com/artembert/json-placeholder__calculator/prices',
				prices: null
			};
		},
		methods: {
			getData() {
				this.axios.get(this.pricesUrl)
				.then((response) => {
					this.prices = response.data;
				})
			}
		}
	}
</script>

<style scoped lang="stylus">
	.calculator
		background-color #b6a88b
		padding 40px 0

		&__inner
			background-color #ffffff
			width 748px
			margin 0 auto
			padding 10px
</style>

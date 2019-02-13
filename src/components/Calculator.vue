<template>
	<div class="calculator">
		<div class="calculator__inner">
			<table>
			<CalculatorRow
				v-for="row in prices"
				:key="row.id"
				:title="row.title"
				:price="row.price"
				:priceUnit="row.priceUnit"
			/>
			</table>
			<button type="button" @click="getData">getData()</button>
			<button type="button" @click="increaseTotalCost">this.$store.commit('increment')</button>
		</div>
		<div class="calculator__total">{{totalCount}}</div>
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
		computed: {
			totalCount() {
				return this.$store.state.count
			}
		},
		methods: {
			getData() {
				this.axios.get(this.pricesUrl)
				.then((response) => {
					this.prices = response.data;
				})
			},
			increaseTotalCost() {
				this.$store.commit('increment')
			},
		}
	}
</script>

<style scoped lang="stylus">
	.calculator
		box-shadow: 0 1px 2px 0 rgba(60,64,67,.3), 0 1px 3px 1px rgba(60,64,67,.15)
		border-radius: 6px;
		background-color: #f1f3f4;
		padding 20px

		&__inner
			border-radius: 6px;
			background-color #ffffff
			margin 0 auto
			padding 10px
	button
		margin 10px
</style>

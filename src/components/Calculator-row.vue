<template>
	<tr class="calculator-row">
		<td class="calculator-row__title">{{title}}</td>
		<td>{{price}}
		{{priceUnit}}</td>
		<td>
			<label>
				Количество
				<input
					type="number"
					v-model.number="count"
					@change="changeCount(rowCost)"
				>
			</label>
		</td>
		<td>{{rowCost}}</td>
	</tr>
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
				count: null
			};
		},
		computed: {
			rowCost() {
				return this.price * this.count
			}
		},
		methods: {
			changeCount(rowCost) {
				this.$emit('change-count', rowCost)
			}
		}
	}
</script>

<style scoped lang="stylus">
	.calculator-row
		/*display flex*/
		/*align-items center*/
		/*justify-content space-between*/
		padding 20px
		border 1px solid #eeeeee

		&__title
			font-weight bold

	td
		padding 7px 20px
		text-align left
		white-space nowrap
</style>

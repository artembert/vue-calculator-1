<template>
  <div class="home">
		<Calculator/>
  </div>
</template>

<script>
// @ is an alias to /src
import Calculator from '@/components/Calculator.vue'

export default {
  name: 'home',
  components: {
		Calculator,
  }
}
</script>
<style scoped lang="stylus">
*
	box-sizing border-box
</style>

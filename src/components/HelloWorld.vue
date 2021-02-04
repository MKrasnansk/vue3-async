<template>
	<input type="number" v-model="value" />
	<p>moja hodnota: {{ value }}, {{ triple }}</p>
</template>

<script>
import { toRefs, watchEffect, reactive } from 'vue'

export default {
	name: 'HelloWorld',
	setup() {
		let state = reactive({
			value: 0,
			triple: 0
		})
		watchEffect(() => {
			state.triple = state.value * 3
		})
		return {
			...toRefs(state)
		}
	}
}
</script>

<style scoped>
input {
	font-size: 2em;
}
</style>

<template>
	<h1>Async Component</h1>
	<p>{{ lastName }}, {{ firstName }}</p>
</template>

<script>
function fetchUser() {
	return new Promise(function(resolve) {
		setTimeout(() => {
			resolve({
				firstName: 'Michal',
				lastName: 'Krasnansky'
			})
		}, 3000)
	})
}
export default {
	name: 'AsyncComponent',
	async setup() {
		const { firstName, lastName } = await fetchUser()
		return { firstName, lastName }
	}
}
</script>

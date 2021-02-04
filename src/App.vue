<template>
	<HelloWorld />
	<Riki-1 />
	<div>
		<Suspense>
			<template #default>
				<async-component />
			</template>
			<template #fallback>
				Wait for it..
			</template>
		</Suspense>
	</div>
</template>

<script>
import AsyncComponent from './components/AsyncComponent.vue'
import HelloWorld from './components/HelloWorld.vue'
import Riki1 from './components/Riki1.vue'

export default {
	name: 'App',
	components: {
		HelloWorld,
		Riki1,
		AsyncComponent
	}
}
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
#insideHeder {
	border: 1px solid red;
}
</style>

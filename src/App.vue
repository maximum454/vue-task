<template>
	<div id="app">
		<test-task></test-task>
	</div>
</template>

<script>
import TestTask from "@/components/TestTask";

export default {
	name: 'App',
	components: {
		TestTask,
	}
}
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
}
</style>

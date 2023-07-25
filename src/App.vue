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
*{
	margin: 0;
	padding: 0;
}
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	box-sizing: border-box;
	padding: 20px;
}
</style>

<template>
	<div class="home">
		<h2>Home</h2>
		<Login />
	</div>
</template>

<script>
import Login from '../components/Login.vue'

export default {
	name: "Home",
	components: {
		Login
	}
}
</script>

<style scoped>

</style>
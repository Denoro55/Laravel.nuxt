<template>
	<div>
		<h1>Hello {{ user.name }}!</h1>
		<nuxt-link to="/">Home page</nuxt-link>
		<nuxt-link to="/me">Me</nuxt-link>
	</div>
</template>

<script>
    export default {
        // https://github.com/nuxt-community/axios-module
        async asyncData({ app }) {
            const user = await app.$axios.$get('/me');
            return { user };
        },
    };
</script>
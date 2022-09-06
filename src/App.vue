<template>
	<NavMenu />
	<router-view/>
	<PageFooter />
</template>

<style lang="scss">

</style>

<script>
	import NavMenu from '@/components/NavMenu'
	import PageFooter from '@/components/PageFooter'

	export default {
		name: 'App',
		components: {
			NavMenu,
			PageFooter
		}
	}

</script>
<script lang="ts">
	import Navbar from './navbar.svelte';

	export let title = 'Header';
    export let pageTitle = '';
	export let active = '/';
</script>

<svelte:head>
    <title>{pageTitle ? `LAGbag - ${pageTitle}` : 'LAGbag'}</title>
</svelte:head>
<Navbar {active} />
<div class="page-header">
	<h1>{title}</h1>
</div>

<style>
	.page-header {
		padding: 10px;
		text-align: center;
		color: white;
		background-color: rgb(72, 102, 47);
		font-size: 40px;
	}
</style>

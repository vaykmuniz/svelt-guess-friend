<script>
	import Header from '../components/Header/Header.svelte';
</script>

<div class="mainContainer">
	<Header />
	<main class='mainContainer'>
		<slot />
	</main>
</div>

<style>
	.mainContainer {
		height: 100%;
		width: 100%;
		background-color: aquamarine;
	}
</style>

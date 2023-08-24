<script>
	import Header from '../components/Header/Header.svelte';
</script>

<div class="mainContainer">
	<Header />
	<main class="mainContainer">
		<slot />
	</main>
</div>

<style>
	.mainContainer {
		height: 100vh;
		width: 100vw;
		background-color: whitesmoke;
	}
</style>

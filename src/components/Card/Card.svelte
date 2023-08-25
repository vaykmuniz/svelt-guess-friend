<script lang="ts">
	export let title: string = '';
</script>

<div class="card">
	<h1 class="title">{title}</h1>
	<slot />
</div>

<style>
	.title {
		font-weight: bold;
	}

	.card {
		padding: 8px;
		background-color: cornflowerblue;
		width: auto;
		min-width: 200px;
		border-radius: 16px;

		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		align-items: flex-start;
	}
</style>

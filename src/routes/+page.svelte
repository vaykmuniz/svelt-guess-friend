<script lang="ts">
	import Card from '../components/Card/Card.svelte';
	import { APPS_LIST } from '../shared/conts/index';
	let list: string[] = [];
	let username: string = '';

	function addApp(friend: string) {
		console.log(list);
		list.push(friend);
		list = list;
	}
</script>

<svelte:head>
	<title>ZUP</title>
	<meta name="description" content="ZUP?" />
</svelte:head>

<section class="column">
	<div class="row">
		<h1>Who are you?</h1>
		<div class="row">
			<p>Name:</p>
			<input bind:value={username} />
		</div>
	</div>

	<div class="row">
		<h1>Select Modules:</h1>
		{#each APPS_LIST as app}
			<label for="appname" class="badge"
				>{app.name}
				<input
					class="unset"
					id="appname"
					name="appname"
					type="checkbox"
					on:click={() => addApp(app.name)}
					value={app.name}
				/>
			</label>
		{/each}
	</div>

	<div class="column">
		{#each list as app}
			<Card title={app} />
		{/each}
	</div>
</section>

<style>
	.unset {
		all: unset;
	}

	.column {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.row {
		display: inline-flex;
		justify-content: center;
		align-items: center;
		flex-wrap: wrap;

		gap: 8px;
	}

	.badge {
		all: unset;

		height: 30px;
		min-width: 80px;
		padding: 2px;
		background-color: white;
		border-radius: 8px;

		display: inline-flex;
		justify-content: center;
		align-items: center;

		cursor: pointer;
	}

	.badge:hover {
		background-color: lightgreen;
		color: white;
	}
</style>

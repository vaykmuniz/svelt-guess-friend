<script lang="ts">
	import { FRIENDS_LIST } from '../shared/conts/index';
	let list: string[] = [];

	function addFriend(friend: string) {
		console.log(list);
		list.push(friend);
		list = list;
	}
</script>

<svelte:head>
	<title>Guess the friend</title>
	<meta name="description" content="Svelt test game" />
</svelte:head>

<section class="column">
	<div class="row">
		<h1>Guess the friend:</h1>
		{#each FRIENDS_LIST as friend}
			<button class="badge" on:click={() => addFriend(friend.name)}>
				{friend.name}
			</button>
		{/each}
	</div>
	<div class="row">
		<h2>Clicked Friends:</h2>
		{#each list as clickedFriend}
			<div class="badge">{clickedFriend}</div>
		{/each}
	</div>
</section>

<style>
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

		height: 20px;
		width: 50px;
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

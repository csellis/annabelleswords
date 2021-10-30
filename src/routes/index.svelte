<script context="module">
	export const prerender = true;
</script>

<script>
	import Counter from '$lib/Counter.svelte';

	let words = [
		'what',
		'that',
		'there',
		'where',
		'know',
		'now',
		'night',
		'knight',
		'not',
		'knot',
		'could',
		'should',
		'would',
		'thought',
		'through'
	];
	let current = Math.floor(Math.random() * words.length);

	function selectRandom() {
		let random = Math.floor(Math.random() * words.length);
		if (random === current) {
			selectRandom();
		} else {
			current = random;
		}
	}
</script>

<svelte:head>
	<title>Annabelle's Flash Cards</title>
</svelte:head>

<main>
	<h1>Annabelle's Flash Cards</h1>
	<h2>
		{words[current]}
	</h2>

	<button on:click={selectRandom}>Random</button>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		height: 100%;
		flex: 1 100%;
	}

	h1 {
		font-size: 2.5rem;
	}
	h2 {
		display: grid;
		align-self: center;
		font-size: 2rem;
		font-weight: 700;
		flex: 1 100%;
	}
</style>

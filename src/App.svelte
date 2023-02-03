<script>
  import Character from './lib/Character.svelte';
	let characters = [];
	let page = 1;
	async function loadCharacters() {
		const response = await fetch(
			'https://rickandmortyapi.com/api/character?page=' + page
		);
		const data = await response.json();
		characters = data.results;
	}
	loadCharacters();

	

	function nextPage() {
		page++;
		loadCharacters();
	}

	function previousPage() {
		if (page > 1) {
			page--;
			loadCharacters();
		}
	}
</script>
<h1>
	<span>Rick and Morty</span>
	<img class='portal' src="https://i.pinimg.com/originals/68/1b/00/681b00d06b2e20e4fe7c5dd5d2fcc63d.png" alt="rick portal">
</h1>

<div>
	<div class="buttons">
		<button on:click={previousPage} disabled={page === 1}>previous</button>
		<button on:click={nextPage}>next</button>
	</div>
</div>

<div class="container">
	{#each characters as character}
    <Character character={character} />
	{/each}
</div>

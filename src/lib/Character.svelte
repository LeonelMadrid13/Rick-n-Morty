<script>
	export let character;

    function status(status) {
		if (status === 'Alive') {
			return 'alive';
		} else if (status === 'Dead') {
			return 'dead';
		} else {
			return 'unknown';
		}
	}
</script>

<div class="characters">
	<h2 class="charName">{character.name}</h2>
	<img class="identification" src={character.image} alt={character.name} />
	<h4>
		<span class="charSpecies">{character.species}</span>
		<span class={status(character.status)}>{character.status}</span>
	</h4>
</div>

<style>
	.characters {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin: 1rem;
	}
	.charName {
		font-size: 1.5rem;
		font-weight: bold;
	}
	.charSpecies {
		font-size: 1.2rem;
		font-weight: bold;
	}
	.charStatus {
		font-size: 1.2rem;
		font-weight: bold;
	}
	.identification {
		width: 200px;
		height: 200px;
		border-radius: 50%;
	}

	.alive {
		color: green;
	}

	.dead {
		color: red;
	}

	.unknown {
		color: yellow;
	}
</style>

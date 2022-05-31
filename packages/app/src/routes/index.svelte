<script lang="ts">
	import { Suits } from "$lib/assets/suits";
	import Card from "$lib/components/Card.svelte";
</script>

<p>There is should be a card game</p>

<div class="cards">
	<div class="row">
		{#each [1, 2, 3, 4, 5, 6, 7] as value}
			<Card suit={Suits.Bugfix} {value} />
		{/each}
	</div>
	<div class="row">
		{#each [1, 2, 3, 4, 5, 6, 7] as value}
			<Card suit={Suits.Eye} {value} --card-suit-color="#fec415" />
		{/each}
	</div>
	<div class="row">
		{#each [1, 2, 3, 4, 5, 6, 7] as value}
			<Card suit={Suits.Index} {value} --card-suit-color="#fec415" />
		{/each}
	</div>
	<div class="row">
		{#each [1, 2, 3, 4, 5, 6, 7] as value}
			<Card suit={Suits.Send} {value} />
		{/each}
	</div>
	<div class="row">
		{#each [1, 2, 3, 4, 5, 6, 7] as value}
			<Card suit={Suits.Skip} {value} />
		{/each}
	</div>
	<div class="row">
		{#each [1, 2, 3, 4, 5, 6, 7] as value}
			<Card suit={Suits.Swap} {value} --card-suit-color="#fec415" />
		{/each}
	</div>
</div>

<style>
	:global(body) {
		color: white;
		background-color: #1e1e1e;
	}

	.cards {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	.row {
		display: flex;
		gap: 1rem;
	}
</style>

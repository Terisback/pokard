<script lang="ts">
	import { Suits } from "$lib/assets";
	import { cardColor } from "$lib/utils";
	import Card from "./Card.svelte";
	let hand = [
		{ suit: Suits.Bugfix, value: 6 },
		{ suit: Suits.Eye, value: 1 },
		{ suit: Suits.Send, value: 2 },
		{ suit: Suits.Skip, value: 5 },
		{ suit: Suits.Index, value: 4 },
	];
</script>

<div class="hand">
	{#each hand as card, index}
		{@const mid = (index - hand.length / 2 + 0.5) / hand.length}
		{@const offset = Math.cos(mid * Math.PI) * -5 + 10}
		{@const angle = Math.sin(mid * Math.PI) * 3}
		<div
			class="card-wrapper"
			style="transform: rotate({angle}deg) translateY({offset}px)"
		>
			<Card
				suit={card.suit}
				value={card.value}
				--card-suit-color={cardColor(card.suit)}
			/>
		</div>
	{/each}
</div>

<style>
	.hand {
		display: flex;
		justify-content: center;
		gap: -1rem;
	}

	.card-wrapper {
		margin-left: -0.5rem;
		margin-right: -0.5rem;
		transition: all 0.1s;
		transform: rotateY(180deg);
	}

	.card-wrapper:hover {
		margin-top: -4rem;
	}
</style>

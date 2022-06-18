<script lang="ts">
	import { Suits } from "$lib/assets";
	import Card from "$lib/components/Card.svelte";
	import Player from "$lib/components/Player.svelte";
	import { cardColor } from "$lib/utils";
	let hand = [
		{ suit: Suits.Bugfix, value: 6 },
		{ suit: Suits.Eye, value: 1 },
		{ suit: Suits.Send, value: 2 },
		{ suit: Suits.Skip, value: 5 },
		{ suit: Suits.Index, value: 4 },
	];
</script>

<div class="hand">
	{#each hand as card}
		<!-- удалил стиль (исправить) -->
		<div class="card-wrapper">
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
		height: inherit;
		display: flex;
		justify-content: center;
		align-items: flex-end;
		gap: -1rem;
	}

	.card-wrapper {
		box-shadow: none;
		cursor: pointer;
		transition: all 0.3s;
	}
	:global(main) {
		width: 100vw;
		height: 90vh;
	}
	.card-wrapper:hover {
		transition: all 0.2s;
		transform: scale(1.1);
		z-index: 1;
	}
	.card-wrapper:active {
		transform-style: preserve-3d;
		position: absolute;
		left: 48%;
		transition: 0.8s;
		transform: rotateY(180deg) rotateX(45deg) rotateZ(0deg) scale(1.05)
			translateY(-50vh);
		animation: entry 0.1s linear 0.1;
	}

	:global(body) {
		margin: 0;
		padding: 0;
		color: white;
		background-color: #1e1e1e;
	}
</style>

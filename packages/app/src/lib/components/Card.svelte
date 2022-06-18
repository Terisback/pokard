<script lang="ts">
	import Bugfix from "$lib/assets/Bugfix.svelte";
	import Eye from "$lib/assets/Eye.svelte";
	import Index from "$lib/assets/Index.svelte";
	import Send from "$lib/assets/Send.svelte";
	import Skip from "$lib/assets/Skip.svelte";
	import Swap from "$lib/assets/Swap.svelte";
	import { Suits } from "$lib/assets";
	import type { SvelteComponent } from "svelte";

	export let suit: Suits;
	export let value: number;

	let suit_icon: typeof SvelteComponent;
	switch (suit) {
		case Suits.Bugfix:
			suit_icon = Bugfix;
			break;
		case Suits.Eye:
			suit_icon = Eye;
			break;
		case Suits.Index:
			suit_icon = Index;
			break;
		case Suits.Send:
			suit_icon = Send;
			break;
		case Suits.Skip:
			suit_icon = Skip;
			break;
		case Suits.Swap:
			suit_icon = Swap;
			break;
	}
</script>

<div class="card">
	<div class="card-face front">
		<div class="value">
			<span>{value}</span>
			<svelte:component this={suit_icon} />
		</div>

		<div class="suit">
			<svelte:component this={suit_icon} />
		</div>
	</div>
	<div class="card-face back" />
</div>

<style>
	.card {
		position: relative;
		width: 6rem;
		transform-style: preserve-3d;
		padding: 5px;
	}
	.card-face {
		position: relative;
		--card-padding: 0.4rem;
		aspect-ratio: 64 / 89;
		padding: var(--card-padding);
		border-radius: 0.5em;
		backface-visibility: hidden;
	}
	.front {
		color: var(--card-suit-color, #57585a);
		background-color: var(--card-background, white);
		box-shadow: 0 0 0.5rem #000a;
		display: flex;
		overflow: hidden;
	}
	.back {
		transform: rotateY(180deg); /* Поворачиваем текст */
		background-image: url("https://deti-online.com/img/raskraski-cat/druzhba-eto-chudo.jpg");
		background-position: 50% 50%;
		background-size: cover;
		position: absolute;
		top: 0;
		left: 0;
		bottom: 0;
		right: 0;
	}

	.value {
		align-self: flex-start;

		font-size: x-large;
		font-weight: bolder;

		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.suit {
		flex: 1 1;
		align-self: flex-end;
	}

	.suit :global(svg) {
		width: -webkit-fill-available;
		height: auto;
	}
</style>

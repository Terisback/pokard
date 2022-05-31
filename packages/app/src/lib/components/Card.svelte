<script lang="ts">
	import Bugfix from "$lib/assets/Bugfix.svelte";
	import Eye from "$lib/assets/suits/Eye.svelte";
	import Index from "$lib/assets/suits/Index.svelte";
	import Send from "$lib/assets/suits/Send.svelte";
	import Skip from "$lib/assets/suits/Skip.svelte";
	import Swap from "$lib/assets/suits/Swap.svelte";
	import { Suits } from "$lib/assets/suits";
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
	<div class="value">
		<span>{value}</span>
		<svelte:component this={suit_icon} />
	</div>

	<div class="suit">
		<svelte:component this={suit_icon} />
	</div>
</div>

<style>
	.card {
		--card-padding: 0.4rem;

		position: relative;
		width: 6rem;
		padding: var(--card-padding);
		aspect-ratio: 64 / 89;
		overflow: hidden;

		border-radius: 0.5em;
		color: var(--card-suit-color, #57585a);
		background-color: var(--card-background, white);

		display: flex;
		justify-content: space-between;
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

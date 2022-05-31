<script lang="ts">
	import type { SvelteComponent } from "svelte";

	export let suit: typeof SvelteComponent;
	export let value: number;
</script>

<div class="card">
	<div class="value">
		<span>{value}</span>
		<svelte:component this={suit} />
	</div>

	<div class="suit">
		<svelte:component this={suit} />
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

<script lang="ts">
	import type { SvelteComponent } from "svelte";

	export let suit: typeof SvelteComponent;
	export let value: number;
</script>

<div class="card">
	<div class="corner top left">
		<span>{value}</span>
		<svelte:component this={suit} />
	</div>

	<div class="corner bottom right upside-down">
		<span>{value}</span>
		<svelte:component this={suit} />
	</div>

	<div class="corner fill top right" />
	<div class="corner fill bottom left upside-down" />

	<div class="inner">
		{#if value == 1}
			<svelte:component this={suit} />
		{:else}
			<div class="row">
				{#if value >= 4}
					<svelte:component this={suit} />
					<svelte:component this={suit} />
				{:else}
					<svelte:component this={suit} />
				{/if}
			</div>
			<div class="row">
				{#if value >= 5}
					{#each [{}, {}, {}].slice(0, value - 4) as _}
						<svelte:component this={suit} />
					{/each}
				{:else if value == 3}
					<svelte:component this={suit} />
				{/if}
			</div>
			<div class="row">
				{#if value >= 4}
					<svelte:component this={suit} />
					<svelte:component this={suit} />
				{:else}
					<svelte:component this={suit} />
				{/if}
			</div>
		{/if}
	</div>
</div>

<style>
	.card {
		--card-padding: 0.4rem;

		position: relative;
		width: 10rem;
		aspect-ratio: 64 / 89;
		overflow: hidden;

		border-radius: 0.5em;
		color: var(--card-suit-color, #57585a);
		background-color: var(--card-background, beige);
		box-shadow: inset 0 0 0 var(--card-padding) white;

		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.inner {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.inner > :global(svg) {
		width: 7.5rem;
		height: 7.5rem;
	}

	.row {
		flex-basis: 3rem;
		display: flex;
	}

	.row > :global(svg) {
		width: 3rem;
		height: 3rem;
	}

	.corner {
		position: absolute;
		padding: 0.1rem;

		font-weight: bolder;
		background-color: white;
		border-bottom-right-radius: 0.5em;

		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.fill {
		padding: 0.4rem;
		border-bottom-right-radius: initial;
		border-bottom-left-radius: 0.5rem;
	}

	/* Utils */

	.top {
		top: var(--card-padding);
	}

	.right {
		right: var(--card-padding);
	}

	.bottom {
		bottom: var(--card-padding);
	}

	.left {
		left: var(--card-padding);
	}

	.upside-down {
		transform: rotate(0.5turn);
	}
</style>

<script lang="ts">
	import Card from "$lib/components/Card.svelte";
	import Bugfix from "$lib/assets/suits/Bugfix.svelte";
	import Eye from "$lib/assets/suits/Eye.svelte";
	import Index from "$lib/assets/suits/Index.svelte";
	import Send from "$lib/assets/suits/Send.svelte";
	import Skip from "$lib/assets/suits/Skip.svelte";
	import Swap from "$lib/assets/suits/Swap.svelte";
</script>

<p>There is should be a card game</p>

<div class="row">
	{#each [1, 2, 3, 4, 5, 6, 7] as val}
		<Card suit={Bugfix} value={val} />
	{/each}
</div>
<div class="row">
	{#each [1, 2, 3, 4, 5, 6, 7] as val}
		<Card suit={Eye} value={val} --card-suit-color="#fec415" />
	{/each}
</div>
<div class="row">
	{#each [1, 2, 3, 4, 5, 6, 7] as val}
		<Card suit={Index} value={val} --card-suit-color="#fec415" />
	{/each}
</div>
<div class="row">
	{#each [1, 2, 3, 4, 5, 6, 7] as val}
		<Card suit={Send} value={val} />
	{/each}
</div>
<div class="row">
	{#each [1, 2, 3, 4, 5, 6, 7] as val}
		<Card suit={Skip} value={val} />
	{/each}
</div>
<div class="row">
	{#each [1, 2, 3, 4, 5, 6, 7] as val}
		<Card suit={Swap} value={val} --card-suit-color="#fec415" />
	{/each}
</div>

<style>
	:global(body) {
		color: white;
		background-color: #1e1e1e;
	}

	.row {
		display: flex;
		gap: 1rem;
	}
</style>

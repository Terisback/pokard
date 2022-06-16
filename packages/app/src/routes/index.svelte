<script lang="ts">
	import { Suits } from "$lib/assets";
	import Card from "$lib/components/Card.svelte";
	import Hand from "$lib/components/Hand.svelte";
</script>

<p>There is should be a card game</p>

<Hand />

<style>
	:global(body) {
		color: white;
		background-color: #1e1e1e;
	}
</style>

<script>
	import { fade } from 'svelte/transition';
	let visible = true;
</script>

<button on:click={() => (visible = !visible)}>Toggle</button>

{#if visible}
	<div in:fade={{ duration: 9000 }}>This element will fade in and out.</div>
{/if}

<style>
	div {
		transition: opacity 0.5s ease;
		background-color: red;
	}
</style>

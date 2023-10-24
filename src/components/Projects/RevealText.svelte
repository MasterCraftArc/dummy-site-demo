<script>
	import { fade, fly } from 'svelte/transition';
	import { onMount, onDestroy } from 'svelte';

	let animate = false; // Set it to true initially to show the element
	let targetElement;
	let spanElement;
	let animationPlayed = false;

	export let span;
	export let text;

	const observer = new IntersectionObserver((entries, observer) => {
		if (entries[0].isIntersecting && !animationPlayed) {
			animate = true;
			animationPlayed = true;
		}
	});

	onMount(() => {
		observer.observe(targetElement);
	}, 1500);

	onDestroy(() => {
		observer.disconnect();
	});
</script>

<div bind:this={targetElement} class:animate class="lines">
	<div class="overflow">
		{#if animate}
			<h1 in:fly={{ y: 500 }} out:fade={{ duration: 300 }}>
				<span class="s" bind:this={spanElement}>{span}</span>
				{text}
			</h1>
		{/if}
	</div>
</div>

<script>
	import { fade, fly } from 'svelte/transition';
	import { onMount } from 'svelte';

	let animate = false;
	let targetElement;
	let spanElement;
	export let span;
	export let text;
	let observer;

	onMount(() => {
		observer = new IntersectionObserver((entries) => {
			entries.forEach((entry) => {
				if (entry.isIntersecting) {
					animate = true;
					observer.disconnect();
				}
			});
		});

		observer.observe(targetElement);

		return () => {
			if (observer) {
				observer.disconnect();
			}
		};
	});

	$: {
		if (animate) {
			observer.observe(targetElement);
		}
	}
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

<style>
	h1 span {
		color: #9acc5b;
		text-shadow: 0 0 5px #9acc5b;
	}
	.overflow {
		padding-bottom: 7rem;
	}
</style>

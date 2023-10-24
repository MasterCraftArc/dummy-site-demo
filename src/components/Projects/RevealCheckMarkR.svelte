<script>
	import checkMark from '../../images/svg/check-mark.svg';
	import { fly } from 'svelte/transition';
	import { onMount, onDestroy } from 'svelte';

	export let text;
	let animate = false;
	let targetElement;
	let animationPlayed = false;

	const observer = new IntersectionObserver((entries, observer) => {
		entries.forEach((entry) => {
			if (entry.isIntersecting && !animationPlayed) {
				animate = true;
				animationPlayed = true;
			}
		});
	});

	onMount(() => {
		observer.observe(targetElement);
	}, 1500);

	onDestroy(() => {
		observer.disconnect();
	});
</script>

<div class="text-div" bind:this={targetElement} class:animate>
	{#if animate}
		<img
			transition:fly={{
				x: 500,
				duration: 1600,
				delay: 250
			}}
			src={checkMark}
			alt=""
			loading="lazy"
			class="check-mark"
		/>
		<h3
			transition:fly={{
				x: 500,
				duration: 1600,
				delay: 250
			}}
		>
			{text}
		</h3>
	{/if}
</div>

<style>
	.text-div {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 1rem;
	}

	h3 {
		text-align: left;
	}

	.check-mark {
		width: 30px;
		height: 30px;
	}
</style>

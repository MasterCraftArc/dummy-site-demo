<script>
	import zarf from '../../images/svg/zarf.svg';
	import zarfPlatform from '../../images/svg/zarf-platform.svg';
	import { onMount, onDestroy } from 'svelte';
	import { fly } from 'svelte/transition';
	import { backInOut } from 'svelte/easing';

	let animate = false;
	let targetElement;
	let animationPlayed = false;
	export let character
	export let platform

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

<div class="image-holder" bind:this={targetElement} class:animate>
	{#if animate}
		<img
			in:fly={{
				x: 500,
				duration: 1600,
				delay: 250
			}}
			src={character}
			alt="zarf"
			loading="lazy"
			class="zarf"
		/>

		<img
			in:fly={{
				x: 500,
				duration: 1600,
				delay: 250
			}}
			src={platform}
			alt="zarf-platform"
			loading="lazy"
			class="zarf-platform"
		/>
	{/if}
</div>

<style>
	.image-holder {
		display: flex;
		flex-direction: column;
	}

	.zarf {
		animation: float 3s infinite;
		width: 200px;
		height: 200px;
	}

	.zarf-platform {
		width: 200px;
		height: 200px;
		z-index: -1;
		margin-top: -2rem;
	}
</style>

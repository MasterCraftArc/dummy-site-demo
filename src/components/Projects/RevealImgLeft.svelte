<script>
	import { onMount, onDestroy } from 'svelte';
	import { fly } from 'svelte/transition';

	let animate = false;
	let targetElement;
	let animationPlayed = false;
	export let character;
	export let platform;

	const observer = new IntersectionObserver((entries) => {
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
				x: -500,
				duration: 1600,
				delay: 250
			}}
			src={character}
			alt="zarf"
			loading="lazy"
			class="leapfrog"
		/>

		<img
			in:fly={{
				x: -500,
				duration: 1600,
				delay: 250
			}}
			src={platform}
			alt="zarf-platform"
			loading="lazy"
			class="platform"
		/>
	{/if}
</div>

<style>
	@keyframes bounce {
		0%,
		20%,
		50%,
		80%,
		100% {
			transform: translateY(0);
		}
		40% {
			transform: translateY(-30px);
		}
		60% {
			transform: translateY(-15px);
		}
	}
	.image-holder {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.leapfrog {
		height: 200px;
		width: 200px;
		animation: bounce 2s infinite;
	}
	.platform {
		height: 300px;
		width: 300px;
		margin-top: -170px;
		z-index: -1;
	}
</style>

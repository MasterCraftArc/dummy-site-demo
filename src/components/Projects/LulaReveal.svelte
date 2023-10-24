\<script>
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
	@keyframes fly {
		0% {
			transform: translateY(100px);
			opacity: 1;
		}
		25% {
			transform: translateY(75px);
			opacity: 0.75;
		}
		50% {
			transform: translateY(50px);
			opacity: 0.7;
		}
		75% {
			transform: translateY(25px);
			opacity: 0.4;
		}
		100% {
			transform: translateY(0px);
			opacity: 0;
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
		animation: fly 6s infinite;
	}

	.platform {
		height: 300px;
		width: 300px;
		z-index: -1;
	}
</style>

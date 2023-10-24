<script>
	import Typewriter from 'svelte-typewriter';

	export let headings = [''];
	export let glowHeader = '';

	let typewriterProps = {
		mode: 'loopOnce',
		interval: 90,
		keepCursorOnFinish: 100
	};
</script>

<Typewriter {...typewriterProps}>
	{#each headings as heading (heading)}
		{#if heading.includes(glowHeader)}
			<h1><span class="glow">{glowHeader}</span></h1>
		{:else}
			<h1>{heading}</h1>
		{/if}
	{/each}
</Typewriter>

<style>
	:root {
		--cursor-color: #a5bdfc;
		--cursor-width: 10px;
	}

	.glow {
		animation: glow-animation 1.5s infinite alternate;
	}

	@keyframes glow-animation {
		0% {
			text-shadow: 0 0 10px #a5bdfc;
		}

		100% {
			text-shadow: 0 0 20px #a5bdfc;
		}
	}

	@media screen and (max-width: 1200px) {
		h1 {
			width: 350px;
			height: 100px;
		}
	}
</style>

<script>
	import LeftRight from '../LeftRight.svelte';
	import ai from '../../images/svg//ai-for-national-security/ai-for-national-security.svg';
	import Button from '../../components/Button.svelte';
	import CardGlow from '../Home/CardGlow.svelte';
	import headerGlow from '../../images/svg/product-glows/zarf-header-glow.svg';
	import blueGlow from '../../images/svg/product-glows/zarf-card-glow.svg';
	import MobileSection1 from './Mobile/MobileSection1.svelte';
	$: innerWidth = 0;
</script>

<svelte:window bind:innerWidth />

{#if innerWidth < 1200}
	<MobileSection1 />
{:else}
	<section>
		<div>
			<div class="foreground">
				<div class="h1-container">
					<img src={headerGlow} alt="header-glow" loading="lazy" class="glow" />
					<h1>AI For <span>National</span> Security</h1>
					<p>Coming Soon</p>
				</div>
			</div>
		</div>
		<LeftRight>
			<div slot="left">
				<img src={ai} alt="" />
			</div>
			<div slot="right">
				<div class="right">
					<h3>Chat-gpt like experience for Defense systems</h3>
					<h3>Your data, your environment, your mission</h3>
					<Button text="Get Early Access" />
				</div>
			</div>
		</LeftRight>
		<div class="card-glow"><CardGlow glowLeft={blueGlow} glowRight={blueGlow} /></div>
	</section>
{/if}

<style>
	h3 {
		text-shadow: none;
	}
	.foreground {
		position: relative;
	}

	.h1-container {
		position: relative;
		display: inline-block;
	}

	.glow {
		position: absolute;
		top: -10rem;
		left: -20rem;
		z-index: -1;
	}

	.card-glow {
		position: absolute;
		top: 0;
		left: 0;
		z-index: -1;
	}
	p {
		font-size: 50px;
		font-weight: 400;
		line-height: 61px;
		letter-spacing: 0em;
		text-align: center;
	}

	.right {
		display: flex;
		text-align: start;
		gap: 5rem;
		flex-direction: column;
	}

	section {
		padding-top: 5rem;
		gap: 5rem;
	}
</style>

<script>
	import InternalButton from '../InternalButton.svelte';
	import MobileSection1 from './MobileSection1.svelte';
	$: innerWidth = 0;
</script>

<svelte:window bind:innerWidth />
{#if innerWidth && innerWidth < 1200}
	<MobileSection1 />
{:else}
	<section class="section1">
		<div class="text-container">
			<div>
				<h1>Defense Unicorns is</h1>
				<h1><span>A Modern Software Prime</span></h1>
			</div>
			<p>
				We offer everything you need to eliminate IT challenges, grow your business, and have peace
				of mind with expert IT suppoort and services.
			</p>
			<InternalButton link="/ContactUs" text="Contact Us" />
		</div>
		<div class="text-container2">
			<div class="h1-container">
				<h1 class="line-height">Deploy Your <span>Misson</span> Applications</h1>
				<h1 class="line-height">Where Your <span>Mission</span> Demands Are</h1>
			</div>
			<p>
				We offer everything you need to eliminate IT challenges, grow your business, and have peace
				of mind with expert IT suppoort and services.
			</p>
			<InternalButton link="/ContactUs" text="Contact Us" />
		</div>
	</section>
{/if}

<style>
	.line-height {
		line-height: 50px;
	}

	.text-container {
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		gap: 2rem;
	}

	.text-container2 {
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		gap: 2rem;
	}

	section {
		padding-top: 5rem;
		padding-bottom: 0rem;
		background-image: url('../../images/png/Hero.png');
		background-size: cover;
		background-repeat: no-repeat;
		background-position: center center;
		gap: 40rem;
	}

	h1 {
		font-size: 56px;
	}

	@media (max-width: 400px) {
		h1 {
			max-width: 350px;
			height: 100px;
		}
	}
</style>

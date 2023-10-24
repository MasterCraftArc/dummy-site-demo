<script>
	import Button from '../Button.svelte';
</script>

<section class="mobile-section">
	<div class="text-container-mobile">
		<div>
			<h1>Defense Unicorns is a</h1>
			<h1>Modern <span>Software Prime</span></h1>
		</div>
		<Button link="/" text="Contact Us" />
	</div>
	<div class="text-container-mobile2">
		<div>
			<h1 class="mobile">Deploy Your</h1>
			<h1 class="mobile"><span>Mission Applications</span></h1>
			<h1 class="mobile">Where Your</h1>
			<h1 class="mobile"><span>Mission Demands</span></h1>
			<h1 class="mobile">Are</h1>
		</div>
		<p>
			We offer everythiong you need to eliminate IT challenges, grow your business, and have peace
			of mind with expert IT suppoort and services.
		</p>
		<Button link="/" text="Contact Us" />
	</div>
</section>

<style>
	.mobile {
		font-size: 36px;
		line-height: 35px;
	}

	p {
		max-width: 400px;
	}

	h1 {
		height: auto;
	}

	.text-container-mobile2 {
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		gap: 1rem;
	}

	section {
		padding: 10rem 0;
		padding-top: 5rem;
		background-image: url('../../images/png/Hero.png');
		background-size: cover;
		background-repeat: no-repeat;
		background-position: center center;
		gap: 40rem;
	}
</style>

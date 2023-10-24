<script>
	import seven from '../../../images/svg/clock/07.svg';
	import eleven from '../../../images/svg/clock/11.svg';
	import Clock from '../clock.svelte';
</script>

<section>
	<div>
		<h1>AI For <span>National Security</span></h1>
		<h1>Launch Count Down</h1>
	</div>
	<div class="container">
		<div class="text-container">
			<Clock number={seven} />
			<h1>DAYS</h1>
		</div>
		<div class="text-container">
			<Clock number={eleven} />
			<h1>HOURS</h1>
		</div>
	</div>
</section>

<style>
	section {
		padding-top: 0rem;
		gap: 5rem;
	}

	h1 {
		font-size: 36px;
		width: 100vw;
	}

	.text-container {
		width: 250px;
		height: 200px;
		display: flex;
		flex-direction: column;
	}

	.container {
		padding: 5rem;
		border: 2px solid #a5bdfc;
		box-shadow: 0px 0px 15px 20px #a5bdfc;
		border-radius: 25px;
		display: flex;
		align-items: center;
		gap: 3rem;
		justify-content: center;
		width: 100%;
		flex-direction: row;
	}
	@media screen and (max-width: 1200px) {
		.container {
			flex-direction: column;
			gap: 10rem;
		}
	}
</style>

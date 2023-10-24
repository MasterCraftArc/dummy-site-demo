<script>
	import CardGlow from '../Home/CardGlow.svelte';
	import yellowGlow from '../../images/svg/yellow-glow.svg';
	import blueGlow from '../../images/svg/blue-glow.svg';
	import checkmark from '../../images/svg/check-mark.svg';
	import Button from '../Button.svelte';
	import { onMount } from 'svelte';

	let cardObservers = [];
	let cards = [];

	onMount(() => {
		cards.forEach((card, index) => {
			const observer = new IntersectionObserver((entries) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						card.classList.add('fade-in-fwd');
					} else {
						card.classList.remove('fade-in-fwd');
					}
				});
			});
			observer.observe(card);
			cardObservers[index] = observer;
		});
		return () => {
			cardObservers.forEach((observer) => observer.disconnect());
		};
	});
</script>

<section class="section4">
	<div class="card-glow"><CardGlow glowLeft={yellowGlow} glowRight={blueGlow} /></div>
	<div class="card fade-in-fwd" bind:this={cards[0]}>
		<div class="text-container">
			<h3>Rapid ATO</h3>
			<p>
				We accelerate ATO timelines by more than 50%, for some customers in as little as 90 days
			</p>
			<div class="check-holder">
				<div class="checkmark">
					<img src={checkmark} alt="checkmark" loading="lazy" class="check" />
					<p>Classified & open environments</p>
				</div>
				<div class="checkmark">
					<img src={checkmark} alt="checkmark" loading="lazy" class="check" />
					<p>70% NIST 800-53 Tech Control</p>
				</div>
			</div>
			<Button text="Learn More" />
		</div>
	</div>
	<div class="card fade-in-fwd" bind:this={cards[1]}>
		<div class="text-container">
			<h3>Deploy Anywhere</h3>
			<p>Defense Unicorns deliver mission capabilities wherever your mission requires</p>
			<div class="check-holder">
				<div class="checkmark">
					<img src={checkmark} alt="checkmark" loading="lazy" class="check" />
					<p>cloud or on-prem</p>
				</div>
				<div class="checkmark">
					<img src={checkmark} alt="checkmark" loading="lazy" class="check" />
					<p>Land, Air, Space, or Sea</p>
				</div>
			</div>
			<Button text="Learn More" />
		</div>
	</div>
	<div class="card fade-in-fwd" bind:this={cards[2]}>
		<div class="text-container">
			<h3>No Vendor Lock In</h3>
			<p>
				The Defense Unicorns platform baseline is open source, allowing for greater accessibility
			</p>
			<div class="check-holder">
				<div class="checkmark">
					<img src={checkmark} alt="checkmark" loading="lazy" class="check" />
					<p>Infrastructure agnostic</p>
				</div>
				<div class="checkmark">
					<img src={checkmark} alt="checkmark" loading="lazy" class="check" />
					<p>No Platform License</p>
				</div>
			</div>
			<Button text="Learn More" />
		</div>
	</div>
</section>

<style>
	.section4 {
		display: flex;
		justify-content: space-evenly;
		align-items: center;
		flex-direction: row;
		position: relative;
	}

	.card-glow {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		z-index: -1;
	}

	@media (max-width: 1200px) {
		.section4 {
			flex-direction: column;
			gap: 3rem;
		}
	}

	.check {
		width: 30px;
		height: 30px;
	}

	.checkmark {
		display: flex;
		flex-direction: row;
		align-items: center;
		gap: 1rem;
	}

	.text-container {
		display: flex;
		justify-content: center;
		flex-direction: column;
		align-items: flex-start;
		text-align: start;
		gap: 2rem;
	}

	.check-holder {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	.card {
		padding: 3rem 1.5rem;
		height: 300px;
		width: 300px;
		background-color: black;
		border: 2px solid white;
		border-radius: 25px;
		display: flex;
		justify-content: center;
		align-items: center;
		cursor: pointer;
		transform: translateY(-10px);
		opacity: 0;
	}

	.card:hover {
		box-shadow: 10px 0px 20px -5px #a5bdfc, -10px 0px 20px -5px #c547fa, 0px 10px 20px -5px #3f75fc;
	}
</style>

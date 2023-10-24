<script>
	import LeftRight from '../LeftRight.svelte';

	import Cards from './Cards.svelte';
	import eclipse from '../../images/svg/eclipse.svg';
	import CardGlow from '../Home/CardGlow.svelte';
	import blueGlow from '../../images/svg/product-glows/lula-card-glow.svg';
	import Star from '../../images/svg/star.svg';
	import lula from '../../images/svg/lula.svg';
	import lulaPlatform from '../../images/svg/lula-platform.svg';
	import card1 from '../../images/svg/lula-card-imgs/card1.svg';
	import card2 from '../../images/svg/lula-card-imgs/card2.svg';
	import card3 from '../../images/svg/lula-card-imgs/card3.svg';
	import lulaGlow from '../../images/svg/product-glows/lula-header-glow.svg';
	import Imgs2 from './img-orientation/imgs2.svelte';
	import Imgs3 from './img-orientation/imgs3.svelte';
	import Imgs4 from './img-orientation/imgs4.svelte';
	import MobileSection5 from './mobile/MobileSection5.svelte';
	import RevealTextLula from './RevealTextLula.svelte';
	import RevealCheckMarkR from './RevealCheckMarkR.svelte';
	import RevealLula from './LulaReveal.svelte';

	$: innerWidth = 0;
</script>

<svelte:window bind:innerWidth />
{#if innerWidth < 1200}
	<MobileSection5 />
{:else}
	<section class="section3">
		<div>
			<div class="h1-container">
				<img src={lulaGlow} alt="header-glow" loading="lazy" class="glow" />
				<RevealTextLula span="Lula" text="- Kubernetes Compliance Engine" />
			</div>
			<LeftRight>
				<div slot="left" class="left">
					<RevealLula character={lula} platform={lulaPlatform} />
				</div>
				<div slot="right" class="right">
					<RevealCheckMarkR text="Turn your configuration into NIST control verification" />
					<RevealCheckMarkR text="Automate SCA and AO enforcement" />
					<RevealCheckMarkR text="Accelerate your ATO timelines" />
					<RevealCheckMarkR text="Turn compliance as spreadsheet into Compliance as code" />
				</div>
			</LeftRight>
		</div>
		<div>
			<div class="h1-container">
				<img src={lulaGlow} alt="header-glow" loading="lazy" class="glow" />
				<h1>Use <span> Lula</span> for</h1>
			</div>
			<div class="cards">
				<div class="card-glow"><CardGlow glowLeft={blueGlow} glowRight={blueGlow} /></div>
				<div class="card">
					<Cards>
						<span slot="img1" class="eclipse"><Imgs3 background={eclipse} img={card1} /></span>
						<span slot="title"><h3>generate controls from config</h3></span>
						<span slot="text"
							><p>
								Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis doloremque quaerat,
								quo, tempora ea quam autem placeat harum fuga quia nam enim, eligendi rem illum
								tempore! Neque nobis perspiciatis cupiditate.
							</p></span
						>
					</Cards>
					<Cards>
						<span slot="img1" class="eclipse"><Imgs2 background={eclipse} img={card2} /></span>
						<span slot="title"><h3>Validate Controls in runtime</h3></span>
						<span slot="text"
							><p>
								Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis doloremque quaerat,
								quo, tempora ea quam autem placeat harum fuga quia nam enim, eligendi rem illum
								tempore! Neque nobis perspiciatis cupiditate.
							</p></span
						>
					</Cards>
					<Cards>
						<span slot="img1" class="eclipse"><Imgs4 background={eclipse} img={card3} /></span>
						<span slot="title"><h3>Automate Your ATOs</h3></span>
						<span slot="text"
							><p>
								Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis doloremque quaerat,
								quo, tempora ea quam autem placeat harum fuga quia nam enim, eligendi rem illum
								tempore! Neque nobis perspiciatis cupiditate.
							</p></span
						>
					</Cards>
				</div>
			</div>
			<div />
			<div class="links">
				<div class="a-tag">
					<a href="https://github.com/defenseunicorns/lula" target="_blank">
						<img src={Star} alt="" loading="lazy" class="star" /> Star us on Github</a
					>
				</div>
			</div>
		</div>
	</section>
{/if}

<style>
	h3 {
		text-align: left;
	}
	.h1-container {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.glow {
		position: absolute;
		z-index: -1;
	}

	.h1-container h1 {
		position: relative;
		z-index: 1;
	}
	h1 span {
		color: #61afb1;
		text-shadow: 0 0 5px #61afb1;
	}

	h1 {
		padding-bottom: 7rem;
	}

	section {
		gap: 10rem;
		padding-top: 0;
	}

	.card {
		display: flex;
		justify-content: space-evenly;
		width: 100vw;
	}

	.links {
		padding-top: 3rem;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		gap: 2rem;
	}

	a {
		text-decoration: none;
	}

	.star {
		height: 15px;
		width: 15px;
	}

	.a-tag {
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 1rem;
	}

	.a-tag:hover {
		border-radius: 25px;
		background-color: rgba(255, 255, 255, 0.1);
		cursor: pointer;
	}

	.card-glow {
		position: absolute;
		width: 100%;
		height: 100%;
		z-index: -1;
	}
	.right {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		max-width: 45vw;
		gap: 2rem;
	}

	.left {
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}

	h3 {
		padding-top: 1rem;
	}

	.cards {
		display: flex;
		justify-content: space-evenly;
		align-items: center;
	}

	@media (max-width: 1200px) {
		h3 {
			font-size: 24px;
		}

		.card {
			flex-direction: column;
			display: flex;
			justify-content: space-evenly;
			align-items: center;
			gap: 3rem;
		}
	}
</style>

<script>
	import LeftRight from '../LeftRight.svelte';
	import zarf from '../../images/svg/zarf.svg';
	import zarfPlatform from '../../images/svg/zarf-platform.svg';
	import Cards from './Cards.svelte';
	import eclipse from '../../images/svg/eclipse.svg';
	import folder from '../../images/svg/zarf-card-imgs/folder.svg';
	import Imgs from './img-orientation/imgs.svelte';
	import CardGlow from '../Home/CardGlow.svelte';
	import zarfGlow from '../../images/svg/product-glows/zarf-card-glow.svg';
	import Button from '../Button.svelte';
	import Star from '../../images/svg/star.svg';
	import chip from '../../images/svg/zarf-card-imgs/chip.svg';
	import server from '../../images/svg/zarf-card-imgs/server.svg';
	import zarfHeader from '../../images/svg/product-glows/zarf-header-glow.svg';
	import MobileSection2 from './mobile/MobileSection2.svelte';
	import RevealText from './RevealText.svelte';
	import RevealCheckMarkL from './RevealCheckMarkL.svelte';
	import RevealImgRight from './RevealImgRight.svelte';
	$: innerWidth = 0;
	let character = zarf;
	let platform = zarfPlatform;
</script>

<svelte:window bind:innerWidth />
{#if innerWidth < 1200}
	<MobileSection2 />
{:else}
	<section class="section2">
		<div class="text-container">
			<div class="h1-container">
				<img src={zarfHeader} alt="header-glow" loading="lazy" class="glow" />

				<RevealText span="Zarf" text="- Air Gap Softare Delivery" />
			</div>
		</div>
		<div>
			<LeftRight>
				<div slot="left" class="left">
					<RevealCheckMarkL text="Package and Deploy to Air Gap Systems" />
					<RevealCheckMarkL
						text="Consistently deploys the same capabilities for highly disributable systems"
					/>
					<RevealCheckMarkL text="Provides SBOM Support" />
					<RevealCheckMarkL text="Works while connected too!" />
				</div>
				<div slot="right" class="right">
					<RevealImgRight {character} {platform} />
				</div>
			</LeftRight>
		</div>

		<div>
			<div class="h1-container">
				<img src={zarfHeader} alt="header-glow" loading="lazy" class="glow" />
				<h1 class="header-padding">Use <span>Zarf</span> To</h1>
			</div>
			<div class="cards">
				<div class="card-glow"><CardGlow glowLeft={zarfGlow} glowRight={zarfGlow} /></div>
				<div class="card">
					<Cards>
						<span slot="img1" class="eclipse"><Imgs background={eclipse} img={folder} /></span>
						<span slot="title"><h3>Securely Package Apps and Resources</h3></span>
						<span slot="text"
							><p>
								Provides the ability to package a chunk of the internet and then securely deliver
								all of the files and dependencies needed to run an application in adisconnected
								environment.
							</p></span
						>
					</Cards>
					<Cards>
						<span slot="img1" class="eclipse"><Imgs background={eclipse} img={chip} /></span>
						<span slot="title"><h3>Deploy Cloud Apps While Disconnected</h3></span>
						<span slot="text"
							><p>
								Provides the ability to deploy apps declaratively and without internet connectivity.
								Opening up the door for modern cloud capabilities to be deployed in disconnected
								environments.
							</p></span
						>
					</Cards>
					<Cards>
						<span slot="img1" class="eclipse"><Imgs background={eclipse} img={server} /></span>
						<span slot="title"><h3>Easily Maintain Apps While Disconnected</h3></span>
						<span slot="text"
							><p>
								Zarf reduces the skill & resources needed to manage and update applications in
								disconnected environments, ensuring no down time or data loss when updating
								software.
							</p></span
						>
					</Cards>
				</div>
				<div />
			</div>
			<div class="links">
				<div class="a-tag">
					<a href="https://github.com/defenseunicorns/zarf" target="_blank">
						<img src={Star} alt="star" loading="lazy" class="star" /> Star us on Github</a
					>
				</div>
				<Button text="Learn More" link="https://zarf.dev/" />
			</div>
		</div>
	</section>
{/if}

<style>
	.header-padding {
		padding-bottom: 7rem;
	}

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
	.card {
		display: flex;
		justify-content: space-evenly;
		width: 100vw;
	}

	section {
		gap: 10rem;
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
	.left {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		gap: 2rem;
		max-width: 45vw;
	}

	.right {
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

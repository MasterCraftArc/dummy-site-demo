<script>
	import ImgOrientation from '../Projects/img-orientation/imgs.svelte';
	import eclipse from '../../images/svg/eclipse.svg';
	import bullseye from '../../images/svg/careers/section-3-imgs/bullseye.svg';
	import arrowCircle from '../../images/svg/careers/section-3-imgs/arrow-circle.svg';
	import care from '../../images/svg/careers/section-3-imgs/care.svg';
	import headerglow from '../../images/svg/product-glows/zarf-header-glow.svg';
</script>

<section>
	<div>
		<img class="headerglow" src={headerglow} alt="" />
		<h1>OUR CORE VALUES</h1>
		<h1>What Makes Unicorns Sparkle</h1>
	</div>
	<div class="container">
		<div class="img-container">
			<ImgOrientation background={eclipse} img={bullseye} />
			<h2>We are <span>Focused</span></h2>
		</div>
		<div class="img-container">
			<ImgOrientation background={eclipse} img={bullseye} />
			<h2>We are <span>Mission Driven</span></h2>
		</div>
		<div class="img-container">
			<ImgOrientation background={eclipse} img={arrowCircle} />
			<h2>We are <span>Adaptable</span></h2>
		</div>
		<div class="img-container">
			<ImgOrientation background={eclipse} img={care} />
			<h2>We are <span>Caring</span></h2>
		</div>
		<div class="img-container">
			<ImgOrientation background={eclipse} img={bullseye} />
			<h2>We are <span>Humble</span></h2>
		</div>
	</div>
</section>

<style>
	.headerglow {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		z-index: -2;
	}

	section {
		gap: 3rem;
		position: relative;
	}
	.img-container {
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		gap: 2rem;
	}

	.container {
		display: flex;
		width: 100%;
		justify-content: space-evenly;
	}
</style>

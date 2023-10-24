<script>
	import headerglow from '../../images/svg/product-glows/zarf-header-glow.svg';
	import CardGlow from '../Home/CardGlow.svelte';
	import cardGlow from '../../images/svg/product-glows/zarf-card-glow.svg';
</script>

<section class="container">
	<div class="cardglow">
		<CardGlow glowLeft={cardGlow} glowRight={cardGlow} />
	</div>
	<img class="headerglow" src={headerglow} alt="" />
	<div class="header">
		<h1>CURRENT OPENINGS</h1>
		<h1>Find Your Next <span>Career</span></h1>
	</div>
</section>

<style>
	.container {
		position: relative;
	}

	.cardglow {
		position: absolute;
		top: -10rem;
		left: 0;
		width: 100%;
		height: 100%;
		z-index: -1;
	}

	.headerglow {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		z-index: -2;
	}

	.header {
		position: relative;
		z-index: 2;
		text-align: center;
	}
</style>

<script>
	import headerGlow from '../images/svg/product-glows/zarf-header-glow.svg';
</script>

<div class="h1-container">
	<img src={headerGlow} alt="header-glow" loading="lazy" class="glow" />
	<slot name="header" />
</div>

<style>
	.h1-container {
		position: relative;
		display: inline-block;
	}
	.glow {
		position: absolute;
		top: -15rem;
		left: -30rem;
		z-index: -1;
		width: 200%;
		height: auto;
	}
</style>

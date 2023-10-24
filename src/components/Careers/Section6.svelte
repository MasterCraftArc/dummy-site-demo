<script>
	import doug from '../../images/svg/doug.svg';
	import CardGlow from '../Home/CardGlow.svelte';
	import zarfGlow from '../../images/svg/product-glows/zarf-header-glow.svg';
</script>

<section style="position: relative;">
	<img src={doug} alt="" />
	<div class="card-glow">
		<img src={zarfGlow} alt="" class="glow" />
	</div>
	<div class="text-content">
		<h1>"Invest in people so they can work anywhere. Treat</h1>
		<h1>them in a way they won't want to work</h1>
		<h1>anywhere but here"</h1>
		<h1>- Andrew Greene</h1>
	</div>
</section>

<style>
	.card-glow {
		position: absolute;
		top: 15rem;
		left: 0;
		z-index: -1;
	}

	.text-content {
		position: relative;
		z-index: 1;
	}

	section {
		gap: 3rem;
	}
</style>

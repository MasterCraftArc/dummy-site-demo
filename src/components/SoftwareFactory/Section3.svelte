<script>
	import softwareFactoryBadges from '../../images/svg/software-factory/software-factory-badges.svg';
	import HeaderGlow from '../HeaderGlow.svelte';
</script>

<section>
	<div>
		<div class="foreground">
			<HeaderGlow>
				<div class="h1-container" slot="header">
					<h1>Defense Unicorns Is Trusted By the Most</h1>
					<h1><span>Critical Systems</span> in the World</h1>
				</div></HeaderGlow
			>
		</div>
	</div>

	<div class="img-holder">
		<img src={softwareFactoryBadges} alt="" loading="lazy" />
	</div>
</section>

<style>
	img {
		width: 100%;
	}
</style>

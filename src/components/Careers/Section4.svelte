<script>
	import img1Section1 from '../../images/svg/careers/unicorns/section1/img1.svg';
	import img2Section1 from '../../images/svg/careers/unicorns/section1/img2.svg';
	import img2Section2 from '../../images/svg/careers/unicorns/section2/img2.svg';
	import img1Section3 from '../../images/svg/careers/unicorns/section3/img1.svg';
	import { fade } from 'svelte/transition';
</script>

<section transition:fade={{ delay: 250, duration: 300 }}>
	<div class="img-container-1">
		<img src={img1Section1} alt="" />
		<img src={img2Section1} alt="" />
	</div>
	<div class="img-container-2">
		<img src={img1Section3} alt="" />
		<img src={img2Section2} alt="" />
	</div>
</section>

<style>
	img {
		width: 100%;
	}
	.img-container-1 {
		display: flex;
		gap: 1rem;
		width: 100%;
		justify-content: center;
		padding: 1rem 0;
	}
	.img-container-2 {
		display: flex;
		gap: 1rem;
		width: 100%;
		justify-content: center;
	}
</style>

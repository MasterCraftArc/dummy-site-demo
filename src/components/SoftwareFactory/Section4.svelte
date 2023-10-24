<script>
	import LeftRight from '../LeftRight.svelte';
	import api from '../../images/svg/software-factory/api.svg';
	import Button from '../Button.svelte';
	import HeaderGlow from '../HeaderGlow.svelte';
</script>

<section>
	<HeaderGlow>
		<h1 slot="header">Software Factory <span>Use Cases</span></h1>
	</HeaderGlow>
	<div class="container">
		<LeftRight>
			<div slot="left" class="left">
				<div class="img-holder">
					<img src={api} alt="api" loading="lazy" />
				</div>
			</div>
			<div slot="right" class="right">
				<p>
					A software factory solution designed specifically for national security systems. A common
					developer environment, designed to accelerate ATOs, and deploy mission capabilities to any
					environment.
				</p>
				<Button text="Contact Us" />
			</div>
		</LeftRight>
	</div>
</section>

<style>
	section {
		padding-top: 3rem;
		gap: 7rem;
	}

	.left,
	.right {
		width: 100%;
	}

	.right {
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		text-align: left;
		gap: 3rem;
	}

	img {
		width: 100%;
	}
	.img-holder {
		display: flex;
		flex-direction: column;
	}
</style>

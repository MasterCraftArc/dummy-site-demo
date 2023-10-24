<script>
	import LeftRight from '../../LeftRight.svelte';
	import ai from '../../../images/svg//ai-for-national-security/ai-for-national-security.svg';
	import Button from '../../../components/Button.svelte';
</script>

<section>
	<div>
		<div class="foreground">
			<div class="h1-container">
				<h1>AI For <span>National</span> Security</h1>
				<p>Coming Soon</p>
			</div>
		</div>
	</div>
	<LeftRight>
		<div slot="left">
			<img src={ai} alt="ai" loading="lazy" />
		</div>
		<div slot="right">
			<div class="right">
				<p>Chat-gpt like experience for Defense systems</p>
				<p>Your data, your environment, your mission</p>
				<Button text="Get Early Access" />
			</div>
		</div>
	</LeftRight>
</section>

<style>
	img {
		width: 300px;
	}

	.foreground {
		position: relative;
	}

	.h1-container {
		width: 100vw;
	}

	p {
		font-size: 25px;
		font-weight: 400;
		line-height: 30px;
		letter-spacing: 0em;
		text-align: center;
	}

	.right {
		display: flex;
		text-align: start;
		gap: 5rem;
		flex-direction: column;
	}

	section {
		padding-top: 5rem;
		gap: 5rem;
	}
</style>

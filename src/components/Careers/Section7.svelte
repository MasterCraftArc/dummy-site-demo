<script>
	import LeftRight from '../LeftRight.svelte';
	import bottomImage from '../../images/svg/careers/unicorns/bottom-image.svg';
	import Button from '../Button.svelte';
</script>

<section>
	<p>SKILL BRIDGE OPPORTUNITY</p>
	<h1>Same <span>Mission Different</span> Experience</h1>
	<LeftRight>
		<div slot="left">
			<div class="left">
				<p>
					The DOD SkillBridge program is an opportunity for service members to gain valuable
					civilian work experience through specific industry training, apprenticeships, or
					internships during the last 180 days of service. Defense Unicorns is honored to be an
					authorized SkillBridge provider with a history of providing service members with
					real-world job experience through this program.
				</p>
				<Button text="learn more" />
			</div>
		</div>
		<div slot="right">
			<img src={bottomImage} alt="" />
		</div>
	</LeftRight>
</section>

<style>
	.left {
		display: flex;
		justify-content: flex-start;
		align-items: flex-start;
		text-align: left;
		gap: 2rem;
		flex-direction: column;
	}
</style>

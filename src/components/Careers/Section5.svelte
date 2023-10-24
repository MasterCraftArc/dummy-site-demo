<script>
	import Cards from '../Projects/Cards.svelte';
	import Imgs from '../Projects/img-orientation/imgs.svelte';
	import eclipse from '../../images/svg/eclipse.svg';
	import familyOrientated from '../../images/svg/careers/card-imgs/family-oriented.svg';
	import fullyCovered from '../../images/svg/careers/card-imgs/fully-covered.svg';
	import graph from '../../images/svg/careers/card-imgs/graph.svg';
	import money from '../../images/svg/careers/card-imgs/money.svg';
	import scales from '../../images/svg/careers/card-imgs/scales.svg';
	import workFromHome from '../../images/svg/careers/card-imgs/work-from-anywhere.svg';
</script>

<section>
	<div class="header">
		<h3>OUR BENEFITS</h3>
		<h1>Life of a <span>Defense</span> Unicorns</h1>
	</div>
	<div class="cards">
		<Cards>
			<span slot="img1" class="eclipse"><Imgs background={eclipse} img={workFromHome} /></span>
			<span slot="title"><h3>Work From Anywhere</h3></span>
			<span slot="text"
				><p>
					We are fully remote, with Unicorns living all over the country. We empower Unicorns to
					work where they work best and we provide support for their remote office setup.
				</p></span
			>
		</Cards>
		<Cards>
			<span slot="img1" class="eclipse"><Imgs background={eclipse} img={familyOrientated} /></span>
			<span slot="title"><h3>Family Oriented Environment</h3></span>
			<span slot="text"
				><p>
					We support Unicorns making sure their work-life compliments their home-life. We offer 16
					weeks of paid parental leave plus 8 weeks of part-time leave.
				</p></span
			>
		</Cards>
		<Cards>
			<span slot="img1" class="eclipse"><Imgs background={eclipse} img={scales} /></span>
			<span slot="title"><h3>Great Work/Life Balance</h3></span>
			<span slot="text"
				><p>
					We offer all full-time Unicorns unlimited PTO (minimum 10 Days) plus all Federal Holidays,
					1 week for Thanksgiving, and two weeks for Christmas and New Years.
				</p></span
			>
		</Cards>
	</div>
	<div class="cards">
		<Cards>
			<span slot="img1" class="eclipse"><Imgs background={eclipse} img={fullyCovered} /></span>
			<span slot="title"><h3>Fully Covered Medical</h3></span>
			<span slot="text"
				><p>
					We care about the health of our Unicorns. We cover Medical, Dental, Vision for Unicorns
					and their families, including 100% of in-network covered services and 100% of premiums.
				</p></span
			>
		</Cards>
		<Cards>
			<span slot="img1" class="eclipse"><Imgs background={eclipse} img={money} /></span>
			<span slot="title"><h3>Wealth & Financial Resources</h3></span>
			<span slot="text"
				><p>
					We offer all full-time Unicorns company equity options, 401k retirement plan with $20k
					employer contribution, life and disability insurance, and access to financial advisors.
				</p></span
			>
		</Cards>
		<Cards>
			<span slot="img1" class="eclipse"><Imgs background={eclipse} img={graph} /></span>
			<span slot="title"><h3>Career Growth & Learning</h3></span>
			<span slot="text"
				><p>
					We want all Unicorns to continue to grow in their careers. We offer financial support for
					trainings, conferences, and professional subscriptions.
				</p></span
			>
		</Cards>
	</div>
</section>

<style>
	.header {
		display: flex;
		gap: 1rem;
		flex-direction: column;
		padding-bottom: 3rem;
	}

	.cards {
		display: flex;
		gap: 2rem;
		padding-bottom: 2rem;
	}
</style>

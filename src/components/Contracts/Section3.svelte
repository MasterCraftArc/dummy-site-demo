<script>
	import ContractCards from './ContractCards.svelte';
	import InternalButton from '../InternalButton.svelte';

	import SBIR from '../../images/svg/contract-imgs/sbir.svg';
	import MobileContractCards from '../Contracts/MobileContractCards.svelte';
	$: innerWidth = 0;
</script>

<svelte:window bind:innerWidth />
{#if innerWidth < 1200}
	<MobileContractCards>
		<h1 slot="header">Phase 3 <span>SBIR/STTR </span>Authority</h1>
		<div slot="left">
			<p>
				Defense Unicorns has a number of SBIR and STTR contracts that can be leveraged for new Phase
				3 contract vehicles.
			</p>
		</div>
		<div slot="right">
			<img src={SBIR} alt="" loading="lazy" class="SBIR" />
		</div>
		<InternalButton slot="button" text="Contact Us" link="ContactUs" />
	</MobileContractCards>
{:else}
	<ContractCards>
		<h1 slot="header">Phase 3 <span>SBIR/STTR </span>Authority</h1>
		<div slot="left">
			<p>
				Defense Unicorns has a number of SBIR and STTR contracts that can be leveraged for new Phase
				3 contract vehicles.
			</p>
		</div>
		<div slot="right">
			<img src={SBIR} alt="" loading="lazy" class="SBIR" />
		</div>
		<InternalButton slot="button" text="Contact Us" link="ContactUs" />
	</ContractCards>
{/if}

<style>
	p {
		color: #fff;
		text-align: center;
		font-size: 25px;
		font-style: normal;
		font-weight: 600;
		line-height: normal;
	}

	.SBIR {
		width: 100%;
	}
</style>

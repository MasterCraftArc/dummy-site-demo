<script>
	import defenseUnicornsLogo from '../../images/svg/doug.svg';
	import Mobile from './MobileNav.svelte';
	import Dropdown from './Dropdown.svelte';
	import InternalButton from '../InternalButton.svelte';
	import Announcement from '../Home/Announcement.svelte';

	let scrolled = false;

	let innerWidth = 0;
	$: isMobile = innerWidth < 1200;

	function handleScroll() {
		scrolled = window.scrollY > 0;
	}
</script>

<svelte:window bind:innerWidth on:scroll={handleScroll} />

{#if innerWidth && innerWidth < 1200}
	<Mobile />
{:else}
	<Announcement />
	<nav class:scrolled class="scrolled">
		<div class="flex-grid">
			<div class="logo">
				<a href="/">
					<img src={defenseUnicornsLogo} alt="logo" loading="lazy" />
				</a>
			</div>
			<div class="links">
				<Dropdown />
				<a class="link" href="/Projects">Open Source</a>
				<a class="link" href="/Contracts">Contracts</a>
				<a class="link" href="/CaseStudies">Case Studies</a>
				<a class="link" href="/UnicornAcademy">Unicorn Academy</a>
			</div>
			<div class="button">
				<InternalButton link="/ContactUs" text="Request Demo" />
			</div>
		</div>
	</nav>
{/if}

<style>
	.scrolled {
		position: sticky;
		top: 0;
		background-color: black;
		width: 100%;
		z-index: 1000;
		transition: all 0.3s ease;
	}
	.flex-grid {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0;
	}

	.logo {
		flex: 1;
		display: flex;
		justify-content: flex-start;
		align-items: center;
		padding-left: 3rem;
	}

	.links {
		display: flex;
		gap: 3rem;
	}

	.link {
		text-decoration: none;
		cursor: pointer;
		position: relative;
		display: flex;
		align-items: center;
		color: white;
		font-size: 20px;
		white-space: nowrap;
	}

	.link:hover {
		text-decoration: none;
		color: #ffd700;
	}

	.link::before {
		content: '';
		position: absolute;
		width: 100%;
		height: 3px;
		bottom: -4px;
		left: 0;
		background: linear-gradient(to right, #ffd700, #ffa500);
		visibility: hidden;
		transform: scaleX(0);
		transition: all 0.3s ease-in-out;
	}

	.link:hover::before {
		visibility: visible;
		transform: scaleX(1);
	}

	.logo img {
		width: 60px;
		height: 85px;
		transition: all 0.3s ease-in-out;
	}

	.logo:hover img {
		width: 65px;
		height: 90px;
	}

	.button {
		flex: 1;
		display: flex;
		justify-content: flex-end;
		align-items: center;
		padding-right: 3rem;
	}

	@media only screen and (max-width: 1200px) {
		.logo img {
			height: 3rem;
		}

		.flex-grid {
			padding: 0 1rem;
		}
	}
</style>

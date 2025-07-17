<script lang="ts">
	import { slide } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	import backgroundImage from '$lib/assets/background.png';
	import logo from '$lib/assets/logo.svg';

	let innerWidth = 0;

	const navItems = [
		{
			name: 'Home',
			href: 'home'
		},
		{
			name: 'Über Mich',
			href: 'about'
		},
		{
			name: 'Leistungen',
			href: 'services'
		},
		{
			name: 'Kontakt',
			href: 'contact'
		}
	];

	let active = navItems[0].name;

	$: responsiveMenu = false;

	function toggleResponsiveMenu() {
		responsiveMenu = !responsiveMenu;
	}
</script>

<svelte:window bind:innerWidth />

<div class="grey-box">
	<img src={backgroundImage} alt="background" class="bg-img" />
</div>
<div class="header">
	<a href="home">
		<img src={logo} alt="logo" class="logo" />
	</a>
	{#if innerWidth > 850}
		<div class="navbar">
			{#each navItems as item}
				<a
					href={item.href}
					class="nav"
					class:active={item.name === active}
					on:click={() => (active = item.name)}>{item.name}</a
				>
			{/each}
		</div>
	{:else}
		<button class="menu" on:click={toggleResponsiveMenu}>
			<div class="line line-upper" class:line-upper-cross={responsiveMenu} />
			<div class="line line-lower" class:line-lower-cross={responsiveMenu} />
		</button>
		{#if responsiveMenu}
			<div
				class="mobile-menu-container"
				transition:slide={{ duration: 400, easing: quintOut, axis: 'y' }}
			>
				{#each navItems as item}
					<a
						href={item.href}
						class="nav"
						class:active={active === item.name}
						on:click={() => {
							responsiveMenu = false;
							active = item.name;
						}}>{item.name}</a
					>
				{/each}
			</div>
		{/if}
	{/if}
</div>

<div on:click={() => (responsiveMenu = false)} aria-hidden="true">
	<slot />
</div>

<div class="footer">
	<h4 class="title">Hebamme Tabea Kleine, 24214 Gettorf</h4>
</div>

<style>
	.grey-box {
		position: absolute;
		background-color: #ece5e4;
		left: 0;
		top: 0;
		width: calc(300px + 10%);
		height: 840px;
		min-height: 100%;
		z-index: -1;
		overflow: hidden;
	}

	.bg-img {
		position: absolute;
		left: 50%;
		top: 50%;
		transform: translate(-50%, -50%);
		width: 100%;
		min-height: 100%;
	}

	.grey-box {
		width: 30vw;
		height: 50vw;
		min-height: 0;
	}

	.grey-box:after {
		content: '';
		position: absolute;
		bottom: 0;
		left: 0;
		right: 0;
		background: linear-gradient(to bottom, rgba(255, 255, 255, 0) 20%, rgba(255, 255, 255, 1) 100%);
		height: 40%;
	}

	.header {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		height: 120px;
		align-items: center;
		padding: 0 60px 0 30px;
	}

	.navbar {
		display: flex;
		flex-direction: row;
		gap: 60px;
	}

	.logo {
		height: 55px;
	}

	a {
		text-decoration: none;
		color: var(--color-grey-100);
		font-size: 1.5rem;
	}

	.nav {
		padding: 0.4rem 1rem;
		position: relative;
		font-size: 20px;
		color: var(--color-grey-50);
	}

	.nav::before,
	.nav::after {
		content: '';
		height: 14px;
		width: 14px;
		position: absolute;
		transition: all 0.35s ease;
		opacity: 0;
	}

	.nav::before {
		content: '';
		right: 0;
		top: 0;
		border-top: 2px solid var(--color-grey-75);
		border-right: 2px solid var(--color-grey-50);
		transform: translate(-100%, 50%);
	}

	.nav:after {
		content: '';
		left: 0;
		bottom: 0;
		border-bottom: 2px solid var(--color-grey-75);
		border-left: 2px solid var(--color-grey-50);
		transform: translate(100%, -50%);
	}

	.nav:hover:before,
	.nav:hover:after {
		transform: translate(0, 0);
		opacity: 1;
	}

	.nav:hover {
		color: black;
	}

	.footer {
		margin-top: 80px;
		height: 100px;
		background-color: var(--color-grey-100);
		display: grid;
		align-items: center;
	}

	.title {
		color: white;
		letter-spacing: 0.1rem;
		text-align: center;
	}

	.menu {
		position: relative;
		width: 40px;
		height: 38px;
		cursor: pointer;
		z-index: 4;
		padding: 0;
		-webkit-tap-highlight-color: transparent;
	}

	.menu:focus-visible {
		outline: none;
	}

	.line {
		height: 2px;
		width: 40px;
		border-radius: 5px;
		background-color: var(--color-grey-100);
		position: absolute;
	}

	.line-upper {
		top: 10px;
		transition: all 0.2s;
	}

	.line-lower {
		bottom: 10px;
		transition: all 0.2s;
	}

	.line-upper-cross {
		top: calc(50% - 1px);
		transform: rotate(45deg);
	}

	.line-lower-cross {
		bottom: calc(50% - 1px);
		transform: rotate(-45deg);
	}

	.mobile-menu-container {
		display: grid;
		grid-template-columns: max-content;
		justify-content: center;
		position: fixed;
		right: 0;
		left: 0;
		top: 0;
		padding-top: 80px;
		padding-bottom: 38px;
		text-align: center;
		background-color: white;
		box-shadow: 0 0 20px 10px rgba(0, 0, 0, 0.1);
		row-gap: 10px;
		z-index: 3;
	}

	.active {
		color: black;
	}

	@media only screen and (max-width: 1000px) {
		.footer {
			margin-top: 0;
		}
		.navbar {
			gap: 20px;
		}
	}

	@media only screen and (max-width: 850px) {
		.grey-box {
			display: none;
		}

		.header {
			grid-template-columns: max-content auto max-content;
		}
	}

	@media only screen and (max-width: 600px) {
		.logo {
			display: none;
		}

		.mobile-menu-container {
			padding-top: 100px;
			row-gap: 20px;
		}
	}
</style>

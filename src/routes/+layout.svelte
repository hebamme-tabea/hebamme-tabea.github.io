<script lang="ts">
	import { slide } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';

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
			name: 'Kontakt',
			href: 'contact'
		}
	];

	$: responsiveMenu = false;

	function toggleResponsiveMenu() {
		responsiveMenu = !responsiveMenu;
	}
</script>

<svelte:window bind:innerWidth />

<div class="header">
	<a href="home">
		<img src="images/logo.svg" alt="logo" class="logo" />
	</a>
	<div />
	{#if innerWidth > 850}
		{#each navItems as item}
			<a href={item.href} class="nav">{item.name}</a>
		{/each}
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
					<a href={item.href} class="nav" on:click={() => (responsiveMenu = false)}>{item.name}</a>
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
	.header {
		display: grid;
		height: 120px;
		grid-template-columns: max-content auto repeat(3, max-content);
		align-items: center;
		gap: 60px;
		padding: 0 60px 0 30px;
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
		padding-bottom: 48px;
		text-align: center;
		background-color: white;
		box-shadow: 0 0 20px 10px rgba(0, 0, 0, 0.1);
		row-gap: 10px;
		z-index: 3;
	}

	@media only screen and (max-width: 1000px) {
		.footer {
			margin-top: 0;
		}
	}

	@media only screen and (max-width: 850px) {
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

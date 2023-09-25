<script lang="ts">
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

	let responsiveMenu = false;

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
	{#if innerWidth >= 850}
		{#each navItems as item}
			<a href={item.href} class="nav">{item.name}</a>
		{/each}
	{:else}
		<button class="menu" on:click={toggleResponsiveMenu}>
			<div class="line line-upper" class:line-upper-cross={responsiveMenu} />
			<div class="line line-lower" class:line-lower-cross={responsiveMenu} />
		</button>
	{/if}
</div>

<div>
	<slot />
</div>

<div class="footer">
	<div class="title">Hebamme Tabea Kleine, 23730 Neustadt in Holstein</div>
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
		color: #444444;
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
		border-top: 2px solid #666666;
		border-right: 2px solid #aaaaaa;
		transform: translate(-100%, 50%);
	}

	.nav:after {
		content: '';
		left: 0;
		bottom: 0;
		border-bottom: 2px solid #666666;
		border-left: 2px solid #aaaaaa;
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
		background-color: #444444;
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
	}

	.line {
		height: 2px;
		width: 40px;
		border-radius: 5px;
		background-color: #444444;
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

	@media only screen and (max-width: 500px) {
		.logo {
			display: none;
		}
	}
</style>

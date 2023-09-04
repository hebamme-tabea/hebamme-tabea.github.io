<div class="header">
	<a href="home">
		<img src="images/logo.svg" alt="logo" class="logo" />
	</a>
	<div />
	<a href="home" class="nav">Home</a>
	<a href="about" class="nav">Über Mich</a>
	<a href="contact" class="nav">Kontakt</a>
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
</style>

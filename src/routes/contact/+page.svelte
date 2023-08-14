<div class="grey-box">
	<img src="images/background.png" alt="background" class="bg-img" />
</div>

<div class="grid">
	<div />
	<div class="text-section">
		<div class="name">TABEA KLEINE</div>
		<div class="profession">Hebamme</div>
		<div class="text">
			<a href="mailto:hebamme.tabea@gmail.com">hebamme.tabea@gmail.com</a><br />
			04561 5288391
		</div>
	</div>
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

	.grid {
		display: grid;
		grid-template-columns: 400px 1fr;
		margin: 0 10%;
		gap: 50px;
	}

	.babyfeet-img {
		width: 100%;
	}

	.text-section {
		width: 100%;
		padding-top: 40px;
		color: #444444;
	}

	.name {
		font-size: 2rem;
		letter-spacing: 0.3rem;
	}

	.profession {
		font-family: Brittany Signature;
		font-size: 2.3rem;
		padding-top: 20px;
	}

	.text {
		font-size: 1.4rem;
		margin: 20px 0 0 150px;
		font-style: italic;
		line-height: 1.8;
	}

	a {
		text-decoration: none;
		color: inherit;
	}
</style>

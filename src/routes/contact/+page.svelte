<div class="grey-box">
	<img src="images/background.png" alt="background" class="bg-img" />
</div>

<div class="grid">
	<div />
	<div class="text-section">
		<h1 class="name">TABEA KLEINE</h1>
		<h2 class="profession">Hebamme</h2>
		<div class="text">
			<a href="mailto:hebamme.tabea@gmail.com">hebamme.tabea@gmail.com</a><br />
			+49 152 02740874
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

	.text-section {
		width: 100%;
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

	@media only screen and (max-width: 1000px) {
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
			background: linear-gradient(
				to bottom,
				rgba(255, 255, 255, 0) 20%,
				rgba(255, 255, 255, 1) 100%
			);
			height: 40%;
		}

		.grid {
			grid-template-columns: 30vw 1fr;
		}

		.text {
			margin-bottom: 80px;
		}
	}

	@media only screen and (max-width: 850px) {
		.grey-box {
			display: none;
		}

		.grid {
			grid-template-columns: 1fr;
		}

		.text-section {
			padding-top: 0;
		}
	}

	@media only screen and (max-width: 600px) {
		.text {
			margin-left: 0;
			margin-top: 60px;
		}
	}
</style>

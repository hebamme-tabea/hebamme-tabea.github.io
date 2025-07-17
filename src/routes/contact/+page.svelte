<script>
	import Button from '$lib/general/Button.svelte';
</script>

<div class="grid">
	<div />
	<div class="text-section">
		<h1 class="name">TABEA KLEINE</h1>
		<h2 class="profession">Hebamme</h2>
		<div class="text">
			<a href="mailto:hebamme.tabea@gmail.com">hebamme.tabea@gmail.com</a><br />
			+49 152 02740874
		</div>
		<div class="button-wrapper">
			<Button href="https://kleine.hebamio.de/anmeldung" target="_blank">Link zur Anmeldung</Button>
			<div class="note">
				(du wirst zu <a href="https://www.hebamio.de/" target="_blank">Hebamio</a> weitergeleitet)
			</div>
		</div>
	</div>
</div>

<style>
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

	.button-wrapper {
		margin: 60px 0 0 150px;
	}

	.note {
		font-style: normal;
		font-size: 1.3rem;
		margin-bottom: 40px;
		margin-top: 10px;
	}

	.note > a {
		text-decoration: underline;
	}

	@media only screen and (max-width: 1000px) {
		.grid {
			grid-template-columns: 30vw 1fr;
		}

		.text {
			margin-bottom: 80px;
		}
	}

	@media only screen and (max-width: 850px) {
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
		.button-wrapper {
			margin: 60px 0 0 0;
		}
	}
</style>

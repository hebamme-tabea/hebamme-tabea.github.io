<script lang="ts">
	import Quote from '$lib/general/Quote.svelte';
	import { MetaTags } from 'svelte-meta-tags';

	const quoteText =
		'In dem Moment, in dem ein Kind geboren wird, wird auch eine Mutter geboren. Die Frau hat vorher schon existiert, jedoch nicht als Mutter. Das Mutter-Sein ist etwas völlig Neues.';
	const quoteAuthor = '- Bhagwan Shree Rajneesh';
</script>

<MetaTags
	title="Hebamme Tabea Kleine"
	description="Kompetente Schwangerenvorsorge und Wochenbettbetreuung in Neustadt in Holstein mit eigener Erfahrung mit extremer Schwangerschaftsübelkeit."
	canonical="https://hebamme-tabea.github.io/home"
/>
<div class="grey-box">
	<img src="images/background.png" alt="background" class="bg-img" />
</div>
<div class="grid">
	<img src="images/profilbild.jpg" alt="profile" class="profile-img" />
	<div class="text-section">
		<h1 class="name">TABEA KLEINE</h1>
		<h2 class="profession">Hebamme</h2>
		<Quote text={quoteText} author={quoteAuthor} />
		<div class="skills">Schwangerenvorsorge &#183; Wochenbettbetreuung</div>
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

	.profile-img {
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
		white-space: no-wrap;
	}

	.profession {
		font-family: Brittany Signature;
		font-size: 2.3rem;
		padding-top: 20px;
	}

	.skills {
		width: 800px;
		font-style: italic;
		text-align: center;
		font-size: 1.1rem;
	}

	@media only screen and (max-width: 1300px) {
		.grid {
			grid-template-columns: 100%;
			margin: 0 20%;
		}

		.grey-box {
			width: 50%;
			height: calc(300px + 60vw);
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

		.text-section {
			padding-top: 0;
		}

		.profession {
			margin-top: 0;
		}

		.text-section :global(.quote) {
			margin-left: -10vw;
			width: 80vw;
		}

		.skills {
			width: 100%;
		}
	}

	@media only screen and (max-width: 1000px) {
		.text-section :global(.quote) {
			width: 90vw;
		}
	}

	@media only screen and (max-width: 800px) {
		.text-section :global(.quote) {
			margin-left: -20vw;
			width: 110vw;
		}
	}

	@media only screen and (max-width: 700px) {
		.text-section :global(.quote-body) {
			top: 20%;
		}
	}

	@media only screen and (max-width: 580px) {
		.text-section :global(.quote-body) {
			font-size: 1rem;
			top: 25%;
		}

		.text-section :global(.quote-author) {
			font-size: 1rem;
		}
	}

	@media only screen and (max-width: 500px) {
		.text-section :global(.quote-body) {
			font-size: 0.8rem;
			top: 30%;
		}

		.text-section :global(.quote-author) {
			font-size: 0.8rem;
		}

		.grid {
			margin: 0 10%;
		}
	}

	@media only screen and (max-width: 450px) {
		.text-section :global(.quote-body) {
			top: 20%;
		}
	}
</style>

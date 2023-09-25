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
	</div>
	<div class="quote">
		<Quote text={quoteText} author={quoteAuthor} />
	</div>
	<div class="skills">Schwangerenvorsorge &#183; Wochenbettbetreuung</div>
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
		grid-template-areas:
			'image title'
			'image quote'
			'image skills';
		grid-template-columns: 400px 1fr;
		margin: 0 10%;
		column-gap: 50px;
	}

	.profile-img {
		width: 100%;
		grid-area: image;
		z-index: 2;
	}

	.text-section {
		width: 100%;
		padding-top: 40px;
		color: #444444;
		grid-area: title;
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

	.quote {
		grid-area: quote;
	}

	.skills {
		width: 800px;
		font-style: italic;
		text-align: center;
		font-size: 1.1rem;
		grid-area: skills;
	}

	@media only screen and (max-width: 1300px) {
		.skills {
			width: 100%;
		}

		.quote :global(.quote) {
			width: 600px;
		}

		.quote :global(.quote-body) {
			font-size: 1rem;
			width: 50%;
			left: 26%;
		}

		.quote :global(.quote-author) {
			font-size: 1rem;
		}
	}

	@media only screen and (max-width: 1100px) {
		.quote :global(.quote) {
			margin-left: -80px;
		}

		.skills {
			margin-left: -80px;
		}
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
			grid-template-areas:
				'image title'
				'image skills'
				'quote quote';
			grid-template-columns: 1fr 1fr;
			grid-template-rows: 300px auto;
			column-gap: 100px;
		}

		.text-section {
			padding-top: 100px;
		}

		.skills {
			margin-left: 0;
			text-align: left;
		}

		.quote :global(.quote) {
			width: 100%;
			margin-left: 0;
		}

		.quote :global(.quote-body) {
			font-size: 2.2vw;
			width: 50%;
			left: 26%;
		}

		.quote :global(.quote-author) {
			font-size: 2.2vw;
		}
	}

	@media only screen and (max-width: 850px) {
		.grey-box {
			display: none;
		}
		.grid {
			grid-template-areas:
				'title'
				'image'
				'skills'
				'quote';
			grid-template-columns: 1fr;
			grid-template-rows: repeat(3, max-content);
			column-gap: 100px;
			margin: 0 20%;
		}

		.skills {
			text-align: center;
			margin: 20px 0;
		}

		.text-section {
			padding-top: 0;
		}

		.profession {
			margin-top: 0;
		}

		.quote :global(.quote) {
			width: 140%;
			margin-left: 0;
		}
	}

	@media only screen and (max-width: 500px) {
		.grid {
			margin: 0 5%;
		}

		.text-section {
			padding: 0 60px;
		}

		.quote :global(.quote) {
			width: 120%;
			margin-left: 0;
		}

		.quote :global(.quote-body) {
			font-size: 2.8vw;
		}

		.quote :global(.quote-author) {
			font-size: 2.8vw;
		}
	}

	@media only screen and (max-width: 400px) {
		.text-section {
			padding: 0 20px;
		}
	}
</style>

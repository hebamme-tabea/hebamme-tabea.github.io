<script lang="ts">
	import Quote from '$lib/general/Quote.svelte';
	import { MetaTags } from 'svelte-meta-tags';
	import profilePicture from '$lib/assets/profilbild.jpg';

	const quoteText =
		'In dem Moment, in dem ein Kind geboren wird, wird auch eine Mutter geboren. Die Frau hat vorher schon existiert, jedoch nicht als Mutter. Das Mutter-Sein ist etwas völlig Neues.';
	const quoteAuthor = '- Bhagwan Shree Rajneesh';
</script>

<MetaTags
	title="Hebamme Tabea Kleine in Gettorf, Kiel und Eckernförde"
	description="Kompetente Schwangerenvorsorge und Wochenbettbetreuung mit Schwerpunkt auf das Wohlergehen der Mutter und persönlicher Erfahrung bezüglich intensiver Schwangerschaftsübelkeit."
	canonical="https://kleine-hebamme.de/home"
	robots="index,follow"
/>
<div class="grid">
	<img src={profilePicture} alt="profile" class="profile-img" />
	<div class="text-section">
		<h1 class="name">TABEA KLEINE</h1>
		<h2 class="profession">Hebamme</h2>
	</div>
	<div class="quote">
		<Quote text={quoteText} author={quoteAuthor} />
	</div>
	<h3 class="skills">Schwangerenvorsorge &#183; Wochenbettbetreuung</h3>
</div>

<style>
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
		border-radius: var(--border-radius);
	}

	.text-section {
		width: 100%;
		color: var(--color-grey-100);
		grid-area: title;
	}

	.name {
		font-size: 2rem;
		letter-spacing: 0.3rem;
		white-space: no-wrap;
	}

	.profession {
		font-family: var(--font-brittany);
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
			font-size: 1.3rem;
			width: 50%;
			left: 26%;
		}

		.quote :global(.quote-author) {
			font-size: 1.3rem;
		}
	}

	@media only screen and (max-width: 850px) {
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

		.quote :global(.quote-body) {
			font-size: 1.1rem;
		}

		.quote :global(.quote-author) {
			font-size: 1.1rem;
		}
	}

	@media only screen and (max-width: 700px) {
		.quote :global(.quote) {
			width: 170%;
		}
	}

	@media only screen and (max-width: 600px) {
		.profile-img {
			border-radius: 0;
		}

		.grid {
			margin: 0;
		}

		.text-section {
			padding: 0;
			margin: 0 40px;
		}

		.quote {
			margin: 0 40px;
		}

		.quote :global(.quote) {
			width: 160%;
			margin-left: 0;
		}

		.quote :global(.quote-body) {
			font-size: 1rem;
		}

		.quote :global(.quote-author) {
			font-size: 1rem;
		}
	}

	@media only screen and (max-width: 400px) {
		.quote {
			margin: 0 15px 0 10px;
		}
	}
</style>

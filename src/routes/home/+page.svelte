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
</style>

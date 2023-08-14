<script lang="ts">
	import Quote from '$lib/general/Quote.svelte';

	const quoteText =
		'In dem Moment, in dem ein Kind geboren wird, wird auch eine Mutter geboren. Die Frau hat vorher schon existiert, jedoch nicht als Mutter. Das Mutter-Sein ist etwas völlig Neues.';
	const quoteAuthor = '- Bhagwan Shree Rajneesh';
</script>

<div class="grey-box">
	<img src="images/background.png" alt="background" class="bg-img" />
</div>
<div class="grid">
	<img src="images/profilbild.jpeg" alt="profile" class="profile-img" />
	<div class="text-section">
		<div class="name">TABEA KLEINE</div>
		<div class="profession">Hebamme</div>
		<img src="logo.svg" alt="logo" class="logo" />
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

	.logo {
		width: 400px;
		margin-top: 50px;
		margin-left: 200px;
		display: none;
	}

	.skills {
		width: 800px;
		font-style: italic;
		text-align: center;
		font-size: 1.1rem;
	}
</style>

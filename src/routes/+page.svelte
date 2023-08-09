<script>
	//Das Mutter-Sein ist etwas völlig Neues.
</script>

<div class="grey-box" />
<div class="grid">
	<img src="profilbild.jpeg" alt="profile" class="profile-img" />
	<div class="text-section">
		<div class="name">TABEA KLEINE</div>
		<div class="profession">Hebamme</div>
		<img src="logo.svg" alt="logo" class="logo" />
		<div class="quote">
			<img src="quote-bg.png" alt="quote" class="quote-background" />
			<div class="quote-body">
				In dem Moment, in dem ein Kind geboren wird, wird auch eine Mutter geboren. Die Frau hat
				vorher schon existiert, jedoch nicht als Mutter. Die Mutter ist genauso neu wie das Kind.
			</div>
			<div class="quote-author">- Bhagwan Shree Rajneesh</div>
		</div>
		<div class="skills">Schwangerenvorsorge &#183; Wochenbettbetreuung</div>
	</div>
</div>

<style>
	.grey-box {
		position: absolute;
		background-color: #eeeeee;
		left: 0;
		top: 0;
		width: calc(300px + 10%);
		height: 840px;
		min-height: 100%;
		z-index: -1;
		background-image: url(background.png);
		background-repeat: no-repeat;
		background-size: cover;
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

	.quote {
		margin: 20px 0;
		position: relative;
		width: 800px;
	}

	.quote-background {
		width: 100%;
	}

	.quote-body {
		position: absolute;
		font-size: 1.3rem;
		top: 28%;
		text-align: center;
		width: 47%;
		left: 28%;
	}

	.quote-author {
		position: absolute;
		bottom: 20%;
		right: 25%;
	}

	.skills {
		font-style: italic;
		text-align: center;
		font-size: 1.1rem;
	}
</style>

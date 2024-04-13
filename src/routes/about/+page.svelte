<div class="grey-box">
	<img src="images/background.png" alt="background" class="bg-img" />
</div>

<div class="grid">
	<img src="images/babyfeet.jpg" alt="babyfoot" class="babyfeet-img" />
	<div class="title">
		<h1 class="name">TABEA KLEINE</h1>
		<h2 class="profession">Hebamme</h2>
	</div>
	<div class="text">
		Ich bin Tabea und 1993 in Heilbronn, Baden Württemberg geboren. Aufgewachsen bin ich in der
		Gegend von Heidelberg und 2015 für die Hebammenausbildung nach Hamburg gezogen. Dabei hat mich
		besonders die Veränderung des weiblichen Körpers während einer Schwangerschaft fasziniert und
		die enorme Leistung die Frauen in der Schwangerschaft, unter der Geburt und im Wochenbett
		erbringen. Nach der Ausbildung bin ich selbst schwanger geworden und litt dabei die kompletten 9
		Monate an extremer Schwangerschaftsübelkeit. Dadurch ist mein Respekt vor Frauen in der
		Schwangerschaft noch einmal gestiegen. In meiner Arbeit möchte ich daher meine Aufmerksamkeit
		nicht nur auf das Wohlergehen des Neugeborenen, sondern auch besonders auf das Wohlergehen der
		Mutter richten, denn eine Entbindung gehört zu den bedeutendsten Initationen im Leben einer
		Frau. Denn wenn ein Kind geboren wird, kommt auch eine Mutter zur Welt. Nach einem Jahr
		Elternzeit meines zweiten Kindes, steige ich wieder in meinen Beruf ein.
	</div>
</div>

<style>
	.grey-box {
		position: absolute;
		background-color: var(--color-grey-25);
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
			'image text';
		grid-template-columns: 400px 1fr;
		margin: 0 10%;
		column-gap: 50px;
		color: var(--color-grey-100);
	}

	.babyfeet-img {
		width: 100%;
		grid-area: image;
		border-radius: var(--border-radius);
	}

	.title {
		grid-area: title;
	}

	.name {
		font-size: 2rem;
		letter-spacing: 0.3rem;
	}

	.profession {
		font-family: var(--font-brittany);
		font-size: 2.3rem;
		padding-top: 20px;
	}

	.text {
		grid-area: text;
		font-size: 1.2rem;
		margin: 0 0 0 70px;
	}

	@media only screen and (max-width: 1300px) {
		.text {
			margin: 30px 0 0 0;
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
			grid-template-columns: 1fr 1fr;

			column-gap: 100px;
			grid-template-areas:
				'image title'
				'text text';
		}

		.title {
			padding-top: 100px;
		}

		.text {
			margin-bottom: 100px;
			margin-top: 60px;
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
				'text';
			grid-template-columns: 1fr;
			grid-template-rows: repeat(3, max-content);
			column-gap: 100px;
			margin: 0 20%;
		}

		.title {
			padding-top: 0;
		}

		.profession {
			margin-top: 0;
		}
	}

	@media only screen and (max-width: 600px) {
		.grid {
			margin: 0;
		}

		.title {
			margin: 0 40px;
		}

		.text {
			margin-left: 40px;
			margin-right: 40px;
		}
	}
</style>

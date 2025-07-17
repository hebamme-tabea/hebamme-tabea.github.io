<script lang="ts">
	import babyfeetImage from '$lib/assets/babyfeet.jpg';
	import Button from '$lib/general/Button.svelte';
</script>

<div class="grid">
	<img src={babyfeetImage} alt="babyfoot" class="babyfeet-img" />
	<div class="title">
		<h1 class="name">TABEA KLEINE</h1>
		<h2 class="profession">Hebamme</h2>
	</div>
	<div class="text">
		<p>
			Als Hebamme begleite ich individuell und kompetent durch Schwangerschaft, Wochenbett und die
			erste Zeit mit Baby.<br />
			Zu meinen Angeboten zählen:
		</p>
		<ul>
			<li>
				<span>
					Schwangerenvorsorge: Ich führe Vorsorgeuntersuchungen gemäß den Mutterschaftsrichtlinien
					durch – auf Wunsch in Zusammenarbeit mit der Ärztin/deinem Arzt.</span
				>
			</li>
			<li>
				<span>
					Hilfe bei Schwangerschaftsbeschwerden: Bei typischen Beschwerden wie Übelkeit,
					Rückenschmerzen oder Wassereinlagerungen unterstütze ich mit fachgerechten, auch
					natürlichen Maßnahmen und Kinesiotaping.</span
				>
			</li>
			<li>
				<span>
					Telefon- und Videoberatung: Viele Fragen lassen sich unkompliziert telefonisch oder per
					Videogespräch besprechen – zum Beispiel, wenn schnelle Hilfe oder ein Rat zwischendurch
					benötigt werden.</span
				>
			</li>
			<li>
				<span>
					Kinesiotaping: Zur Linderung von Schmerzen, Verspannungen und zur Unterstützung bei
					verschiedenen Schwangerschaftsbeschwerden biete ich professionelles Kinesiotaping an.</span
				>
			</li>
			<li>
				<span>
					Wochenbettbetreuung: Nach der Geburt bin ich für dich und dein Baby da. Ich unterstütze
					beim Stillen, achte auf die Rückbildung und das Gedeihen des Babys und stehe bei allen
					Themen rund um die erste Zeit zu Hause an deiner Seite.</span
				>
			</li>
			<li>
				<span>
					Still- und Ernährungsberatung/ Beikost: Ob Fragen zum Stillen, zur Flaschenernährung,
					Ernährungsschwierigkeiten oder Beikost – ich berate und unterstütze individuell, auch
					längerfristig während der gesamten Stillzeit.</span
				>
			</li>
		</ul>
		<p>
			Mein Ziel ist es, dich mit Einfühlungsvermögen und Fachwissen zu begleiten – Rund um
			Schwangerschaft, Geburt, Babyzeit und das reinwachsen in die Mutterschaft.
		</p>
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

	li {
		padding: 15px;
	}

	li > span {
		display: inline-block;
		vertical-align: middle;
	}

	.button-wrapper {
		margin-top: 40px;
	}

	.note {
		font-style: normal;
		font-size: 1.3rem;
		margin-top: 10px;
	}

	a {
		text-decoration: underline;
		color: inherit;
	}

	@media only screen and (max-width: 1300px) {
		.text {
			margin: 30px 0 0 0;
		}
	}

	@media only screen and (max-width: 1000px) {
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

		.babyfeet-img {
			border-radius: 0;
		}
	}
</style>

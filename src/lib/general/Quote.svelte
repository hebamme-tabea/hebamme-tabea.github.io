<script lang="ts">
	export let text: string | undefined = undefined;
	export let author: string | undefined = undefined;
</script>

<div class="quote">
	<img src="images/quote-bg.png" alt="quote" class="quote-background" />
	<div class="quote-body">{text}</div>
	<div class="quote-author">{author}</div>
</div>

<style>
	.quote {
		margin: 20px 0;
		position: relative;
		width: 800px;
		left: 50%;
		transform: translateX(-50%);
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
</style>

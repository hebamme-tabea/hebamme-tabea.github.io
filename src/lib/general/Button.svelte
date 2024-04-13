<script lang="ts">
	export let href: string;
	export let target = '_self';
</script>

<a {href} {target}>
	<button>
		<slot />
	</button>
</a>

<style>
	button {
		padding: 10px 20px;
		border-radius: 5px;
		color: white;
		font-family: var(--font-garamond);
		font-size: 1.2rem;
		cursor: pointer;
		background-color: var(--color-grey-100);
		transition: background-color 0.3s;
	}

	a :hover {
		background-color: var(--color-grey-75);
		transition: background-color 0.3s;
	}
</style>

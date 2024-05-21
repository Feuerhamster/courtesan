<script lang="ts">
	export let href: string;
	import Portal from "svelte-portal";
</script>

<Portal target="body">
	<a {href}>
		<slot />
	</a>
</Portal>

<style lang="scss">
	@import "../../scss/defaults";

	a {
		text-decoration: none;
		background: $color-sec;
		color: $color-txt;

		position: absolute;
		right: 18px;
		bottom: 86px;

		display: flex;
		align-items: center;
		justify-content: center;

		height: 3em;
		width: 3em;

		border-radius: 32px;
		box-shadow: $shadow;

		:global(span) {
			font-size: 2em;
		}
	}
</style>

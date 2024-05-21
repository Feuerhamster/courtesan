<script lang="ts">
	export let color: string = "";
</script>

<button on:click {...$$props} class={color}>
	<slot />
</button>

<style lang="scss">
	@import "../../scss/defaults";
	@import "../../scss/mixins";

	button {
		display: flex;
		justify-content: center;
		background: none;
		outline: none;
		border: 2px solid $color-bl;
		background-color: $color-bl-bg;
		color: $color-bl;
		padding: 8px 6px;
		border-radius: 6px;
		flex: 1;
		transition: 0.1s border;
		font-size: 1em;
		width: 100%;

		&.pink {
			border: 2px solid $color-pr;
			color: $color-pr;
			background-color: $color-pr-bg;
		}

		&.red {
			border: 2px solid $color-rd;
			color: $color-rd;
			background-color: $color-rd-bg;
		}

		&.orange {
			border: 2px solid $color-or;
			color: $color-or;
			background-color: $color-or-bg;
		}
	}
</style>

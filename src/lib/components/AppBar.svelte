<script lang="ts">
	import { searchString } from "$lib/stores";

	export let placeholder = "";
	export let icon = "";
</script>

<header>
	<span class="material-symbols-rounded">{icon}</span>
	<input {placeholder} bind:value={$searchString} />
</header>

<style lang="scss">
	@import "../../scss/defaults";

	header {
		display: flex;
		gap: 8px;
		padding: 8px 12px;
		background: $color-bg-2;
		box-shadow: $shadow;
		border-radius: 32px;
		align-items: stretch;
		font-size: 1.05em;
		position: sticky;
		top: 0;

		span.material-symbols-rounded {
			font-size: 1.8rem;
			padding: 2px;
			color: $color-txt;
			flex-shrink: 0;
		}

		input {
			background: none;
			border: none;
			outline: none;
			width: 100%;
			color: $color-txt;

			&::placeholder {
				color: $color-txt-2;
			}
		}
	}
</style>

<script context="module">
	let counter = 0;
</script>

<script lang="ts">
	export let label: string = "";
	let id = "input_" + counter++;

	export let value = "";
	export let type = "";
</script>

<div class="input-wrapper">
	{#if type === "number"}
		<input {id} bind:value type="number" {...$$props} placeholder="&nbsp;" />
	{:else}
		<input {id} bind:value {...$$props} placeholder="&nbsp;" />
	{/if}

	{#if label}
		<label for={id}>
			{label}
		</label>
	{/if}
</div>

<style lang="scss">
	@import "../../../scss/defaults";
	@import "../../../scss/mixins";

	.input-wrapper {
		position: relative;
		display: flex;

		input {
			@include input-field;

			&:focus {
				border: 2px solid $color-pr;

				& + label {
					@include input-label-focused;
					color: $color-pr;
				}
			}

			&:not(:placeholder-shown) + label {
				@include input-label-focused;
			}
		}

		label {
			@include input-label;
		}
	}
</style>

<script context="module">
	let counter = 0;
</script>

<script lang="ts">
	export let label: string = "";
	let id = "input_" + counter++;

	export let value = "";
</script>

<div class="input-wrapper">
	<textarea {id} bind:value {...$$props} placeholder="&nbsp;" rows="4" />
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

		textarea {
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

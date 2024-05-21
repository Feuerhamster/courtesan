<script context="module">
	let counter = 0;
</script>

<script lang="ts">
	export let label: string;
	let id = "select_" + counter++;

	export let value = "";
</script>

<div class="select-wrapper">
	<select {id} bind:value on:change {...$$props}>
		<slot />
	</select>
	<label for={id}>
		{label}
	</label>
	<span class="material-symbols-rounded">expand_more</span>
</div>

<style lang="scss">
	@import "../../../scss/defaults";
	@import "../../../scss/mixins";

	.select-wrapper {
		position: relative;
		display: flex;
		width: 100%;

		select {
			@include input-field;
			appearance: none;

			&:focus {
				border: 2px solid $color-pr;

				& + label {
					color: $color-pr;
				}
			}

			& + label {
				@include input-label-focused;
			}
		}

		label {
			@include input-label;
		}

		.material-symbols-rounded {
			position: absolute;
			right: 10px;
			top: 14px;
			color: $color-txt-2;
			font-size: 1.6em;
			pointer-events: none;
		}
	}
</style>

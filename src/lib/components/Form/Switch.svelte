<script context="module">
	let counter = 0;
</script>

<script lang="ts">
	export let label: string = "";
	let id = "check_" + counter++;

	export let checked = false;
</script>

<div class="switch-container">
	<p>{label}</p>
	<label class="switch" for={id}>
		<input type="checkbox" {id} bind:checked on:change />
		<span class="slider"></span>
	</label>
</div>

<style lang="scss">
	@import "../../../scss/defaults";

	.switch-container {
		height: 28px;
		display: grid;
		grid-template-columns: 1fr auto;
		align-items: center;
		min-width: 70px;
		gap: 8px;

		p {
			margin-left: 4px;
		}

		.switch {
			position: relative;
			display: flex;
			width: 45px;
			height: 18px;

			input {
				opacity: 0;
				width: 0;
				height: 0;

				&:checked + .slider {
					background-color: $color-pr;
				}

				&:checked + .slider:before {
					transform: translateX(21px);
					background-color: $color-sec;
				}
			}

			.slider {
				position: absolute;
				cursor: pointer;
				top: 0;
				left: 0;
				right: 0;
				bottom: 0;
				background-color: $color-edge;
				-webkit-transition: 0.4s;
				transition: 0.4s;
				border-radius: 32px;

				&:before {
					position: absolute;
					content: "";
					height: 24px;
					width: 24px;
					left: -0px;
					bottom: -3px;
					background-color: $color-txt;
					transition: 0.2s;
					border-radius: 50%;
					box-shadow: $shadow;
				}
			}
		}
	}
</style>

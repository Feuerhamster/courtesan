<header class="sub-page-header">
	<button class="material-symbols-rounded" on:click={() => history.back()}>arrow_back</button>

	<h1>
		<slot />
	</h1>
</header>

<style lang="scss">
	@import "../../scss/defaults";

	header {
		display: flex;
		gap: 8px;
		padding: 8px 0px;

		h1 {
			font-weight: 400;
			font-size: 1.2em;
		}

		button {
			border: 0;
			background: none;
			color: $color-txt-2;
			font-size: 1.4em;
		}
	}
</style>

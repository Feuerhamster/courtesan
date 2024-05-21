<header>
	<img src="/favicon.png" alt="courtesan logo" />
	<h1>Courtesan</h1>
	<a href="/settings" class="material-symbols-rounded"> settings </a>
</header>

<style lang="scss">
	@import "../scss/defaults";

	header {
		display: flex;
		align-items: center;
		gap: 1rem;

		h1 {
			font-size: 1.6rem;
			font-weight: 600;
			flex: 1;
		}

		img {
			border-radius: 32px;
			height: 2.6rem;
		}

		a {
			color: $color-txt;
			font-size: 2rem;
			text-decoration: none;
		}
	}
</style>

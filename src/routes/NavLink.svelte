<script lang="ts">
	import { page } from "$app/stores";

	export let exact = false;
	export let href = "/";
	export let icon = "";
	export let label = "";

	$: active = $page.url.pathname.startsWith(href) ? "active" : "";
	$: activeExact = $page.url.pathname === href ? "active" : "";
</script>

<a {...$$props} {href} class={exact ? activeExact : active}>
	<span class="material-symbols-rounded">
		{icon}
	</span>
	<span class="text">
		{label}
	</span>
</a>

<style lang="scss">
	@import "../scss/defaults";

	a {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: 4px;

		color: $color-txt-2;
		text-decoration: none;
		transition: color 0.2s;

		.material-symbols-rounded {
			display: flex;
			padding: 2px;
			transition:
				padding 0.2s,
				background 0.2s;
			border-radius: 32px;
			font-size: 1.4rem;
		}

		.text {
			font-size: 0.8em;
		}

		// funktioniert nicht
		&.active {
			color: $color-pr;

			.material-symbols-rounded {
				background-color: $color-pr-bg-2;
				padding: 2px 16px;
			}
		}
	}
</style>

<script lang="ts">
	import "@fontsource-variable/lexend";
	import "@fontsource-variable/material-symbols-rounded";

	import { fly } from "svelte/transition";
	import { App as CAP } from "@capacitor/app";
	import { goto } from "$app/navigation";
	import { page } from "$app/stores";
	import BottomNavigation from "./BottomNavigation.svelte";
	import { browser } from "$app/environment";

	if (browser) {
		CAP.addListener("backButton", async ({ canGoBack }) => {
			if (window.location.pathname === "/") CAP.exitApp();

			let pathSippets = window.location.pathname.split("/");

			while (pathSippets.length > 1) {
				pathSippets.pop();
				let url = pathSippets.join("/");

				if (url.length < 1) url = "/";

				try {
					goto(url, { replaceState: true });
					return;
				} catch (e) {}
			}
		});
	}
</script>

{#key $page.url.pathname}
	<main id="app" in:fly={{ duration: 250, y: -25 }}>
		<slot></slot>
	</main>
{/key}

{#if ["/", "/clients", "/dates", "/sales", "/expenses"].includes($page.url.pathname)}
	<BottomNavigation />
{/if}

<style lang="scss">
	@import "../scss/defaults";
	@import "../scss/reset";

	:global(body) {
		background-color: $color-bg;
		font-family: "Lexend Variable", sans-serif;
		display: flex;
		flex-direction: column;
		font-size: 18px;
		color: $color-txt;
		height: 100%;
		height: 100vh;
		-webkit-tap-highlight-color: transparent;
	}

	#app {
		display: flex;
		flex-direction: column;
		flex: 1;
		gap: 16px;
		padding: 12px;
		overflow-x: hidden;
		width: 100%;
		position: relative;
	}

	:global(.material-symbols-rounded) {
		font-family: "Material Symbols Rounded Variable", sans-serif;
		line-height: 1;
	}
	:global(.material-symbols-rounded.green) {
		color: $color-pr;
	}
	:global(.material-symbols-rounded.red) {
		color: $color-rd;
	}
	:global(.material-symbols-rounded.blue) {
		color: $color-bl;
	}
	:global(.material-symbols-rounded.orange) {
		color: $color-or;
	}
	:global(.material-symbols-rounded.yellow) {
		color: $color-yl;
	}

	:global(ul) {
		margin: 0;
		padding: 0 0 0 21px;
	}

	:global(li) {
		margin: 8px 0;
	}
</style>

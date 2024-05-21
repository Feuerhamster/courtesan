<script lang="ts">
	import NavLink from "./NavLink.svelte";
</script>

<nav>
	<NavLink href="/clients" icon="group" label="Clients" />
	<NavLink href="/dates" icon="calendar_month" label="Dates" />
	<NavLink href="/" icon="home" label="Overview" exact />
	<NavLink href="/sales" icon="paid" label="Sales" />
	<NavLink href="/expenses" icon="receipt_long" label="Expenses" />
</nav>

<style lang="scss">
	@import "../scss/defaults";

	nav {
		background-color: $color-bg-2;
		display: grid;
		grid-template-columns: repeat(5, 1fr);
		box-shadow: $shadow;
		padding: 8px 4px 6px 4px;
	}
</style>

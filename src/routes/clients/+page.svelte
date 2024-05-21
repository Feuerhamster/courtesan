<script lang="ts">
	import AppBar from "$lib/components/AppBar.svelte";
	import OverlayButton from "$lib/components/OverlayButton.svelte";
</script>

<AppBar placeholder="Search clients" icon="group" />

<OverlayButton href="/clients/add">
	<span class="material-symbols-rounded">add</span>
</OverlayButton>

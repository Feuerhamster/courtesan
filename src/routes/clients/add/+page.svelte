<script lang="ts">
	import Input from "$lib/components/Form/Input.svelte";
	import Select from "$lib/components/Form/Select.svelte";
	import Textarea from "$lib/components/Form/Textarea.svelte";
	import Button from "$lib/components/Button.svelte";
	import SubPageHeader from "$lib/components/SubPageHeader.svelte";

	// TODO: Custom field that adds new genders to a list
	const genderOptions = ["Unknown", "Male", "Female", "Non-Binary", "Other"];
</script>

<SubPageHeader>Add Client</SubPageHeader>

<form>
	<Input type="text" required label="Name *" />
	<Input type="number" required label="Age *" />
	<Select label="Gender *" required>
		{#each genderOptions as gender, i}
			<option value={i}>
				{gender}
			</option>
		{/each}
	</Select>
	<Input type="text" required label="Job *" />
	<Textarea label="Additional infos" />
	<Button color="pink">Add Client</Button>
</form>

<style lang="scss">
	@import "../../../scss/mixins.scss";

	form {
		@include page-content;
	}
</style>

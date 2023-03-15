<script>
	import Select from "./Select.svelte";

	let mode = "title";
	let transitionDelay = 1000;

	function handleContinue() {
		mode = "transition";
		setTimeout(() => {
			mode = "select";
		}, transitionDelay);
	}
</script>

<main class={`main-${mode}`}>
	<h1
		class={mode === "title"
			? ""
			: mode === "select"
			? "title-select-positioning"
			: ""}
	>
		My Digital Portfolio
	</h1>
	{#if mode === "select"}
		<Select />
	{:else if mode === "title"}
		<button on:click={handleContinue}>View Portfolio</button>
	{/if}
</main>

<style>
	main {
		margin-top: 30%;
		display: flex;
		flex-direction: column;
		align-items: center;

		transition: margin-top 1s;
	}
	main.main-transition,
	main.main-select {
		margin-top: 0;
	}
	button {
		margin-bottom: 200px;
	}
</style>

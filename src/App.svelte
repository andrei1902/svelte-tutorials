<script>
	export let name;
	export let age;

	$: uppercaseName = name.toUpperCase(); // Must use $ here

	$: console.log(name);

	$: if (name === 'Ionica') {
		age = 20;
	}

	function onClick() {
		age += 1
	}

	function changeName() {
		name = 'Ionica'
	}

	function nameInput(event) {
		name = event.target.value;
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}, my age is {age}!</h1>
<button on:click="{onClick}">Change age</button>
<button on:click="{changeName}">Change name</button>
<input type="text" value="{name}" on:input={nameInput}>
<input type="text" bind:value="{name}">

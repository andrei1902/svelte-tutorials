<script>
	export let name;
	export let age;

	$: uppercaseName = name.toUpperCase(); // Must use $ here

	function onClick() {
		age += 1
	}

	function changeName() {
		name = 'Ionica'
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

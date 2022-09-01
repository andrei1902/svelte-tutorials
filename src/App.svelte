<script>
	export let name;
	export let age;

	function onClick() {
		age += 1
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {name}, my age is {age}!</h1>
<button on:click="{onClick}">Change age</button>

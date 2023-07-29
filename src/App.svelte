<script>
	import ContactCard from './ContactCard.svelte';
	export let name = 'Risitas';
	let description = "Risitas";
	let jobTitle ="Kek lord";
	let image ="https://i.ytimg.com/vi/WDiB4rtp1qw/mqdefault.jpg";
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
</script>

<style>
	h1 {
		color: purple;
	}
	.form-container {
		max-width: 50%;
		display: flex;
		flex-direction: column;
		gap: .5rem;
	}
</style>

<h1>Hello {uppercaseName}, my age is {age}!</h1>

<button on:click="{onClick}">Change age</button>
<button on:click="{changeName}">Change name</button>

<form class="form-container">
	<input type="text" bind:value="{name}" placeholder="name">
	<input type="text" bind:value="{jobTitle}" placeholder="job title">
	<input type="text" bind:value="{image}" />
	<textarea rows="3" bind:value="{description}" placeholder="description"/>
</form>

<ContactCard
	useName={name}
	jobTitle={jobTitle}
	{description}
	{image}
/>

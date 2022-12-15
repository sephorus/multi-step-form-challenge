<script>
    /**
	 * @type {() => any}
	 */
     export let stepIncrement;

    let textValue = ''
</script>

<h1 class="text-3xl font-bold mb-3">Personal info</h1>
<p class="text-gray-400 mb-10">Please provide your name, email address, and phone number</p>
<form class="flex flex-col">
    <label for="text" value="hello">
    <input type="text" name="text" bind:value={textValue} required>
    <button on:click={() => stepIncrement()}>Button</button>
</form>
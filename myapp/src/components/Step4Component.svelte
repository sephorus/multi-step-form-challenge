<script>
    /**
	 * @type {() => any}
	 */
     export let stepIncrement;
     /**
	 * @type {() => any}
	 */
      export let stepDecrement;
</script>

<h1>Step 4</h1>
<div class="mt-auto flex justify-between align-bottom">
    <button class="text-gray-400 hover:text-black" on:click={() => stepDecrement()}>Go back</button>
    <button class="py-4 px-6 bg-blue-900 text-white rounded-lg mt-auto w-fit ml-auto" disabled={true} on:click={() => stepIncrement()}>Next Step</button>
</div>
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
<div>
    <button on:click={() => stepDecrement()}>Go back</button>
    <button on:click={() => stepIncrement()}>Button</button>
</div>
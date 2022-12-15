<script>
    /**
	 * @type {any}
	 */
     export let stepNumber;
     /**
	 * @type {() => any}
	 */
     export let stepIncrement;
     /**
	 * @type {any}
	 */
      export let stepDecrement;

     import Step1Component from '../components/Step1Component.svelte'
     import Step2Component from '../components/Step2Component.svelte'
     import Step3Component from '../components/Step3Component.svelte'
     import Step4Component from '../components/Step4Component.svelte'
</script>

<div class="col-span-2 py-14 pl-24 pr-24">
    {#if stepNumber === 1}
        <Step1Component {stepIncrement} />
    {/if}

    {#if stepNumber === 2}
        <Step2Component {stepIncrement} {stepDecrement} />
    {/if}

    {#if stepNumber === 3}
        <Step3Component {stepIncrement} {stepDecrement} />
    {/if}

    {#if stepNumber === 4}
        <Step4Component {stepIncrement} {stepDecrement} />
    {/if}
</div>
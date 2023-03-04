<script>
    /**
	 * @type {any}
	 */
     export let stepNumber
    /**
	 * @type {any}
	 */
     export let steps

     import image from '../images/bg-sidebar-desktop.svg'
</script>

<div id="stepTracker" class="flex flex-col p-4 relative">
    <img src={image} alt="stuff goes here">
    <div class="absolute px-8 py-10">
        {#each steps as step}
            <div class="mb-8 flex">
                <p class="mr-4 step text-center" class:currentStep={step.stepNumber === stepNumber} class:stepComplete={step.stepNumber < stepNumber}>{step.stepNumber}</p>
                <div class="flex flex-col">
                    <p class="text-xs text-blue-300 uppercase">Step {step.stepNumber}</p>
                    <h2 class="font-bold text-sm text-white tracking-wider uppercase">{step.stepTitle}</h2>
                </div>
            </div>
        {/each}
    </div>
</div>

<style>
    .stepComplete {
        background-color: lightgray;
        color: hsl(243, 100%, 62%);
        opacity: 0.6;
    }

    .currentStep {
        background-color: hsl(206, 94%, 87%);
        color: hsl(243, 100%, 62%);
    }
</style>
<script>
    /**
	 * @type {() => any}
	 */
     export let stepIncrement;
     /**
	 * @type {() => any}
	 */
      export let stepDecrement;

     import arcadeIcon from '../images/icon-arcade.svg';
     import advancedIcon from '../images/icon-advanced.svg';
     import proIcon from '../images/icon-pro.svg';

     let multiplier = 1;

     $: arcadeCost = 9 * multiplier;
     $: advancedCost = 12 * multiplier;
     $: proCost = 15 * multiplier;
</script>

<section class="flex flex-col">
    <h1 class="text-3xl font-bold mb-3">Select your plan</h1>
    <p class="text-gray-400 mb-8">You have the option of monthly and yearly billing.</p>
    <div class="grid grid-cols-3 w-full mb-8 gap-5">
        <div class="p-4 border-2 border-gray-200 rounded-lg">
            <img class="mb-10" src={arcadeIcon} alt="arcade plan option">
            <h2 class="text-base">Arcade</h2>
            <p class="text-sm text-gray-400">{`$${arcadeCost}/mo`}</p>
        </div>
        <div class="p-4 border-2 border-gray-200 rounded-lg">
            <img class="mb-10" src={advancedIcon} alt="advanced plan option">
            <h2 class="text-base">Advanced</h2>
            <p class="text-sm text-gray-400">{`$${advancedCost}/mo`}</p>
        </div>
        <div class="p-4 border-2 border-gray-200 rounded-lg">
            <img class="mb-10" src={proIcon} alt="pro plan option">
            <h2 class="text-base">Pro</h2>
            <p class="text-sm text-gray-400">{`$${proCost}/mo`}</p>
        </div>
    </div>

    <div class="flex justify-center align-middle mb-8 py-3 bg-slate-100 rounded-lg">
        <p class="mr-6">Monthly</p>
        <button class="mr-6">Toggle</button>
        <p>Yearly</p>
    </div>

    <div>
        <button on:click={() => stepDecrement()}>Go back</button>
        <button on:click={() => stepIncrement()}>Button</button>
    </div>
</section>
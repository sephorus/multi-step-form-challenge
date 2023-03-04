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
     let options = '';
     let toggled = false

     $: arcadeCost = 9 * multiplier;
     $: advancedCost = 12 * multiplier;
     $: proCost = 15 * multiplier;

     const selectOption = (/** @type {string} */ optionString) => {
        options = optionString
     }

     const changeMultiplier = () => {
        multiplier = multiplier === 1 ? 2 : 1;
        toggled = !toggled;
     }
</script>

<section class="flex flex-col h-full">
    <h1 class="text-3xl font-bold mb-3">Select your plan</h1>
    <p class="text-gray-400 mb-8">You have the option of monthly and yearly billing.</p>
    <div class="grid grid-cols-3 w-full mb-8 gap-5">
        <button class="p-4 border-2 border-gray-200 rounded-lg hover:border-black" class:interesting={options === 'arcade'} on:click={() => selectOption('arcade')}>
            <img class="mb-10" src={arcadeIcon} alt="arcade plan option">
            <h2 class="text-base text-left">Arcade</h2>
            <p class="text-sm text-gray-400 text-left">{`$${arcadeCost}/mo`}</p>
        </button>
        <button class="p-4 border-2 border-gray-200 rounded-lg hover:border-black" class:interesting={options === 'advanced'} on:click={() => selectOption('advanced')}>
            <img class="mb-10" src={advancedIcon} alt="advanced plan option">
            <h2 class="text-base text-left">Advanced</h2>
            <p class="text-sm text-gray-400 text-left">{`$${advancedCost}/mo`}</p>
        </button>
        <button class="p-4 border-2 border-gray-200 rounded-lg hover:border-black" class:interesting={options === 'pro'} on:click={() => selectOption('pro')}>
            <img class="mb-10" src={proIcon} alt="pro plan option">
            <h2 class="text-base text-left">Pro</h2>
            <p class="text-sm text-gray-400 text-left">{`$${proCost}/mo`}</p>
        </button>
    </div>

    <div class="flex justify-center align-middle mb-8 py-3 bg-slate-100 rounded-lg">
        <p>Monthly</p>
        <!-- <label class="relative w-8 h-5 toggle mx-6">
            <input class="opacity-0 h-0 w-0" type="checkbox" on:click={() => changeMultiplier()}>
            <span 
                class="slider absolute top-0 bottom-0 right-0 left-0 bg-blue-800 rounded-3xl cursor-pointer"
                class:toggleRight={toggled}
                class:toggleLeft={!toggled}
            >
            </span>
        </label> -->

        <button 
            on:click={() => changeMultiplier()}
            class="button-container"
        >
            <div
                class="button"
                class:toggleRight={toggled}
                class:toggleLeft={!toggled}
            ></div>
        </button>

        <p>Yearly</p>
    </div>

    <div class="mt-auto flex justify-between align-bottom">
        <button class="text-gray-400 hover:text-black hover:underline" on:click={() => stepDecrement()}>Go back</button>
        {#if options === ''}
            <button class="py-4 px-6 bg-gray-400 text-white rounded-lg mt-auto w-fit ml-auto" disabled={true} on:click={() => stepIncrement()}>Next Step</button>
        {:else}
            <button class="py-4 px-6 bg-blue-800 text-white rounded-lg mt-auto w-fit ml-auto" disabled={false} on:click={() => stepIncrement()}>Next Step</button>
        {/if}
    </div>
</section>

<style>
    .interesting {
        border: 2px solid orange;
    }

    .toggle:before {
        position: absolute;
        content: "";
        height: 12px;
        width: 12px;
        bottom: 4px;
        left: 4px;
        background-color: white;
        -webkit-transition: .4s;
        transition: .4s;
        border-radius: 12px;
        z-index: 1;
    }

    .toggleLeft {
        left: 4px;
    }

    .toggleRight {
        right: 4px;
    }

    .button-container {
        width: 38px;
        height: 20px;
        background-color: #022959;
        border-radius: 12px;
        position: relative;
        margin: 0 8px;
    }

    .button {
        position: absolute;
        position: absolute;
        top: 4px;
        background-color: white;
        height: 12px;
        width: 12px;
        border-radius: 50%;
    }

</style>

<script>
    /**
	 * @type {() => any}
	 */
     export let stepIncrement;
     /**
	 * @type {() => any}
	 */
      export let stepDecrement;

      const addOns = [
        {
            title: 'Online service',
            description: 'Access to multiplayer games',
            id: 'add-on-online-service',
            selected: false
        },
        {
            title: 'Larger storage',
            description: 'Extra 1TB of cloud save',
            id: 'add-on-larger-storage',
            selected: false
        },
        {
            title: 'Customizable profile',
            description: 'Custom theme on your profile',
            id: 'add-on-customizable-profile',
            selected: false
        }
      ]

      $: onlineServiceAddOn = addOns[0].selected
      $: largerStorageAddOn = addOns[1].selected
      $: customizableProfileAddOn = addOns[2].selected

      const updateAddOn = (/** @type {string | number} */ addOnOption) => {
        // @ts-ignore
        addOns[addOnOption] = !addOns[addOnOptions].selected
      }
</script>

<h1>Step 3</h1>
<div class="mt-auto flex justify-between align-bottom">
    <h1 class="text-3xl font-bold mb-3">Pick add-ons</h1>
    <p class="text-gray-400 mb-8">Add-ons help enhance your gaming experience</p>



    <button class="text-gray-400 hover:text-black" on:click={() => stepDecrement()}>Go back</button>
    <button class="py-4 px-6 bg-blue-900 text-white rounded-lg mt-auto w-fit ml-auto" disabled={true} on:click={() => stepIncrement()}>Next Step</button>
</div>
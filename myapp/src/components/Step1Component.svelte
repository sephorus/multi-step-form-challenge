<script>
    /**
	 * @type {() => any}
	 */
     export let stepIncrement;

    let name = ''
    let email = ''
    let phoneNumber = ''

    $: disabled = name === '' || email === '' || phoneNumber === ''
</script>

<section class="flex flex-col h-full">
    <h1 class="text-3xl font-bold mb-3">Personal info</h1>
    <p class="text-gray-400 mb-10">Please provide your name, email address, and phone number</p>
    <form class="flex flex-col">
        <div class="flex flex-col mb-6">
            <label class="mb-2" for="text" value="hello">Name</label>
            <input class="px-4 py-3" type="text" name="text" bind:value={name} placeholder="e.g. Stephen King" required>
        </div>

        <div class="flex flex-col mb-6">
            <label class="mb-2" for="email">Email</label>
            <input class="px-4 py-3"  type="text" name="email" bind:value={email} placeholder="e.g. stephenking@lorem.com" required>
        </div>

        <div class="flex flex-col mb-6">
            <label class="mb-2" for="phoneNumber">Phone Number</label>
            <input class="px-4 py-3"  type="text" name="phoneNumber" bind:value={phoneNumber} placeholder="e.g. +1 234 567 890" required>
        </div>
    </form>
    
    {#if name === '' || email === '' || phoneNumber === ''}
        <button class="py-4 px-6 bg-gray-400 text-white rounded-lg mt-auto w-fit ml-auto" {disabled} on:click={() => stepIncrement()}>Next Step</button>
    {:else}
        <button class="py-4 px-6 bg-blue-900 text-white rounded-lg mt-auto w-fit ml-auto" {disabled} on:click={() => stepIncrement()}>Next Step</button>
    {/if}
</section>
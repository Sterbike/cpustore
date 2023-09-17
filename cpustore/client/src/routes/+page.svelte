<script>
    import AMD from "./AMD/+page.svelte"
    import Intel from "./Intel/+page.svelte"
    import CPUDetails from "./CPUDetails/+page.svelte"
    export let menu = 0;
</script>

<div id="menu">
	<a href="/" on:click|preventDefault={() => (menu = 1)}>AMD</a>
	<a href="/" on:click|preventDefault={() => (menu = 2)}>Intel</a>
</div>

{#if menu === 0}
    <h1>Welcome</h1>
{:else if menu === 1}
    <AMD />
{:else if menu === 2}
    <Intel />
{:else}
    <h1>Page not Found</h1>
{/if}
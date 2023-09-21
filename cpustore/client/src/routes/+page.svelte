<script>
    import AMD from "./AMD/+page.svelte"
    import Intel from "./Intel/+page.svelte"
    import CPUDetails from "./CPUDetails/+page.svelte"
    import { menu } from '../../src/store';

    let currentMenu;
    menu.subscribe(value => {
        currentMenu = value;
    });
    menu.set(0);
</script>

<div class="menu">
	<a href="/" on:click|preventDefault={() => (currentMenu = 0)}>Main</a>
	<a href="/" on:click|preventDefault={() => (currentMenu = 1)}>AMD</a>
	<a href="/" on:click|preventDefault={() => (currentMenu = 2)}>Intel</a>
</div>

{#if currentMenu === 0}
    <h1 class="Welcome">Welcome to our website</h1>
{:else if currentMenu === 1}
    <AMD {menu}/>
{:else if currentMenu === 2}
    <Intel />
{:else if currentMenu === 3}
    <CPUDetails />
{:else}
    <h1>Page not Found</h1>
{/if}

<style>
    .Welcome{
        text-align: center;
    }
    .menu {
        padding-top: 3vh;
        height: 6vh;
        background-color: bisque;
        text-align: center;
    }
    .menu a{
        color:black;
        padding-top: 3vh;
        margin: 3vw;
        font-size: 24px;
        text-decoration: none;
        
    }
    .menu a:hover{
        text-decoration: underline;
    }
</style>
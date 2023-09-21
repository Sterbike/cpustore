<script>
    import jsonData from "../../data/cpus.json";
    import { menu } from '../../../src/store'
    import { onMount } from "svelte";

    const Intelcpus = jsonData.cpus.find(cpu => cpu.brand === 'Intel');

    onMount(() => {
        menu.set(2);
    });
    
    export const sendData = (data) => {
        localStorage.setItem("CpuName", data)
        menu.set(3);
        console.log(menu);
    }


</script>

<body> 
    <h1>Intel</h1>
    {#if Intelcpus}
    <div class="Intelcpu" >
        {#each Intelcpus.models as model}
            <div class="cpu">
                <img src={model.img} alt="cpu">
                <p>{model.name}</p>
                <p>Price: {model.price}$</p>
                <a on:click={() => sendData(model.name)} href="./" >view more...</a>
            </div>

        {/each}
    </div>
    {:else}
        <p>No Intel CPUs found.</p>
    {/if}
</body>

<style>
    .Intelcpu{
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
        text-align: center;
    }

    h1{
        text-align: center;
    }

    .cpu{
        margin: auto;
        margin-top: 10vh;
        background-color: aquamarine;
        width: max-content;
    }

    img{
        width: 10vw;
        height: 18vh;
    }
</style>
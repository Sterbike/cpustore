<script>
    import jsonData from "../../data/cpus.json";
    const Intelcpus = jsonData.cpus.find(cpu => cpu.brand === 'Intel');
    export const sendData = (data) => {
        localStorage.setItem("CpuName", data)
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
                <a on:click={() => sendData(model.name)} href="./CPUDetails" >view more...</a>
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
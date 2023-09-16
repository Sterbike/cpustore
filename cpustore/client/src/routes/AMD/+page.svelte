<script>
    import jsonData from "../../data/cpus.json";
    const AMDcpus = jsonData.cpus.find(cpu => cpu.brand === 'AMD');
</script>

<body> 
    <h1>AMD</h1>
    {#if AMDcpus}
    <div class="AMDcpu">
        {#each AMDcpus.models as model}
            <div>
                <img src={model.img} alt="cpu">
                <p>{model.name}</p>
                <p>Price: {model.price}$</p>
                <a href="asd">view more...</a>
            </div>

        {/each}
    </div>
    {:else}
        <p>No AMD CPUs found.</p>
    {/if}
</body>

<style>
    .AMDcpu{
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
        text-align: center;
    }
    h1{
        text-align: center;
    }

    img{
        width: 10vw;
        height: 18vh;
    }
</style>
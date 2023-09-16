<script>
    import jsonData from "../../data/cpus.json";
    const Intelcpus = jsonData.cpus.find(cpu => cpu.brand === 'Intel');
</script>

<body> 
    <h1>Intel</h1>
    {#if Intelcpus}
    <div class="Intelcpu" >
        {#each Intelcpus.models as model}
            <div >
                <img src={model.img} alt="cpu">
                <p>{model.name}</p>
                <p>Price: {model.price}$</p>
                <a href="asd">view more...</a>
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

    img{
        width: 5vw;
    }
</style>
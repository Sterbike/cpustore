<script>
    import jsonData from "../../data/cpus.json";

    const cpuname = localStorage.getItem("CpuName");
    let cpuModel;

    if (cpuname) {
        
        const matchingCpu = jsonData.cpus.find(cpu => {
            return cpu.models.some(model => model.name === cpuname);
        });

        if (matchingCpu) {
            cpuModel = matchingCpu.models.find(model => model.name === cpuname);
        }
    }

    console.log(cpuModel);
</script>
<div class="cpu">
    <img src={cpuModel.img} alt="">
    <h1>{cpuname}</h1>
    <p>Cores: {cpuModel.cores}</p>
    <p>Threads: {cpuModel.threads}</p>
    <p>Base Clock: {cpuModel.base_clock}</p>
    <p>Boost Clock: {cpuModel.boost_clock}</p>
    <p>Cache: {cpuModel.cache}</p>
    <p>Socket: {cpuModel.socket}</p>
    <p>TDP: {cpuModel.tdp}</p>
    <p>Architecture: {cpuModel.architecture}</p>
    <p>Manufacturing Process: {cpuModel.manufacturing_process}</p>
    <p>Release Date{cpuModel.release_date}</p>
    <h2>Price: {cpuModel.price}$</h2>

</div>

<style>

    .cpu{
        text-align: center;
        margin: auto;
    }

    img{
        width: 20w;
        height: 36vh;
    }
</style>
<script>
    import jsonData from "../data/cpus.json";

    const { cpus } = jsonData;
</script>

{#each cpus as cpu}
    <a href="./{cpu.brand}" class="brand">{cpu.brand}</a>
{/each}
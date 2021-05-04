<script>
    import plannings from "../data/plannings.js";
    const { mai } = plannings;
    const { ADS } = mai;
    console.log(ADS);
</script>

<h1>plannings</h1>
{#each ADS as { jour, agentJour, agentNuit, chefJour, chefNuit }}
    <div class="flex">
        <div class="col">
            {jour}
        </div>
        <div class="col">
            <div class="bold">
                {chefJour.nom}
            </div>
            <div>
                {agentJour.nom}
            </div>
        </div>
        <div class="col">
            <div class="bold">
                {chefNuit.nom}
            </div>
            <div>
                {agentNuit.nom}
            </div>
        </div>
    </div>
{/each}
<!-- {@debug plannings} -->

<!-- {plannings.length} -->
<style>
    .flex {
        display: flex;
        padding: 1rem;
    }
    .col {
        padding: 1rem;
        display: flex;
        justify-content: flex-start;
        flex-direction: column;
    }
    .bold {
        font-weight: bold;
    }
</style>

<script>
    import plannings from "../data/plannings.js"
    const {mai} = plannings
    const {ADS} = mai
    console.log(ADS)

</script>

<h1>plannings</h1>
{#each ADS as {jour, agentJour, agentNuit, chefJour, chefNuit}}
<p>{jour} {chefJour.nom} {chefNuit.nom} {agentJour.nom} {agentNuit.nom}</p>
{/each}
<!-- {@debug plannings} -->
<!-- {plannings.length} -->
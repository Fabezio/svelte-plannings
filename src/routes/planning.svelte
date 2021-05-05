<script>
    import plannings from "../data/plannings.js";
    const { mai } = plannings;
    const { ADS } = mai;
    // console.log(ADS.flat());
    const namesList = [];
    function isInList(obj) {
        if (!namesList.includes(obj.nom.toLowerCase()))
            return namesList.push(obj.nom.toLowerCase());
    }
    ADS.map(({ agentJour, agentNuit, chefJour, chefNuit }) => {
        isInList(agentJour);
        isInList(agentNuit);
        isInList(chefJour);
        isInList(chefNuit);
        //    isInlist(agentJour)
        // namesList.push(agentNuit.nom);
        // namesList.push(chefJour.nom);
        // namesList.push(chefNuit.nom);
        // namesList.push(agentJour)
    });
    namesList.sort();
    console.log(namesList);
    function nameDisplay(obj) {
        const { nom, prenom } = obj;
        return (prenom ? `${nom}, ${prenom}` : nom) || "-----";
    }
    const today = new Date().getDate();
    let worker = "";
    console.log(today);
</script>

<h1>plannings</h1>
<!-- <input type="text" bind:value={worker} placeholder="entrez le nom de l'agent" />
{#if namesList.includes(worker)}
    <p>{worker}</p>

{/if} -->
{#each ADS as { jour, agentJour, agentNuit, chefJour, chefNuit }}
    {#if jour >= today}
        <div class="flex">
            <div class="nb">
                {jour}
            </div>
            <div class="col">
                <div class="bold">
                    {nameDisplay(chefJour)}
                </div>
                <div>
                    {nameDisplay(agentJour)}
                </div>
            </div>
            <div class="col">
                <div class="bold">
                    {nameDisplay(chefNuit)}
                </div>
                <div>
                    {nameDisplay(agentNuit)}
                </div>
            </div>
        </div>
    {/if}
{/each}

<!-- {@debug plannings} -->

<!-- {plannings.length} -->
<style>
    .flex {
        display: flex;
        padding: 1rem;
        justify-content: center;
    }
    .nb {
        padding: 1rem;
    }
    .col {
        text-transform: uppercase;
        padding: 1rem;
        display: flex;
        justify-content: flex-start;
        flex-direction: column;
        min-width: 200px;
    }
    .bold {
        font-weight: bold;
    }
</style>

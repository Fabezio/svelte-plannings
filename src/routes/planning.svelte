<script>
    import plannings from "../data/plannings.js";
    const { mai } = plannings;
    const { ADS } = mai;
    console.log(ADS.flat());
    const namesList = [];
    function isInList(obj) {
        if (!namesList.includes(obj.nom)) return namesList.push(obj.nom);
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
</script>

<h1>plannings</h1>
{#each ADS as { jour, agentJour, agentNuit, chefJour, chefNuit }}
    <div class="flex">
        <div class="col">
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
{/each}

<!-- {@debug plannings} -->

<!-- {plannings.length} -->
<style>
    .flex {
        display: flex;
        padding: 1rem;
    }
    .col {
        text-transform: uppercase;
        padding: 1rem;
        display: flex;
        justify-content: flex-start;
        flex-direction: column;
    }
    .bold {
        font-weight: bold;
    }
</style>

<script>
// const { default: Planning }=require("./planning.svelte")

    const date= new Date()
    const options = {year: "numeric",weekday: "long", day:"numeric", month:"long", week: "numeric"}
    const months = "janvier février mars avril mai juin juillet août septembre octobre novembre décembre".split(" ")
    const dates = []
    const days = "lundi mardi mercredi jeudi vendredi samedi dimanche".split(" ")
    const formatter = Intl.DateTimeFormat("fr", options)
    const line = 7
</script>
<h1>Calendrier</h1>
<!-- <p>{formatter.month(date)}</p> -->
<p>aujourd'hui: {formatter.format(date)}</p>
<!-- {#each months as m}
<p>{m}</p>
{/each} -->

<table>
    <tr>
        {#each days as day}
        <td>{day}</td>
        {/each}
    </tr>
    
    <tr>
        {#each [...Array(31).keys()] as day}
        
        {#if day< 7}
        
        <td>{day+1}</td>
        {/if}
        {/each}
    </tr>
</table>

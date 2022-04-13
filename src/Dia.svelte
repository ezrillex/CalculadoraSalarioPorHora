<script>
    export let escenarios;
    export let dia;

    function calcDiario(escena) {
        let dias = 0;
        for (let i = 0; i < escena.dias.length; i++) {
            if (escena.dias.charAt(i) == "1") {
                dias++;
            }
        }
        return (escena.sal / 4 / dias).toFixed(2);
    }
</script>

<td>
    {#each escenarios as escena}
        {#if escena.dias.charAt(dia) == "1"}
            #{escena.id} ${calcDiario(escena)} ({escena.horas} hours).
            <br />
        {/if}
    {/each}
</td>

<style>
     td {
        border-style: solid;
        border-color: black;
        height: 10rem;
    }
</style>

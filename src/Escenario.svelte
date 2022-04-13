<script lang="ts">
    export let escena;

    let work = "";
    let semanal = 0;
    let days = ["monday", "tuesday", "wednesday", "thursday", "friday", "saturday", "sunday"]
    for (let i = 0; i < escena.dias.length; i++) {
        if(escena.dias.charAt(i) == '1'){
            work += " " + days[i];
            semanal += escena.horas;
        }
    }
    semanal *= 4;
    semanal = escena.sal / semanal;
</script>

<main>
    <div>Scenario {escena.id}:</div>
    <div>Work {work}</div>
    <div>{escena.horas} hours per day</div>
    <div>For ${semanal.toFixed(2)}/Hour (${escena.sal} a month)</div>
</main>

<style>
    main {
        border-style: solid;
        border-color: black;
        padding: 1rem;
    }
</style>
<script lang="ts">
    export let escena;

    let work = "";
    let semanal = 0;
    let days = ["lunes", "martes", "miercoles", "jueves", "viernes", "sabado", "domingo"]
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
    <div>Escenario {escena.id}:</div>
    <div>Trabajar {work}.</div>
    <div>{escena.horas} horas al dia</div>
    <div>Por ${semanal.toFixed(2)}/Hora (${escena.sal} al mes)</div>
</main>

<style>
    main {
        border-style: solid;
        border-color: black;
        padding: 1rem;
    }
</style>
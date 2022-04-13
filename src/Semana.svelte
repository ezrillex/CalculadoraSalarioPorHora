<script>
    import Dia from "./Dia.svelte";

    export let escenarios;



</script>

<tr>
    <Dia dia={0} {escenarios} />
    <Dia dia={1} {escenarios} />
    <Dia dia={2} {escenarios} />
    <Dia dia={3} {escenarios} />
    <Dia dia={4} {escenarios} />
    <Dia dia={5} {escenarios} />
    <Dia dia={6} {escenarios} />
</tr>

<style>
   
</style>

<script lang="ts">
	import Escenario from "./Escenario.svelte";
	import Semana from "./Semana.svelte";

	let escenarios = [];

	let d1,
		d2,
		d3,
		d4,
		d5,
		d6,
		d7 = false;

	let salario;
	let horas;
	function agregar() {
		escenarios = [
			...escenarios,
			{
				id: escenarios.length + 1,
				dias: joinDays(),
				horas: horas,
				sal: salario,
			},
		];
	}

	function reset(){
		escenarios = []
	}

	function joinDays() {
		let string = "";
		string += d1 ? "1" : "0";
		string += d2 ? "1" : "0";
		string += d3 ? "1" : "0";
		string += d4 ? "1" : "0";
		string += d5 ? "1" : "0";
		string += d6 ? "1" : "0";
		string += d7 ? "1" : "0";
		return string;
	}
</script>

<main>
	<div class="d-block">
		<table>
			<tr>
				<th><h1>Monday</h1></th>
				<th><h1>Tuesday</h1></th>
				<th><h1>Wednesday</h1></th>
				<th><h1>Thursday</h1></th>
				<th><h1>Friday</h1></th>
				<th><h1>Saturday</h1></th>
				<th><h1>Sunday</h1></th>
			</tr>
			
				<Semana {escenarios} />
				<Semana {escenarios} />
				<Semana {escenarios} />
				<Semana {escenarios} />

		</table>
	</div>
		
		<div class="escenarios">
			<h1>Scenarios:</h1>
			<label for="salario">Salary:</label>
			<input bind:value={salario} type="number" name="salario" id="salario" />
			<br />
			<br />
			<label for="horas">Hours per day:</label>
			<input bind:value={horas} type="number" name="horas" id="horas" />
			<br />
			<p>Dias:</p>
			<input bind:checked={d1} type="checkbox" name="lun" id="lun" /><label
				for="lun">Monday</label
			>
			<input bind:checked={d2} type="checkbox" name="mar" id="mar" /><label
				for="mar">Tuesday</label
			>
			<input bind:checked={d3} type="checkbox" name="mie" id="mie" /><label
				for="mie">Wednesday</label
			>
			<input bind:checked={d4} type="checkbox" name="jue" id="jue" /><label
				for="jue">Thursday</label
			>
			<input bind:checked={d5} type="checkbox" name="vie" id="vie" /><label
				for="vie">Friday</label
			><br />
			<input bind:checked={d6} type="checkbox" name="sab" id="sab" /><label
				for="sab">Saturday</label
			>
			<input bind:checked={d7} type="checkbox" name="dom" id="dom" /><label
				for="dom">Sunday</label
			>
			<br />
			<br />
			<button on:click={agregar}>Add Scenario</button>
			<button on:click={reset}>Reset</button>
			<br />
			<br />
			{#each escenarios as escena}
				<Escenario {escena} />
				<br />
			{/each}
		</div>
	
</main>

<style>

	main {
		display: flex;
		justify-content: center;
	}
	
	.d-block {
		display: block;
	}

	table,
	tr,
	th {
		border-style: solid;
		border-color: black;
	}

	th {
		width: 10rem;
	}

	tr {
		height: fit-content;
	}

	th>h1{
		height: min-content;
	}

	.escenarios {
		margin-left: 2rem;
	}
</style>

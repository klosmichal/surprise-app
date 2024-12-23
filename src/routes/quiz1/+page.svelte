<svelte:head>
	<title>Quiz 1</title>
	<meta name="quiz1-question" content="quiz1" />
</svelte:head>

<script>
	import { goto } from '$app/navigation';

	let values = {
		two: '',
		three: '',
		five: '',
		ten: ''
	};

	const correctValues = {
		two: 2,
		three: 3,
		five: 5,
		ten: 10
	};

	function checkValues() {
		for (let key in values) {
			if (parseInt(values[key]) !== correctValues[key]) {
				alert(`Incorrect values`);
				return;
			}
		}
		goto('/quiz1-solution');
	}
</script>

<div class="text-column">
	
	
	<h1>Rozwiąż mnie</h1>

	<p>
		Liczby w wierszach i kolumnach oznaczają sumę liczb w danym wierszu lub kolumnie.
		Każdy kolor oznacza inną liczbę.
		Podaj wartość każdego koloru.
	</p>

	<table>
        <tbody>
			<tr>
				<td><div class="color-block two"></div></td>
				<td><div class="color-block three"></div></td>
				<td><div class="color-block five"></div></td>
				<td><div class="color-block ten"></div></td>
				<td><p>20</p></td>
			</tr>
			<tr>
				<td><div class="color-block three"></div></td>
				<td><div class="color-block five"></div></td>
				<td><div class="color-block ten"></div></td>
				<td><div class="color-block two"></div></td>
				<td><p>20</p></td>
			</tr>
			<tr>
				<td><div class="color-block three"></div></td>
				<td><div class="color-block two"></div></td>
				<td><div class="color-block ten"></div></td>
				<td><div class="color-block three"></div></td>
				<td><p>18</p></td>
			</tr>
			<tr>
				<td><div class="color-block ten"></div></td>
				<td><div class="color-block three"></div></td>
				<td><div class="color-block five"></div></td>
				<td><div class="color-block five"></div></td>
				<td><p>23</p></td>
			</tr>
			<tr>
				<td><div class="color-block five"></div></td>
				<td><div class="color-block five"></div></td>
				<td><div class="color-block two"></div></td>
				<td><div class="color-block five"></div></td>
				<td><p>17</p></td>
			</tr>
			<tr>
				<td><p>23</p></td>
				<td><p>18</p></td>
				<td><p>32</p></td>
				<td><p>25</p></td>
			</tr>
		</tbody>
    </table>

    <form on:submit|preventDefault={checkValues} class="form-inline">
        <div class="input-group">
            <div class="color-block two"></div>
            <input type="text" style="" bind:value={values.two}>
        </div>
        <div class="input-group">
            <div class="color-block three"></div>
            <input type="text" bind:value={values.three}>
        </div>
		<div class="input-group">
            <div class="color-block five"></div>
            <input type="text" bind:value={values.five}>
        </div>
        <div class="input-group">
            <div class="color-block ten"></div>
            <input type="text" bind:value={values.ten}>
        </div>
		<br>
        <button type="submit">Sprawdź to dzieciaku</button>
    </form>
</div>

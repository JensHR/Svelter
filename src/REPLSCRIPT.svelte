<script>
	let count = 0;
	let kill = 0;
	
	$: doubled = count * 2;
	$: halved = count / 2;
	$: doubleHalved = doubled - halved;
	
	function incrementCount() {
		count++;
	}
	function killCount() {
		count = 0;
		kill++;
	}
</script>

<button on:click={incrementCount}>
	Clicked {count} {count === 1 ? 'time' : 'times'}
</button>

<button on:click={killCount}>
	Killed {kill} {kill === 1 ? 'time' : 'times'}
</button>


<div>
	Doubled = {doubled}
</div>
<div>
	Halved = {halved}
</div>
<div>
	One and a half = {doubleHalved}
</div>
<script>
	let pwd
	const submitHandler = () => {
		if (pwd === 'test') {
			window.location.href = '/ticket'
		}
	}
</script>

<div id="home">
	<input
		type="password"
		bind:value={pwd}
	/>
	<button on:click={submitHandler}>Submit</button>
</div>

<style>
	#home {
		width: 50%;
		height: 100%;
		display: flex;
		flex-direction: column;
		margin: auto;
		padding: 50% 0;
	}

	input {
		height: 50px;
		border-radius: 10px;
		border: 1px solid black;
		padding: 5px;
		font-size: larger;
	}

	button {
		background-color: rgb(104, 104, 254);
		color: white;
		height: 50px;
		margin: 20px;
		border-radius: 50px;
		border-style: none;
		box-shadow: 0 0 10px black;
		font-size: larger;
	}
</style>

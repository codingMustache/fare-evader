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
		align-items: center;
		flex-direction: column;
		margin: 0 auto;
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
		border-radius: 20px;
		border-style: none;
		background-color: rgb(104, 104, 254);
		height: 80px;
		color: white;
		width: 100%;
		box-shadow: 0 0 30px rgb(79, 79, 233);
		margin: 20px;
		border-radius: 20px;
		font-size: larger;
	}
</style>

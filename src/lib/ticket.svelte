<div>
	<h1>RTA</h1>
	<p>Show operator your ticket</p>
</div>
<button on:click={showPopup}>x</button>
<div
	id="outerCricle"
	class="circle"
>
	<div
		id="innerCricle"
		class="circle"
	>
		<img
			src="logo.jpeg"
			alt="logo"
			width="75px"
		/>
	</div>
</div>
<h1 id="time">{time.toLocaleTimeString('en-US')}</h1>
<div id="card">
	<h1>Adult Single Ride, Bus & <br /> Streetcar</h1>
	<p>New Orleans, LA</p>
	<h2>
		Expires {today.toLocaleDateString('en-US', {
			month: 'short',
			day: 'numeric',
			year: 'numeric'
		})} at {today.toLocaleTimeString('en-US', {
			hour: 'numeric',
			minute: 'numeric'
		})}
	</h2>
</div>

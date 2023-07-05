<!-- Landing Page -->
<script>
	var targetDate = new Date('October 28, 2023 00:00:00').getTime();
	var now = new Date().getTime();
	var timeLeft = targetDate - now;
	var months = Math.floor(timeLeft / (1000 * 60 * 60 * 24 * 30));
	var days = Math.floor((timeLeft % (1000 * 60 * 60 * 24 * 30)) / (1000 * 60 * 60 * 24));
	var hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
	var minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
	var seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);

	function countdown() {
		setInterval(() => {
			now = new Date().getTime();
			timeLeft = targetDate - now;
			months = Math.floor(timeLeft / (1000 * 60 * 60 * 24 * 30));
			days = Math.floor((timeLeft % (1000 * 60 * 60 * 24 * 30)) / (1000 * 60 * 60 * 24));
			hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
			minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
			seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);
		}, 1000);
	}

	countdown();
</script>

<div class="storyContainer">
	<p>
		We met 6 years ago in an intro to philosophy class as college freshmen at Radford University. We
		were lucky enough to be randomly put in the same project group that worked together the entire
		semester. 6 years, one dog, one apartment, one cat and one house later we are so thrilled to be
		getting married this year and hope that you can join us for the celebration!
	</p>
</div>
<div class="countdownContainer">
	<h2>
		{#if months == 1}
			{months} Month
		{:else}
			{months} Months
		{/if}
		{#if days == 1}
			{days} Day
		{:else}
			{days} Days
		{/if}
		{#if hours == 1}
			{hours} Hour
		{:else}
			{hours} Hours
		{/if}
		{#if minutes == 1}
			{minutes} Minute
		{:else}
			{minutes} Minutes
		{/if}
		{#if seconds == 1}
			{seconds} Second
		{:else}
			{seconds} Seconds
		{/if}
		until the wedding day.
	</h2>
</div>
<div class="navContainer">
	<!-- TODO: Determine if links should be clicked from text or the whole region -->

	<a href="/rsvp" class="intPageLink">RSVP</a>
	<div class="registriesContainer">
		<a
			href="https://www.williams-sonoma.com/registry/qvtdq7xv89/registry-list.html"
			target="_blank"
			class="registryLink">Registry (Williams Sonoma)</a
		>
		<a
			href="https://www.amazon.com/wedding/katie-oakes-cade-gray--october-2023/registry/1EFU39WJ0ZUB5"
			target="_blank"
			class="registryLink">Registry (Amazon)</a
		>
	</div>
	<a href="/faq" class="intPageLink">FAQ</a>
</div>

<style>
	h2 {
		color: #222;
	}
	.storyContainer {
		margin-left: 10vw;
		margin-right: 10vw;
		padding: 20px;
		background: #d2cfc6cf;
		box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
		border-radius: 5px;
		display: flex;
		flex-direction: column;
		align-items: center;
		color: #222;
		font-size: 20px;
	}
	.countdownContainer {
		display: flex;
		text-align: center;
		padding: 20px;
	}
	.navContainer {
		padding: 20px;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.registriesContainer {
		padding-top: 20px;
		padding-bottom: 20px;
		display: flex;
		align-content: space-around;
	}
	.registryLink {
		background: #bf8e91;
		font-size: 1.3rem;
		width: 20vw;
		height: 100px;
		margin: 10px;
		padding: 10px;
		display: flex;
		align-items: center;
		justify-content: center;
		text-align: center;
		box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
		border-radius: 5px;
	}
	a {
		text-decoration: none;
		color: #222;
	}
	.intPageLink {
		background: #6e9277;
		font-size: 2rem;
		width: 90%;
		height: 100px;
		display: flex;
		align-items: center;
		justify-content: center;
		text-align: center;
		box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
		border-radius: 5px;
	}
	.intPageLink:hover {
		transform: scale(1.1);
		box-shadow: 0 0 10px 5px #4f6455;
	}
	.registryLink:hover {
		transform: scale(1.1);
		box-shadow: 0 0 10px 5px #806668;
	}
</style>

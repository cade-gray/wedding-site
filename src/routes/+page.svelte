<!-- Landing Page -->
<script>
	let targetDate = new Date('October 28, 2023 16:30:00').getTime();
	let countingDown = true;
	let loaded = false;
	let interval;

	let elapsedTime = {
		years: 0,
		months: 0,
		days: 0,
		hours: 0,
		minutes: 0,
		seconds: 0
	};

	function updateElapsedTime() {
		const now = new Date().getTime();
		let timeDifference = countingDown ? targetDate - now : now - targetDate;

		if (timeDifference <= 0) {
			countingDown = false;
			timeDifference = now - targetDate;
		}
		loaded = true;
		elapsedTime = {
			years: Math.floor(timeDifference / (1000 * 60 * 60 * 24 * 365)),
			months: Math.floor(
				(timeDifference % (1000 * 60 * 60 * 24 * 365)) / (1000 * 60 * 60 * 24 * 30)
			),
			days: Math.floor((timeDifference % (1000 * 60 * 60 * 24 * 30)) / (1000 * 60 * 60 * 24)),
			hours: Math.floor((timeDifference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)),
			minutes: Math.floor((timeDifference % (1000 * 60 * 60)) / (1000 * 60)),
			seconds: Math.floor((timeDifference % (1000 * 60)) / 1000)
		};
	}

	function startCounter() {
		interval = setInterval(updateElapsedTime, 1000);
	}

	startCounter();
</script>

<div class="storyContainer">
	<p>
		We met 6 years ago in an intro to sociology class as college freshmen at Radford University. We
		were lucky enough to be randomly put in the same project group that worked together the entire
		semester. 6 years, one dog, one apartment, one cat and one house later we are so thrilled to be
		getting married this year and hope that you can join us for the celebration!
	</p>
</div>
<div class="countdownContainer">
	<h2>
		{#if !loaded}
			<div class="loadingText">0 Days 0 Hours 0 Minutes 0 Seconds until we get married!</div>
		{:else if countingDown}
			{#if elapsedTime.years > 0}
				{elapsedTime.years}
				{#if elapsedTime.years === 1}Year{:else}Years{/if}{' '}
			{/if}
			{#if elapsedTime.months > 0}
				{elapsedTime.months}
				{#if elapsedTime.months === 1}Month{:else}Months{/if}{' '}
			{/if}
			{#if elapsedTime.days > 0}
				{elapsedTime.days}
				{#if elapsedTime.days === 1}Day{:else}Days{/if}{' '}
			{/if}
			{#if elapsedTime.hours > 0}
				{elapsedTime.hours}
				{#if elapsedTime.hours === 1}Hour{:else}Hours{/if}{' '}
			{/if}
			{#if elapsedTime.minutes > 0}
				{elapsedTime.minutes}
				{#if elapsedTime.minutes === 1}Minute{:else}Minutes{/if}{' '}
			{/if}
			{#if elapsedTime.seconds > 0}
				{elapsedTime.seconds}
				{#if elapsedTime.seconds === 1}Second{:else}Seconds{/if}{' '}
			{/if}
			until we get married!
		{:else}
			{#if elapsedTime.years > 0}
				{elapsedTime.years}
				{#if elapsedTime.years === 1}Year{:else}Years{/if}{' '}
			{/if}
			{#if elapsedTime.months > 0}
				{elapsedTime.months}
				{#if elapsedTime.months === 1}Month{:else}Months{/if}{' '}
			{/if}
			{#if elapsedTime.days > 0}
				{elapsedTime.days}
				{#if elapsedTime.days === 1}Day{:else}Days{/if}{' '}
			{/if}
			{#if elapsedTime.hours > 0}
				{elapsedTime.hours}
				{#if elapsedTime.hours === 1}Hour{:else}Hours{/if}{' '}
			{/if}
			{#if elapsedTime.minutes > 0}
				{elapsedTime.minutes}
				{#if elapsedTime.minutes === 1}Minute{:else}Minutes{/if}{' '}
			{/if}
			{#if elapsedTime.seconds > 0}
				{elapsedTime.seconds}
				{#if elapsedTime.seconds === 1}Second{:else}Seconds{/if}{' '}
			{/if}
			since we got married.
		{/if}
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
	.loadingText {
		color: transparent;
		text-shadow: 0 0 10px #000;
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

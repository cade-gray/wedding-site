<script>
	import '@fontsource-variable/playfair-display';
	import RingLogo from '../ringLogo.svelte';
	import InitialLogo from '../initialLogo.svelte';
</script>

<div class="mainContainer">
	<div class="contentContainer">
		<div class="header">
			<a href="/">
				<RingLogo />
			</a>
		</div>
		<slot />
		<div>
			<InitialLogo />
		</div>
	</div>
</div>

<style>
	.mainContainer {
		padding: 30px;
		background-image: url(../lib/background.svg);
	}
	.contentContainer {
		background: #d2cfc687;
		display: flex;
		flex-direction: column;
		align-items: center;
		box-shadow: 0px 3px 4px 3px rgba(0, 0, 0, 0.25);
		border-radius: 5px;
		min-height: 93vh;
		font-family: 'Playfair Display Variable';
	}
	.header {
		padding: 2em;
	}
	a {
		text-decoration: none;
	}
	h1 {
		color: black;
	}
	.header:hover {
		transform: scale(1.1);
	}
	@media screen and (max-width: 800px) {
		.contentContainer {
			margin: 10px;
		}
		.mainContainer {
			padding: 0px;
		}
	}
</style>

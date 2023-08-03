<script>
	import '@fontsource-variable/playfair-display';
	import RingLogo from '../ringLogo.svelte';
	import InitialLogo from '../initialLogo.svelte';
</script>

<div class="mainContainer">
	<div class="contentContainer">
		<div class="header">
			<a href="/">
				<h1>
					<span class="name" id="cd">Cade</span> &amp; <span class="name" id="kt">Katie</span>
				</h1>
				<h1 class="date">October 28<sup>th</sup>, 2023</h1>
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
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
	}
	h1 {
		color: #222;
	}
	a {
		text-decoration: none;
	}
	.header:hover {
		transform: scale(1.1);
	}
	.name {
		font-size: 3rem;
		font-weight: lighter;
	}
	#cd {
		text-shadow: 2px 1px 1px #6e9277;
	}
	#kt {
		text-shadow: 2px 1px 1px #bf8e91;
	}
	.date {
		text-shadow: 2px 1px 1px #fff;
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

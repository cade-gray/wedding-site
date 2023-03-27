<!-- Landing Page -->
<div class="storyContainer">
	<h2>Our Story</h2>
	<p>
		Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
		labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
		laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in
		voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat
		non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
	</p>
</div>
<div class="navContainer">
	<!-- TODO: Determine if links should be clicked from text or the whole region -->

	<a href="/rsvp" class="intPageLink">RSVP</a>
	<div class="registriesContainer">
		<a href="" class="registryLink">Registry (Williams Sonoma)</a>
		<a href="" class="registryLink">Registry (Amazon)</a>
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
		background: #d2cfc6;
		box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
		border-radius: 5px;
		display: flex;
		flex-direction: column;
		align-items: center;
		color: #222;
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

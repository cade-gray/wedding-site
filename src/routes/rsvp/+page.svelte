<!-- RSVP Page -->
<script>
	import { srcString } from '../../lib/iframeSrc';
</script>

<div class="rsvpContainer">
	<iframe
		title="rsvp"
		src={srcString}
		width="350"
		class="rsvpForm"
		frameborder="0"
		marginheight="0"
		marginwidth="0">Loading…</iframe
	>
	<a href="/" class="homeLink">Home</a>
</div>

<style>
	.rsvpContainer {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100%;
	}
	.homeLink {
		background: #bf8e91;
		font-size: 1.3rem;
		width: 75%;
		height: 50px;
		margin: 10px;
		padding: 10px;
		display: flex;
		align-items: center;
		justify-content: center;
		text-align: center;
		box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
		border-radius: 5px;
		text-decoration: none;
		color: #222;
	}
	.homeLink:hover {
		transform: scale(1.1);
		box-shadow: 0 0 10px 5px #806668;
	}
	.rsvpForm {
		height: 1590px;
	}
</style>

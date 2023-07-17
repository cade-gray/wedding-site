<!-- RSVP Page -->
<script>
	import { srcString } from '../../lib/iframeSrc';
	import HomeLink from '../../homeLink.svelte';
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
	<HomeLink />
</div>

<style>
	.rsvpContainer {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100%;
	}
	.rsvpForm {
		height: 1590px;
	}
</style>

<script>
	export const ssr = false;
</script>

<div class="container">
	<div>
		<a href="/">
			<h1>
				<span style="color: #6e9277;text-shadow: 1px 1px 2px #4f6455;">Cade</span> &amp;
				<span style="color: #bf8e91;text-shadow: 1px 1px 2px #806668;">Katie</span>
			</h1>
		</a>
	</div>
	<slot />
	<div>
		<h2>Footer</h2>
	</div>
</div>

<style>
	.container {
		background: #e4e2dd;
		display: flex;
		flex-direction: column;
		align-items: center;
		box-shadow: 0px 3px 4px 3px rgba(0, 0, 0, 0.25);
		border-radius: 5px;
		min-height: 93vh;
		margin: 30px;
	}
	a {
		text-decoration: none;
	}
	h1 {
		color: black;
	}
</style>

<script>
	import HomeLink from '../../homeLink.svelte';
	var submitted = false;
	var firstNameValue = '';
	var lastNameValue = '';
	var emailValue = '';
	var attendingYNValue = 'N';
	var dietRestValue = null;
	var p1YNValue = 'N';
	var p1NameValue = null;
	var childrenYNValue = null;
	var childCountValue = 0;
	function submitForm() {
		if (
			firstNameValue === '' ||
			lastNameValue === '' ||
			emailValue === '' ||
			childCountValue === '' ||
			isNaN(childCountValue) ||
			childCountValue < 0
		) {
			alert(
				'Please answer all the required questions (First Name, Last Name, Email and if you are attending then also plus one y/n, their name, children y/n, and count of children.).'
			);
		} else {
			// Submit the form or perform any other action here
			var formData = {
				firstName: firstNameValue,
				lastName: lastNameValue,
				email: emailValue,
				attendingYN: attendingYNValue,
				dietRest: dietRestValue,
				plusOneYN: p1YNValue,
				plusOneName: p1NameValue,
				childrenYN: childrenYNValue,
				childCount: childCountValue
			};

			// Do something with the formData object (e.g., send it to the server or process it further)
			const jsonData = JSON.stringify(formData);

			// Make a POST request using the fetch() function
			fetch('https://api.cadegray.dev/wedding/guest', {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json'
				},
				body: jsonData
			})
				.then((response) => response.json())
				.then((data) => {
					submitted = true;
				})
				.catch((error) => {
					// Handle any errors that occurred during the request
					alert(
						'There was an error submitting, please contact Cade and Katie and send them this error: ' +
							error
					);
				});
		}
		// Create an object to store the data
	}
</script>

<div>
	<div class="form">
		{#if submitted == false}
			<h1>RSVP</h1>
			<label for="first-name"><span class="required">*</span>First Name</label>
			<input type="text" name="first-name" id="first-name" bind:value={firstNameValue} required />
			<label for="last-name"><span class="required">*</span>Last Name</label>
			<input type="text" name="last-name" id="last-name" bind:value={lastNameValue} required />
			<label for="email"><span class="required">*</span>Email</label>
			<input type="email" name="email" id="email" bind:value={emailValue} required />
			<label for="attending"><span class="required">*</span>Will you be attending?</label>
			<div>
				<div>
					<input
						type="radio"
						name="attending"
						id="attending"
						value="N"
						bind:group={attendingYNValue}
						checked
					/>
					<label for="attending">No</label>
				</div>
				<div>
					<input
						type="radio"
						name="attending"
						id="attending"
						value="Y"
						bind:group={attendingYNValue}
					/>
					<label for="attending">Yes</label>
				</div>
			</div>
			{#if attendingYNValue == 'N'}
				<br />
				<button on:click={submitForm} class="submitButt">Submit</button>
			{:else}
				<label for="diet-rest">Any Dietary Restrictions?</label>
				<input type="text" name="diet-rest" id="diet-rest" bind:value={dietRestValue} />
				<label for="plus-one"><span class="required">*</span>Plus one?</label>
				<div>
					<div>
						<input
							type="radio"
							name="plus-one"
							id="plus-one"
							value="N"
							bind:group={p1YNValue}
							checked
						/>
						<label for="plus-one">No</label>
					</div>
					<div>
						<input type="radio" name="plus-one" id="plus-one" value="Y" bind:group={p1YNValue} />
						<label for="plus-one">Yes</label>
					</div>
				</div>
				<label for="p1-name">If plus one, their first and last name:</label>
				<input type="text" name="p1-name" id="p1-name" bind:value={p1NameValue} />
				<label for="children"><span class="required">*</span>Bringing Children?</label>
				<div>
					<div>
						<input
							type="radio"
							name="children"
							id="children"
							value="N"
							bind:group={childrenYNValue}
							checked
						/>
						<label for="children">No</label>
					</div>
					<div>
						<input
							type="radio"
							name="children"
							id="children"
							value="Y"
							bind:group={childrenYNValue}
						/>
						<label for="children">Yes</label>
					</div>
				</div>
				<label for="children"><span class="required">*</span>If bringing children, how many?</label>
				<input type="number" name="child-count" id="child-count" bind:value={childCountValue} />
				<br />
				<button on:click={submitForm} class="submitButt">Submit</button>
			{/if}
		{:else}
			{#if attendingYNValue === 'Y'}
				<h2 class="thanksText">
					Thank you for RSVPing {firstNameValue}! We look forward to seeing you on October 28th,
					2023! Please visit the FAQ page for additonal information
				</h2>
			{:else if attendingYNValue === 'N'}
				<h2 class="thanksText">
					Thank you for RSVPing {firstNameValue}! We wish you could make it but appreciate you
					taking the time to let us know.
				</h2>
			{/if}
			<HomeLink />
		{/if}
	</div>
</div>

<style>
	.form {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-between;
		background: #d2cfc6cf;
		margin: 1rem;
		padding: 1rem;
		border-radius: 5px;
		box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
		width: 40vw;
	}
	input {
		border-radius: 5px;
		width: auto;
		background: #bf8e917f;
		height: 1.3rem;
		border: solid 1.5px #222;
		margin-bottom: 5px;
		text-align: center;
	}
	#email {
		width: 60%;
	}
	#diet-rest {
		width: 40%;
	}
	#p1-name {
		width: 60%;
	}
	.submitButt {
		background: #6e9277;
		width: 60%;
		height: 50px;
		font-size: 1rem;
		box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
		border-radius: 5px;
		border: solid 1.5px #222;
		text-decoration: none;
	}
	.submitButt:hover {
		transform: scale(1.1);
	}
	.required {
		color: #5fbf77;
		font-size: 1.5rem;
	}
	.thanksText {
		text-align: center;
	}
	@media screen and (max-width: 800px) {
		.form {
			width: 75vw;
		}
	}
</style>

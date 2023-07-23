<script>
	import HomeLink from '../../homeLink.svelte';
	var submitted = false;
	var submitterFirstName = '';
	function submitForm() {
		// Get the input field values
		var firstNameValue = document.getElementById('first-name').value.trim();
		var lastNameValue = document.getElementById('last-name').value.trim();
		var emailValue = document.getElementById('email').value.trim();
		var dietRestValue = document.getElementById('diet-rest').value;
		var p1YNValue = document.getElementById('plus-one').value;
		var p1NameValue = document.getElementById('p1-name').value;
		var childrenYNValue = document.getElementById('children').value;
		var childCountValue = document.getElementById('child-count').value;

		if (
			firstNameValue === '' ||
			lastNameValue === '' ||
			emailValue === '' ||
			childCountValue === '' ||
			isNaN(childCountValue) ||
			childCountValue < 0
		) {
			alert(
				'Please fill in all the required fields (First Name, Last Name, Email, and amount of children attending).'
			);
		} else {
			// Submit the form or perform any other action here
			var formData = {
				firstName: firstNameValue,
				lastName: lastNameValue,
				email: emailValue,
				dietRest: dietRestValue,
				plusOneYN: p1YNValue,
				plusOneName: p1NameValue,
				childrenYN: childrenYNValue,
				childCount: childCountValue
			};

			// Do something with the formData object (e.g., send it to the server or process it further)
			const jsonData = JSON.stringify(formData);

			// Make a POST request using the fetch() function
			fetch('https://api.cadegray.dev/wedding', {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json'
				},
				body: jsonData
			})
				.then((response) => response.json())
				.then((data) => {
					submitted = true;
					submitterFirstName = formData.firstName;
				})
				.catch((error) => {
					// Handle any errors that occurred during the request
					alert('There was an error submitting, please contact Cade and Katie.');
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
			<input type="text" name="first-name" id="first-name" required />
			<label for="last-name"><span class="required">*</span>Last Name</label>
			<input type="text" name="last-name" id="last-name" required />
			<label for="email"><span class="required">*</span>Email</label>
			<input type="email" name="email" id="email" required />
			<label for="diet-rest">Any Dietary Restrictions?</label>
			<input type="text" name="diet-rest" id="diet-rest" />
			<label for="plus-one"><span class="required">*</span>Plus one?</label>
			<div>
				<div>
					<input type="radio" name="plus-one" id="plus-one" value="Y" checked />
					<label for="plus-one">Yes</label>
				</div>
				<div>
					<input type="radio" name="plus-one" id="plus-one" value="N" />
					<label for="plus-one">No</label>
				</div>
			</div>
			<label for="p1-name">If plus one, their first and last name:</label>
			<input type="text" name="p1-name" id="p1-name" />
			<label for="children"><span class="required">*</span>Bringing Children?</label>
			<div>
				<div>
					<input type="radio" name="children" id="children" value="N" checked />
					<label for="children">No</label>
				</div>
				<div>
					<input type="radio" name="children" id="children" value="Y" />
					<label for="children">Yes</label>
				</div>
			</div>
			<label for="children"><span class="required">*</span>If bringing children, how many?</label>
			<input type="number" name="child-count" id="child-count" value="0" />
			<br />
			<button on:click={submitForm} class="submitButt">Submit</button>
		{:else}
			<h2 class="thanksText">
				Thank you for RSVPing {submitterFirstName}! We look forward to seeing you on October 28th,
				2023! Please visit the FAQ page for additonal information
			</h2>
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
	}
	input {
		border-radius: 5px;
		width: auto;
		background: #bf8e917f;
		height: 1.3rem;
		border: solid 1.5px #222;
		margin-bottom: 5px;
	}
	#email {
		width: 80%;
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
</style>

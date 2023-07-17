<!-- FAQ Page -->
<script>
	import HomeLink from '../../homeLink.svelte';
</script>

<div class="faqContainer">
	<h1>FAQs</h1>
	<ol>
		<li><h3>What time should we arrive?</h3></li>
		<ul>
			<li>
				We suggest arriving to the venue at least 20 minutes before the ceremony starts to give you
				time to park and find a seat. The ceremony will be starting at 4:30pm so plan on arriving at
				4:10 at the latest.
			</li>
		</ul>
		<li><h3>Where should we stay?</h3></li>
		<ul>
			<li>
				<h4>
					There are many lodging options in the area. The closest (within 10 minutes of venue) are
				</h4>
			</li>
			<ul>
				<li>Fairfield Inn (130 Tanner Ln, Clinton, TN 37716)</li>
				<li>Holiday Inn Express (111 Hillvale Rd, Clinton, TN 37716)</li>
				<li>Hampton Inn (105 Hillvale Rd, Clinton, TN 37716)</li>
			</ul>
			<li>
				<h4>
					We are about 30 minutes from downtown Knoxville if you would prefer stay there, here are a
					few great places to stay:
				</h4>
			</li>
			<ul>
				<li>Marriott Knoxville Downtown (525 Henley St, Knoxville, TN 37902)</li>
				<li>The Tennessean Hotel (531 Henley St, Knoxville, TN 37902)</li>
			</ul>
			<li>
				We suggest mapping out how far the venue is from your choice of lodging so you know how far
				it will be.
			</li>
		</ul>
		<li><h3>What is the dress code? Indoor/Outdoor?</h3></li>
		<ul>
			<li>
				The dress code is semi-formal/formal (please no jeans). We will be outside for both the
				ceremony and reception so make sure to check the weather and plan accordingly.
			</li>
		</ul>
		<li><h3>Can I bring a plus one?</h3></li>
		<ul>
			<li>
				If you would like to bring a plus one that was not specifically addressed on your invitation
				please reach out to us. We have a limited number of guests available.
			</li>
		</ul>
		<li><h3>When is the RSVP deadline?</h3></li>
		<ul>
			<li>The RSVP deadline is September 30th, 2023.</li>
		</ul>
		<li><h3>What should I do if I recieved an invite but cannot attend?</h3></li>
		<ul>
			<li>If you cannot attend please RSVP accordingly prior to the deadline.</li>
		</ul>
		<li><h3>Where are you registered?</h3></li>
		<ul>
			<li>
				We are registered at <a
					href="https://www.williams-sonoma.com/registry/qvtdq7xv89/registry-list.html"
					target="_blank">Williams Sonoma</a
				>
				and
				<a
					href="https://www.amazon.com/wedding/katie-oakes-cade-gray--october-2023/registry/1EFU39WJ0ZUB5"
					target="_blank">Amazon</a
				>.
			</li>
		</ul>
		<li><h3>What food and drinks will be served?</h3></li>
		<ul>
			<li>
				We will be serving beer and wine only (no liquor, please do not bring your own). We will
				have several appetizer options, along with barbecue and various sides for dinner. If you
				have any dietary preferences or restrictions please include that in your RSVP so we make
				sure we have the right meal for you!
			</li>
		</ul>
		<li><h3>Is there anything else we should know?</h3></li>
		<ul>
			<li>If you are flying in we recommend flying into Knoxville’s McGhee Tyson Airport.</li>
			<br />
			<li>
				If you are looking for things to do in the area check out Downtown Knoxville, or even the
				Smoky Mountains! There are many fun things to do, please reach out to us if you need any
				recommendations for activities!
			</li>
			<br />
			<li>
				We would like to note that our venue is a smoke and vape free property. We ask that you
				kindly respect these rules and the people that own and maintain the beautiful venue that we
				are lucky to be getting married at and celebrate with all of you! If you have any other
				questions please feel free to reach out to us.
			</li>
			<br />
		</ul>
	</ol>
	<div class="hlContainer">
		<HomeLink />
	</div>
</div>

<style>
	.faqContainer {
		text-align: center;
		padding-left: 2em;
		padding-right: 2em;
		background: #d2cfc6cf;
		margin: 2rem;
		box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
		border-radius: 5px;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	ol,
	li,
	ul {
		list-style-type: none;
		padding-inline-start: 0px;
	}
	.hlContainer {
		width: 25%;
	}
	@media screen and (max-width: 800px) {
		.hlContainer {
			width: 100%;
		}
	}
</style>

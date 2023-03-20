<script>
	let clicked = false;
</script>

<div>
	<button class="btn btn-primary" on:click={() => (clicked = true)}>
		click here
	</button>
	<!--  -->
	{#if clicked == true}
		<p> You have clicked the button!</p>
	{:else}
		<p> You have to click the button! </p>
	{/if}
</div>

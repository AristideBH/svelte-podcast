<script>
	let password = 'Noise_1414';

	const hash = (s) =>
		s.split('').reduce((a, b) => {
			a = (a << 5) - a + b.charCodeAt(0);
			return a & a;
		}, 0);

	// $: console.log(password, hash(password))
</script>

{#if hash(password) === -931144277}
	<div class="container">
		<slot />
	</div>
{:else}
	<div>
		<label for="password">Password:</label>
		<input id="password" bind:value={password} type="password" />
	</div>
{/if}

<style>
	input[type='password'] {
		width: 200px;
	}
	.container {
		max-width: max(960px, 70%);
		margin: 2rem auto 1rem;
		padding: 0 1rem;
	}
</style>

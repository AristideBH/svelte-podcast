<script>
	import { podcasts } from '$lib/data/podcasts.json';
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

{#each podcasts as podcast}
	<a href="./{podcast.id}">
		<article data-color={podcast.color}>
			<h1>{@html podcast.title}</h1>
			<p>{podcast.subtitle}</p>

			<div class="content">
				{@html podcast.content}
			</div>
		</article>
	</a>
{/each}

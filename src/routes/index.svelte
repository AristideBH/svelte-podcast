<script>
	import { podcasts } from '$lib/data/podcasts.json';
</script>

<h1>Podcasts</h1>


{#each podcasts as podcast}
<hr>
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

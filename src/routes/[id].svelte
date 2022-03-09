<script context="module">
	import { podcasts } from '$lib/data/podcasts';

	export async function load({ params }) {
		const id = Number(params.id);
		const podcast = podcasts[Number(id) - 1];
		return { props: { podcast } };
	}
</script>

<script>
	export let podcast;
</script>

<!-- {JSON.stringify(podcast)} -->

<svelte:head>
	<title>{podcast.title}</title>
</svelte:head>

<h1>{@html podcast.title}</h1>

<p>{podcast.subtitle}</p>

<img src={podcast.hero} alt="" />

<audio controls src={podcast.audio} />

<div class="content">
	{@html podcast.content}
</div>

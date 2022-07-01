<script context="module">

	export async function load({fetch}){
		const res = await fetch(`https://api.themoviedb.org/3/movie/popular?api_key=${'4a9e8653983f47a54e84e4ee04339ebb'}&language=en-US&page=1`);

		const data =  await res.json();

		
		if (res.ok) {
			return { props:{popular: data} };
		}
		
	}
	
</script>
<script>
// @ts-nocheck

	import PopularMovies from '../lib/PopularMovies.svelte';
	import SearchMovie from '$lib/SearchMovie.svelte';
	export let popular;
	

</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section class="my-5">
	<SearchMovie />
	<PopularMovies movies={popular} />
</section>

<style>
	
</style>

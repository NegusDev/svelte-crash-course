<script context="module">

	export async function load({fetch, params}){
        console.log(params);
		const res = await fetch(
            `https://api.themoviedb.org/3/search/movie?api_key=4a9e8653983f47a54e84e4ee04339ebb&language=en-US&query=${params.search}&include_adult=true`
            );

		const data =  await res.json();
    
		if (res.ok) {
			return { props: {searchMovie: data.results} };
		}
		
	}
</script>
<script>
    import MovieCard from "$lib/MovieCard.svelte";
    export let searchMovie;
    console.log(searchMovie);
</script>

<div class="container">
    <div class="row">
        {#each searchMovie as film}
            <MovieCard {film} /> 
        {/each}
    </div>
</div>

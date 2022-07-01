<script>
    export let movies;
    const films = movies.results;
    import MovieCard from "./MovieCard.svelte"; 

</script>
<h3 class="text-center">Popular Movies</h3>

<div class="container">
    <div class="row">
        {#each films as film}
            <MovieCard {film} /> 
        {/each}
    </div>

</div>
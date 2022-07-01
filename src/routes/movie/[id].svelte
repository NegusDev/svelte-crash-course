<script context="module">

	export async function load({fetch, params}){
		const res = await fetch(`https://api.themoviedb.org/3/movie/${params.id}?api_key=4a9e8653983f47a54e84e4ee04339ebb&language=en-US`);

		const movieDetail =  await res.json();
    
		if (res.ok) {
			return { props: {movieDetail} };
		}
		
	}
	
</script>
<script>
    export let movieDetail;
    const genres = movieDetail.genres;
    
</script>

<div class="container py-5 my-5">
    <div class="row justify-content-center">
        <div class="col-8">
            <div class="img-box">
                <img src="{'https://image.tmdb.org/t/p/original'+movieDetail.backdrop_path}" alt="" class="img-fluid">
            </div>
            <div class="text-box">
                <p class="genre">
                {#each genres as genre}
                    <span>{genre.name}&nbsp;</span>
                {/each}
                 </p>
                <h2>{movieDetail.original_title}</h2>
                <h5>Overview</h5>
                <p>{movieDetail.overview}</p>
                <p>
                    <span><strong>Release Date</strong></span> {movieDetail.release_date}<br> 
                    <span><strong>Budget</strong></span> {movieDetail.budget}<br> 
                    <span><strong>Rating</strong></span> {movieDetail.vote_average}<br> 
                    <span><strong>Runtime</strong></span> {movieDetail.runtime}mins<br> 
                
                </p> 
            </div>
              
        </div>
    </div>
</div>

<style>
    .genre > span:nth-child(1) {

        content: "\002C" !important;
    }
</style>
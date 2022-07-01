<script>
    // @ts-ignore
    export let film;
</script>

<div class="col-md-3 shadow p-3 my-2 mx-auto ">
    <a href={'/movie/'+film.id+'-'+film.title}>
        <img src={'https://image.tmdb.org/t/p/w500'+film.poster_path} alt="" class="img-fluid">
    </a>
    <h4>{film.title}</h4>
    <p >{film.release_date}</p>
</div>
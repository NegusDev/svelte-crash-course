<script>
    import {goto} from '$app/navigation';
    let inputValue = '';

    function submitSearch() {
        goto('/search/'+inputValue);
    }
</script>
<form on:submit|preventDefault={submitSearch} action="" class="mt-5 w-50  container">
    <div class="input-group">
        <input bind:value={inputValue} type="text" name="search_movie" class="form-control" >
        <button class="btn btn-dark">Search</button>
    </div>
    
</form>

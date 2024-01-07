<script>
import Movie from "./Movie.svelte";

  let value = "";
  let response = [];
  let loading = false;
  const handleInput = (event) => (value = event.target.value);

  $: if (value.length > 2) {
    loading = true;
    fetch(`https://www.omdbapi.com/?s=${value}&apikey=af77700`)
      .then((res) => res.json())
      .then((apiResponse) => {
        response = apiResponse.Search || [];
        loading = false;
        console.log(apiResponse);
      });
  }
</script>

<input
  type="text"
  placeholder="Search movies..."
  {value}
  on:input={handleInput}
/>
{#if loading}
  <strong>Loading...</strong>
{:else }
    {#each response as {Title: movieTitle, Poster, Year}, index}
        <Movie 
            index={index}
            title={movieTitle}
            poster={Poster}
            year={Year}
            />
    {:else}
        <strong>No hay resultados.</strong>
  {/each}
{/if}

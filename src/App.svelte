<script>
  import { onMount } from "svelte";
  const api = "https://coronavirus-19-api.herokuapp.com/all";
  let data = {};
  onMount(async () => {
    let rezultati = await fetch(api);
    data = await rezultati.json();
  });
</script>

<style>
</style>

<main>
  <div class="text-center">
    <h1 class="my-4">Covid19 Tracker</h1>
  </div>

  <div class="container">
    <h2 class="mt-4">Statistics</h2>
    <p>
      Number of total cases:
    </p>
    <div class="row">
      <div class="col-12 col-lg-4 mb-2">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <p class="mb-0 lead">Cases</p>
            {#if data.cases == undefined}
              <h1 class="mb-0">Loading...</h1>
            {:else}
              <h1 class="mb-0">{data.cases}</h1>
            {/if}
          </div>
        </div>
        <hr>
      </div>
      <div class="col-12 col-lg-4 mb-2">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <p class="mb-0 lead">Recovered</p>
            {#if data.recovered == undefined}
              <h1 class="mb-0">Loading</h1>
            {:else}
              <h1 class="mb-0 text-success">{data.recovered}</h1>
            {/if}
          </div>
        </div>
        <hr>
      </div>
      <div class="col-12 col-lg-4">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <p class="mb-0 lead">Death</p>
            {#if data.deaths == undefined}
              <h1 class="mb-0">Loading</h1>
            {:else}
              <h1 class="mb-0 text-danger">{data.deaths}</h1>
            {/if}
          </div>
        </div>
        <hr>
      </div>
</main>
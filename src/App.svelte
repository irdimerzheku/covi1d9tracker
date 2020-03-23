<script>
  import { onMount } from "svelte";
  const api = "https://coronavirus-19-api.herokuapp.com/countries/albania";
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
    <img
      src="https://cdn.countryflags.com/thumbs/albania/flag-button-round-250.png"
      alt="Flamuri Shqiptar"
      class="mt-4"
      style="width: 75px" />
    <h1 class="my-4">Koronavirus në Shqipëri</h1>
    <a href="tel:127" class="btn btn-outline-danger">Telefono Urgjencën</a>
  </div>

  <div class="container">
    <h2 class="mt-4">Statistika</h2>
    <p>
      Numrat e përgjithshëm të ndikimit që COVID-19 ka patur në Shqipëri deri
      tani.
    </p>
    <div class="row">
      <div class="col-12 col-lg-4 mb-2">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <p class="mb-0 lead">Raste</p>
            {#if data.cases == undefined}
              <h1 class="mb-0">Në ngarkim...</h1>
            {:else}
              <h1 class="mb-0">{data.cases}</h1>
            {/if}
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-4 mb-2">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <p class="mb-0 lead">Shëruar</p>
            {#if data.recovered == undefined}
              <h1 class="mb-0">Në ngarkim...</h1>
            {:else}
              <h1 class="mb-0 text-success">{data.recovered}</h1>
            {/if}
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-4">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <p class="mb-0 lead">Vdekje</p>
            {#if data.deaths == undefined}
              <h1 class="mb-0">Në ngarkim...</h1>
            {:else}
              <h1 class="mb-0 text-danger">{data.deaths}</h1>
            {/if}
          </div>
        </div>
      </div>
    </div>
    <h2 class="mt-4">Sot</h2>
    <p>Shifrat e fundit të ditës së sotme.</p>
    <div class="row">
      <div class="col">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <p class="mb-0 lead">Raste</p>
            {#if data.todayCases == undefined}
              <h1 class="mb-0">Në ngarkim...</h1>
            {:else}
              <h1 class="mb-0">{data.todayCases}</h1>
            {/if}
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <p class="mb-0 lead">Vdekje</p>
            {#if data.todayDeaths == undefined}
              <h1 class="mb-0">Në ngarkim...</h1>
            {:else if data.todayDeaths > 0}
              <h1 class="mb-0 text-danger">{data.todayDeaths}</h1>
            {:else}
              <h1 class="mb-0">{data.todayDeaths}</h1>
            {/if}
          </div>
        </div>
      </div>
    </div>
    <h2 class="mt-4">Të Tjera</h2>
    <p>Statistika të tjera nga rastet në Shqipëri.</p>
    <div class="row">
      <div class="col-12 col-lg-4 mb-2">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <p class="lead mb-0">Aktive</p>
            <h1 class="mb-0">{data.active}</h1>
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-4 mb-2">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <p class="lead mb-0">Kritike</p>
            <h1 class="mb-0">{data.critical}</h1>
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-4">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <p class="lead mb-0">Raste/Milion</p>
            <h1 class="mb-0">{data.casesPerOneMillion}</h1>
          </div>
        </div>
      </div>
    </div>
  </div>
</main>
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
    <h1 class="my-4">Covid19</h1>
  </div>

  <div class="container">
    <h2 class="mt-4">Statistics</h2>
    <p>
      General number of cases
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
      <hr> 
<div class="container card shadow-sm " id="mapdiv" style="width: 1135px; height: 465px;"></div>
<div style="width: 1000px; font-size: 70%; padding: 5px 0; text-align: center; background-color: #FFFFFF; margin-top: 1px; color: #B3B4B5;"><a href="https://www.amcharts.com/visited_countries/" style="color: #B3B4B5;">Create your own visited countries map</a> or check out the <a href="https://www.amcharts.com/" style="color: #B3B4B5;">JavaScript Charts</a>.</div>
<script type="text/javascript">
var map = AmCharts.makeChart("mapdiv",{
type: "map",
theme: "dark",
projection: "mercator",
panEventsEnabled : true,
backgroundColor : "#FFFFFF",
backgroundAlpha : 1,
zoomControl: {
zoomControlEnabled : true
},
dataProvider : {
map : "worldHigh",
getAreasFromMap : true,
areas :
[
	{
		"id": "AL",
		"showAsSelected": true
	},
	{
		"id": "AM",
		"showAsSelected": true
	},
	{
		"id": "AT",
		"showAsSelected": true
	},
	{
		"id": "AZ",
		"showAsSelected": true
	},
	{
		"id": "BY",
		"showAsSelected": true
	},
	{
		"id": "BE",
		"showAsSelected": true
	},
	{
		"id": "BA",
		"showAsSelected": true
	},
	{
		"id": "BG",
		"showAsSelected": true
	},
	{
		"id": "HR",
		"showAsSelected": true
	},
	{
		"id": "CZ",
		"showAsSelected": true
	},
	{
		"id": "DK",
		"showAsSelected": true
	},
	{
		"id": "EE",
		"showAsSelected": true
	},
	{
		"id": "FI",
		"showAsSelected": true
	},
	{
		"id": "FR",
		"showAsSelected": true
	},
	{
		"id": "GE",
		"showAsSelected": true
	},
	{
		"id": "DE",
		"showAsSelected": true
	},
	{
		"id": "GR",
		"showAsSelected": true
	},
	{
		"id": "HU",
		"showAsSelected": true
	},
	{
		"id": "IS",
		"showAsSelected": true
	},
	{
		"id": "IE",
		"showAsSelected": true
	},
	{
		"id": "IT",
		"showAsSelected": true
	},
	{
		"id": "XK",
		"showAsSelected": true
	},
	{
		"id": "LV",
		"showAsSelected": true
	},
	{
		"id": "LT",
		"showAsSelected": true
	},
	{
		"id": "MK",
		"showAsSelected": true
	},
	{
		"id": "MD",
		"showAsSelected": true
	},
	{
		"id": "ME",
		"showAsSelected": true
	},
	{
		"id": "NL",
		"showAsSelected": true
	},
	{
		"id": "NO",
		"showAsSelected": true
	},
	{
		"id": "PL",
		"showAsSelected": true
	},
	{
		"id": "PT",
		"showAsSelected": true
	},
	{
		"id": "RO",
		"showAsSelected": true
	},
	{
		"id": "RU",
		"showAsSelected": true
	},
	{
		"id": "RS",
		"showAsSelected": true
	},
	{
		"id": "SK",
		"showAsSelected": true
	},
	{
		"id": "SI",
		"showAsSelected": true
	},
	{
		"id": "ES",
		"showAsSelected": true
	},
	{
		"id": "SE",
		"showAsSelected": true
	},
	{
		"id": "CH",
		"showAsSelected": true
	},
	{
		"id": "TR",
		"showAsSelected": true
	},
	{
		"id": "UA",
		"showAsSelected": true
	},
	{
		"id": "GB",
		"showAsSelected": true
	},
	{
		"id": "CA",
		"showAsSelected": true
	},
	{
		"id": "CR",
		"showAsSelected": true
	},
	{
		"id": "CU",
		"showAsSelected": true
	},
	{
		"id": "DO",
		"showAsSelected": true
	},
	{
		"id": "SV",
		"showAsSelected": true
	},
	{
		"id": "GT",
		"showAsSelected": true
	},
	{
		"id": "HT",
		"showAsSelected": true
	},
	{
		"id": "HN",
		"showAsSelected": true
	},
	{
		"id": "MX",
		"showAsSelected": true
	},
	{
		"id": "NI",
		"showAsSelected": true
	},
	{
		"id": "PA",
		"showAsSelected": true
	},
	{
		"id": "PR",
		"showAsSelected": true
	},
	{
		"id": "US",
		"showAsSelected": true
	},
	{
		"id": "AR",
		"showAsSelected": true
	},
	{
		"id": "BO",
		"showAsSelected": true
	},
	{
		"id": "BR",
		"showAsSelected": true
	},
	{
		"id": "CL",
		"showAsSelected": true
	},
	{
		"id": "CO",
		"showAsSelected": true
	},
	{
		"id": "EC",
		"showAsSelected": true
	},
	{
		"id": "GF",
		"showAsSelected": true
	},
	{
		"id": "GY",
		"showAsSelected": true
	},
	{
		"id": "PY",
		"showAsSelected": true
	},
	{
		"id": "PE",
		"showAsSelected": true
	},
	{
		"id": "SR",
		"showAsSelected": true
	},
	{
		"id": "UY",
		"showAsSelected": true
	},
	{
		"id": "VE",
		"showAsSelected": true
	},
	{
		"id": "DZ",
		"showAsSelected": true
	},
	{
		"id": "AO",
		"showAsSelected": true
	},
	{
		"id": "BW",
		"showAsSelected": true
	},
	{
		"id": "TD",
		"showAsSelected": true
	},
	{
		"id": "CD",
		"showAsSelected": true
	},
	{
		"id": "EG",
		"showAsSelected": true
	},
	{
		"id": "ET",
		"showAsSelected": true
	},
	{
		"id": "KE",
		"showAsSelected": true
	},
	{
		"id": "LY",
		"showAsSelected": true
	},
	{
		"id": "MG",
		"showAsSelected": true
	},
	{
		"id": "ML",
		"showAsSelected": true
	},
	{
		"id": "MR",
		"showAsSelected": true
	},
	{
		"id": "MA",
		"showAsSelected": true
	},
	{
		"id": "NA",
		"showAsSelected": true
	},
	{
		"id": "NE",
		"showAsSelected": true
	},
	{
		"id": "NG",
		"showAsSelected": true
	},
	{
		"id": "SO",
		"showAsSelected": true
	},
	{
		"id": "ZA",
		"showAsSelected": true
	},
	{
		"id": "SD",
		"showAsSelected": true
	},
	{
		"id": "TZ",
		"showAsSelected": true
	},
	{
		"id": "TN",
		"showAsSelected": true
	},
	{
		"id": "EH",
		"showAsSelected": true
	},
	{
		"id": "ZW",
		"showAsSelected": true
	},
	{
		"id": "AF",
		"showAsSelected": true
	},
	{
		"id": "BD",
		"showAsSelected": true
	},
	{
		"id": "BT",
		"showAsSelected": true
	},
	{
		"id": "KH",
		"showAsSelected": true
	},
	{
		"id": "CN",
		"showAsSelected": true
	},
	{
		"id": "HK",
		"showAsSelected": true
	},
	{
		"id": "IN",
		"showAsSelected": true
	},
	{
		"id": "ID",
		"showAsSelected": true
	},
	{
		"id": "IR",
		"showAsSelected": true
	},
	{
		"id": "IQ",
		"showAsSelected": true
	},
	{
		"id": "JP",
		"showAsSelected": true
	},
	{
		"id": "JO",
		"showAsSelected": true
	},
	{
		"id": "KZ",
		"showAsSelected": true
	},
	{
		"id": "KW",
		"showAsSelected": true
	},
	{
		"id": "KG",
		"showAsSelected": true
	},
	{
		"id": "LA",
		"showAsSelected": true
	},
	{
		"id": "MY",
		"showAsSelected": true
	},
	{
		"id": "MN",
		"showAsSelected": true
	},
	{
		"id": "MM",
		"showAsSelected": true
	},
	{
		"id": "NP",
		"showAsSelected": true
	},
	{
		"id": "KP",
		"showAsSelected": true
	},
	{
		"id": "OM",
		"showAsSelected": true
	},
	{
		"id": "PK",
		"showAsSelected": true
	},
	{
		"id": "PH",
		"showAsSelected": true
	},
	{
		"id": "QA",
		"showAsSelected": true
	},
	{
		"id": "SA",
		"showAsSelected": true
	},
	{
		"id": "KR",
		"showAsSelected": true
	},
	{
		"id": "SY",
		"showAsSelected": true
	},
	{
		"id": "TJ",
		"showAsSelected": true
	},
	{
		"id": "TH",
		"showAsSelected": true
	},
	{
		"id": "TM",
		"showAsSelected": true
	},
	{
		"id": "AE",
		"showAsSelected": true
	},
	{
		"id": "UZ",
		"showAsSelected": true
	},
	{
		"id": "VN",
		"showAsSelected": true
	},
	{
		"id": "YE",
		"showAsSelected": true
	},
	{
		"id": "AU",
		"showAsSelected": true
	},
	{
		"id": "PG",
		"showAsSelected": true
	}
]
},
areasSettings : {
autoZoom : true,
color : "#B3B4B5",
colorSolid : "#FF0000",
selectedColor : "#FF0000",
outlineColor : "#666666",
rollOverColor : "#006AFF",
rollOverOutlineColor : "#000000"
}
});
</script>

    </div>

<div class="container">
</div>

</main>
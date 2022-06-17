<script>
  import { onMount } from "svelte";
  import Card from "./components/Card.svelte";

  let results = [];

  onMount(() => {
    const options = {
      method: "GET",
      headers: {
        "X-RapidAPI-Key": "25a916eea1mshc663c709757d1f9p19f877jsnada2ece8fc1b",
        "X-RapidAPI-Host": "rawg-video-games-database.p.rapidapi.com",
      },
    };

    fetch(
      "https://rawg-video-games-database.p.rapidapi.com/games?key=2e13e80be7204f9ea9d6ea08bc058a68",
      options
    )
      .then((response) => response.json())
      .then((response) => {
        results = response.results;
        console.log(results);
      })
      .catch((err) => console.error(err));
  });
</script>

<main>
  {#if results[0]}
    <Card games={results} />
  {/if}
</main>

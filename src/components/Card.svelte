<script>
  export let games = [];
</script>

<div class="games">
  {#each games as game (game.id)}
    <div class="card">
      <img src={game.background_image} alt="" />
      <p>{game.name}</p>
      <p class="rating">{game.rating}</p>
    </div>
  {/each}
</div>

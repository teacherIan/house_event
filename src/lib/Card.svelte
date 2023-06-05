<script lang="ts">
  export let img: string;
  export let house: string;
  let score = parseInt((window.localStorage.getItem(house) || 0).toString());

  function add() {
    score += 1;
    window.localStorage.setItem(house, score.toString());
  }

  function minus() {
    score -= 1;
    window.localStorage.setItem(house, score.toString());
  }
</script>

<div class="house-container">
  <button class="btn add" on:click={add}>+</button>
  <div class="img-container">
    <img src={img} alt="" />
    <div class="score">{score}</div>
  </div>

  <button class="btn minus" on:click={minus}>-</button>
</div>

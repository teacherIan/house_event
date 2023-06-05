<script lang="ts">
  // import svelteLogo from './assets/svelte.svg'
  import amber from './assets/amber.jpeg';
  import ruby from './assets/ruby.jpeg';
  import sapphire from './assets/sapphire.jpeg';
  import pearl from './assets/pearl.jpeg';
  import Card from './lib/Card.svelte';
  import Pixi from './lib/Pixi.svelte';
</script>

<div class="container">
  <Pixi />
  <Card img={amber} house="amber" />
  <Card img={ruby} house="ruby" />
  <Card img={sapphire} house="sapphire" />
  <Card img={pearl} house="pearl" />
</div>

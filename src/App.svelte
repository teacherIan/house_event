<script lang="ts">
  // import svelteLogo from './assets/svelte.svg'
  import amber from './assets/amber.jpeg';
  import ruby from './assets/ruby.jpeg';
  import sapphire from './assets/sapphire.jpeg';
  import pearl from './assets/pearl.jpeg';
  import Card from './lib/Card.svelte';
  import Pixi from './lib/Pixi.svelte';

  if (window.localStorage.getItem('amber') === null) {
    window.localStorage.setItem('amber', '0');
  }

  if (window.localStorage.getItem('ruby') === null) {
    window.localStorage.setItem('ruby', '0');
  }

  if (window.localStorage.getItem('sapphire') === null) {
    window.localStorage.setItem('sapphire', '0');
  }

  if (window.localStorage.getItem('pearl') === null) {
    window.localStorage.setItem('pearl', '0');
  }
</script>

<div class="container">
  <Card img={amber} house="amber" />
  <Card img={ruby} house="ruby" />
  <Card img={sapphire} house="sapphire" />
  <Card img={pearl} house="pearl" />
  <Pixi />
</div>

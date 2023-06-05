<script lang="ts">
  import * as PIXI from 'pixi.js';
  import img from '../assets/Sabres_Image_BW.png';
  import { gsap } from 'gsap';
  import { PixiPlugin } from 'gsap/PixiPlugin';
  let winningHouseName: string = '';

  gsap.registerPlugin(PixiPlugin);
  PixiPlugin.registerPIXI(PIXI);

  const app = new PIXI.Application({
    width: window.innerWidth,
    height: window.innerHeight,
    antialias: true,
    backgroundAlpha: 0,
  });

  document.body.appendChild(app.view as HTMLCanvasElement);
  const container = new PIXI.Container();
  app.stage.addChild(container);

  let sprite: PIXI.Sprite;

  async function downloadAsset() {
    const asset = await PIXI.Assets.load(img);
    sprite = PIXI.Sprite.from(asset);
    sprite.anchor.set(0.5);
    sprite.x = app.screen.width / 2;
    sprite.y = app.screen.height / 2;
    sprite.width = window.innerWidth;
    sprite.height = window.innerHeight;
    // sprite.alpha = 0.5;
    container.addChild(sprite);

    const scores = [
      parseInt(window.localStorage.getItem('amber').toString()),
      parseInt(window.localStorage.getItem('ruby').toString()),
      parseInt(window.localStorage.getItem('sapphire').toString()),
      parseInt(window.localStorage.getItem('pearl').toString()),
    ];
    const highScore = Math.max(...scores);

    const house = ['amber', 'ruby', 'sapphire', 'pearl'];

    const highScoreIndex = scores.indexOf(highScore);
    const highScoreHouse = house[highScoreIndex];

    if (highScoreHouse === 'amber' && winningHouseName !== 'amber') {
      winningHouseName = 'amber';
      gsap.to(sprite, { pixi: { tint: 0xe46725 }, duration: 5 });
    }
    if (highScoreHouse === 'ruby' && winningHouseName !== 'ruby') {
      winningHouseName = 'ruby';
      gsap.to(sprite, { pixi: { tint: 0x9e0b0f }, duration: 5 });
    }
    if (highScoreHouse === 'sapphire' && winningHouseName !== 'sapphire') {
      winningHouseName = 'sapphire';
      gsap.to(sprite, { pixi: { tint: 0x0f52ba }, duration: 5 });
    }

    if (highScoreHouse === 'pearl' && winningHouseName !== 'pearl') {
      winningHouseName = 'pearl';
      gsap.to(sprite, { pixi: { tint: 0x000000 }, duration: 5 });
    }
  }

  window.addEventListener('resize', () => {
    console.log('Resize');
    sprite.width = window.innerWidth;
    sprite.height = window.innerHeight;
    sprite.width = window.innerWidth;
    sprite.height = window.innerHeight;
  });

  downloadAsset().then(() => {
    document.addEventListener('click', () => {
      const scores = [
        parseInt(window.localStorage.getItem('amber').toString()),
        parseInt(window.localStorage.getItem('ruby').toString()),
        parseInt(window.localStorage.getItem('sapphire').toString()),
        parseInt(window.localStorage.getItem('pearl').toString()),
      ];
      const highScore = Math.max(...scores);

      const house = ['amber', 'ruby', 'sapphire', 'pearl'];

      const highScoreIndex = scores.indexOf(highScore);
      const highScoreHouse = house[highScoreIndex];

      if (highScoreHouse === 'amber' && winningHouseName !== 'amber') {
        winningHouseName = 'amber';
        gsap.to(sprite, { pixi: { tint: 0xe46725 }, duration: 5 });
      }
      if (highScoreHouse === 'ruby' && winningHouseName !== 'ruby') {
        winningHouseName = 'ruby';
        gsap.to(sprite, { pixi: { tint: 0x9e0b0f }, duration: 5 });
      }
      if (highScoreHouse === 'sapphire' && winningHouseName !== 'sapphire') {
        winningHouseName = 'sapphire';
        gsap.to(sprite, { pixi: { tint: 0x0f52ba }, duration: 5 });
      }

      if (highScoreHouse === 'pearl' && winningHouseName !== 'pearl') {
        winningHouseName = 'pearl';
        gsap.to(sprite, { pixi: { tint: 0x000000 }, duration: 5 });
      }
    });
  });
</script>

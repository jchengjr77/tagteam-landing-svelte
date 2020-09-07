<script>
  import colors from '../colors';

  // router imports
  import { links } from 'svelte-routing';

  // asset paths
  let lightLogoPath = 'assets/logo-light.svg';

  $: width;
  $: height;

  console.log(colors);
  console.log(width, height);
</script>

<style>
  .headerContainer {
    width: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
  }

  .linksContainer {
    min-width: 50%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: flex-end;
  }

  .mainLink {
    transition: 0.5s;
    margin-left: 5%;
    margin-right: 5%;
    color: #4d4d4d;
    font-size: large;
    font-weight: 300;
  }
  .mainLink:hover {
    transition: 0.5s;
    color: #ff3e00;
    text-decoration: none;
  }

  .logo {
    width: 25%;
    min-width: 200px;
  }
</style>

<svelte:window bind:innerWidth={width} bind:innerHeight={height} />

<div class="headerContainer">
  <img src={lightLogoPath} alt="tagteam-logo" class="logo" />
  <div class="linksContainer" use:links>
    <a href="/" class="mainLink" style="--hoverColor: {colors.brand}">Home</a>
    <a
      href="/features"
      class="mainLink"
      style="--hoverColor: {colors.brand}">Features</a>
    <a
      href="/"
      class="mainLink"
      style="--hoverColor: {colors.brand}">Community</a>
  </div>
</div>

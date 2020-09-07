<script>
  import colors from '../colors';

  // router imports
  import { links } from 'svelte-routing';

  // asset paths
  let lightLogoPath = 'assets/logo-light.svg';

  console.log(colors);
</script>

<style>
  h1 {
    color: var(--color);
    text-transform: uppercase;
    font-size: 6em;
    font-weight: 200;
    margin-block-start: 0;
    margin-block-end: 0;
  }

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
</style>

<div class="headerContainer">
  <img src={lightLogoPath} alt="tagteam-logo" />
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

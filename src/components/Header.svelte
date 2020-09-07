<script>
  import colors from '../colors';
  import { draw, fade } from 'svelte/transition';
  import { quintOut } from 'svelte/easing';

  // router imports
  import { links } from 'svelte-routing';

  // asset paths
  let lightLogo = 'assets/logo-light.svg';

  export let width = window.innerWidth;
  $: mobile = width < 700;
</script>

<style>
  .headerContainer {
    width: 100%;
    display: flex;
    flex-direction: var(--direction);
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

  .linksContainerMobile {
    min-width: 50%;
    padding-top: 5%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
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
    color: var(--hoverColor);
    text-decoration: none;
  }

  .logo {
    width: 25%;
    min-width: 200px;
  }
</style>

<svelte:window bind:innerWidth={width} />

<div class="headerContainer" style="--direction: {mobile ? 'column' : 'row'}">
  <img
    src={lightLogo}
    alt="logo"
    class="logo"
    in:fade={{ delay: 100, duration: 500 }} />
  <div class={mobile ? 'linksContainerMobile' : 'linksContainer'} use:links>
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

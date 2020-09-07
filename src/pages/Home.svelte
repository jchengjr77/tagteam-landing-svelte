<script>
  import colors from '../colors';
  import { fade, slide } from 'svelte/transition';
  import { text } from 'svelte/internal';

  export let width = window.innerWidth;
  $: mobile = width < 700;

  let art1Path = 'assets/business-travel.png';
  let art2Path = 'assets/business-login.png';

  let textVisible = false;
  let subtextVisible = false;
  let imageVisible = false;
  setTimeout(() => {
    console.log('ping');
    textVisible = true;
  }, 1000);
  setTimeout(() => {
    console.log('ping');
    subtextVisible = true;
  }, 1500);
  setTimeout(() => {
    console.log('ping');
    imageVisible = true;
  }, 2250);
</script>

<style>
  .h1Mobile {
    color: var(--color);
    text-transform: uppercase;
    font-size: 1.75em;
    font-weight: 100;
  }

  .h1 {
    color: var(--color);
    text-transform: uppercase;
    font-size: 3em;
    font-weight: 100;
  }

  .h2Mobile {
    font-size: 1.1em;
    font-weight: 300;
  }

  .h2 {
    font-size: 1.5em;
    font-weight: 300;
  }

  img {
    max-width: 100%;
    max-height: 100%;
  }

  .imageContainer {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
  }
</style>

<div>
  {#if textVisible}
    <h1
      class={mobile ? 'h1Mobile' : 'h1'}
      style="--color: {colors.accent2}"
      in:fade={{ duration: 500 }}>
      Presence-aware workspace for teams
    </h1>
    {#if subtextVisible}
      <h2 class={mobile ? 'h2Mobile' : 'h2'} in:fade={{ duration: 500 }}>
        Experience in-person workflows, remotely.
      </h2>
      <h2 class={mobile ? 'h2Mobile' : 'h2'} in:fade={{ duration: 500 }}>
        Connect and communicate with your team in one click.
      </h2>
    {/if}
  {/if}

  {#if imageVisible}
    <div class="imageContainer" in:fade={{ duration: 500 }}>
      {#if !mobile}
        <div><img src={art1Path} alt="art1" /></div>
      {/if}
      <div><img src={art2Path} alt="art2" /></div>
    </div>
  {/if}
</div>

<script>
  import colors from '../colors';

  export let width = window.innerWidth;
  $: mobile = width < 700;
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
</style>

<div>
  <h1 class={mobile ? 'h1Mobile' : 'h1'} style="--color: {colors.accent2}">
    Presence-aware workspace for teams
  </h1>
  <h2 class={mobile ? 'h2Mobile' : 'h2'}>
    Experience in-person workflows, remotely.
  </h2>
  <h2 class={mobile ? 'h2Mobile' : 'h2'}>
    Connect and communicate with your team in one click.
  </h2>
</div>

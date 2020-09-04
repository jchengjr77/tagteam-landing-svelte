<script>
  import colors from '../colors';
  console.log(colors);
</script>

<style>
  h1 {
    color: var(--color);
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
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
    margin-left: 5%;
    margin-right: 5%;
    color: #4d4d4d;
    font-size: large;
    font-weight: 300;
  }
  .mainLink:hover {
    color: #ff3e00;
    text-decoration: none;
  }
</style>

<div class="headerContainer">
  <h1 style="--color: {colors.brand};">TAGTEAM</h1>
  <div class="linksContainer">
    <a href="/" class="mainLink">Home</a>
    <a href="/features" class="mainLink">Features</a>
    <a href="/" class="mainLink">Community</a>
  </div>
</div>

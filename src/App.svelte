<script>
  // component imports
  import Header from './components/Header.svelte';

  // routing imports
  import { Router, Route } from 'svelte-routing';

  // page imports
  import Home from './pages/Home.svelte';
  import Features from './pages/Features.svelte';

  export let url = '';

  export let width = window.innerWidth;
  $: mobile = width < 700;
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <Header />
  <Router {url}>
    <Route path="/features" component={Features} />
    <Route path="/" component={Home} />
  </Router>
</main>

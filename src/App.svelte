<script>
  import { onMount } from 'svelte';
  import Menu from './components/Menu.svelte';
  import Home from './routes/Home.svelte';
  import CustomerRegistration from './routes/CustomerRegistration.svelte';
  
  let currentRoute = '/';

  function handleRouteChange() {
    currentRoute = window.location.pathname;
  }

  function handleLinkClick(event) {
    if (event.target.tagName === 'A') {
      event.preventDefault();
      const href = event.target.getAttribute('href');
      history.pushState(null, '', href);
      handleRouteChange();
    }
  }

  onMount(() => {
    handleRouteChange();
  });
  
</script>

<svelte:window on:popstate={handleRouteChange} />

<button on:click={handleLinkClick}>
  <Menu />

  {#if currentRoute === '/'}
    <Home />
  {:else if currentRoute === '/register'}
    <CustomerRegistration />
  {:else}
    <p>404 - Página no encontrada</p>
  {/if}
</button>

<!--
<style>
  :global(body) {
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    margin: 0;
    padding: 0;
  }
</style>
-->
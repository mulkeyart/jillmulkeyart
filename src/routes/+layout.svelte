<script>
  import "../styles.css";
  import MenuBar from '../lib/Components/MenuBar.svelte';
  import { page } from '$app/stores';

 import {routes} from '../lib/constants'
 

  $: heading = routes[$page.url.pathname] || "Page Not Found";
</script>

<svelte:head>
  <title>jillmulkeyart</title>
</svelte:head>

<MenuBar />
<main class="main_content">
  <h1 class="main_header text-center">{heading}</h1>
  <slot/>
</main>

<style> 
  .main_content {
    display: flex;
    color: white;
	  padding: 32px;
    flex-direction: column;
    width: 100%;
    height: 100%;
    background: linear-gradient(to right, #2f2f2f, #161616);
  }
  .main_header {
	text-shadow: 1px 5px 10px #9177ad;
	filter: brightness(2)
  }
</style>

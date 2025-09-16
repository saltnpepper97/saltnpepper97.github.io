<script lang="ts">
  import { onMount } from 'svelte';

  function openApp() {
    const searchParams = window.location.search; // ?code=...
    const deepLinkUrl = `macphee-ford-rental-tracker://auth-callback${searchParams}`;
    window.location.href = deepLinkUrl;
  }

  onMount(() => {
    // Automatically redirect on page load
    openApp();
  });
</script>

<main style="display:flex; flex-direction:column; align-items:center; justify-content:center; height:100vh; background:#030712; color:white;">
  <h1>Return to App</h1>
  <p>Click "Open App" to finish logging in</p>
  <button on:click={openApp} style="padding:12px 24px; border-radius:8px; border:1px solid rgba(255,255,255,0.2); background:transparent; color:white; cursor:pointer;">
    Open App
  </button>
  <p style="opacity:0.5; margin-top:16px;">You can close this window after authentication</p>
</main>

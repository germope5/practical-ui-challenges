<script>
  // Show or hide slot content
  export let visible = true;
</script>

{#if visible}
  <slot />
{:else}
  <p>Oculto</p>
{/if}

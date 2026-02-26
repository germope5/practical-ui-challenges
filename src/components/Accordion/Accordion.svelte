<script>
  // Simple accordion UI
  let open = false;
  function toggle() {
    open = !open;
  }
</script>

<div class="accordion">
  <button on:click={toggle}>{open ? 'Cerrar' : 'Abrir'}</button>
  {#if open}
    <div class="content">
      <slot />
    </div>
  {/if}
</div>

<script>
  // Two-way bound text input
  export let value = "";
</script>

<input bind:value />
<p>Valor actual: {value}</p>

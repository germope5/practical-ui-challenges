<script>
  // Dropdown selector component
  export let options = [];
  export let selected = null;
  function select(opt) {
    selected = opt;
  }
</script>

<select bind:value={selected} on:change={() => select(selected)}>
  {#each options as opt}
    <option value={opt}>{opt}</option>
  {/each}
</select>
<p>Seleccionado: {selected}</p>

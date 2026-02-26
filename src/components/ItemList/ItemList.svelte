<script>
  // Display a list of elements
  export let items = [];
</script>

<ul>
  {#each items as item}
    <li>{item}</li>
  {/each}
</ul>

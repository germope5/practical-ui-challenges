<script>
  // Counter example with internal state
  let count = 0;
  function increment() {
    count += 1;
  }
</script>

<div>
  <p>Clicks: {count}</p>
  <button on:click={increment}>Incrementar</button>
</div>

<script>
  import { onMount } from 'svelte';
  // Live clock component
  let time = '';
  onMount(() => {
    const interval = setInterval(() => {
      time = new Date().toLocaleTimeString();
    }, 1000);
    return () => clearInterval(interval);
  });
</script>

<p>Hora actual: {time}</p>

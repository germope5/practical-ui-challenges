# TextInput

Campo de texto con enlace bidireccional para capturar entradas.

## Props

- `value` (string): valor ligado.

## Uso

```svelte
<script>
  import TextInput from './TextInput.svelte';
  let name = '';
</script>

<TextInput bind:value={name} />
```

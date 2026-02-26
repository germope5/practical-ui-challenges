# Visibility

Componente que muestra u oculta su contenido según la prop `visible`.

## Props

- `visible` (boolean): controla la visibilidad.

## Uso

```svelte
<script>
  import Visibility from './Visibility.svelte';
</script>

<Visibility visible={true}>
  <p>Este contenido puede esconderse.</p>
</Visibility>
```

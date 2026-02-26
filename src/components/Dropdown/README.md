# Dropdown

Selector desplegable que permite elegir entre varias opciones.

## Props

- `options` (array): lista de valores.
- `selected` (any): valor actualmente seleccionado.

## Uso

```svelte
<script>
  import Dropdown from './Dropdown.svelte';
  let options = ['Rojo','Verde','Azul'];
</script>

<Dropdown {options} />
```

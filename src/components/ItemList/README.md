# ItemList

Muestra una lista de elementos pasada como prop `items`.

## Props

- `items` (array): elementos a listar.

## Uso

```svelte
<script>
  import ItemList from './ItemList.svelte';
  let items = ['Uno','Dos','Tres'];
</script>

<ItemList {items} />
```

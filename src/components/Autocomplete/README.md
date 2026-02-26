# Autocomplete

Componente de entrada con sugerencias filtrables. El campo mantiene una lista de opciones
estática (por ahora) y muestra coincidencias en tiempo real mientras el usuario escribe.
Es un buen punto de partida para retos de UX como autocompletar búsquedas o formularios.

## Características

- Filtrado reactivo de la lista `items` según el texto introducido.
- Selección de sugerencia con clic.
- Emite un evento `select` cuando se elige un elemento.
- Compatible con cualquier array de strings.

## Props

- `items` (string[]) – lista de valores que se pueden sugerir.
- `placeholder` (string, opcional) – texto de ayuda para el input.

## Eventos

```svelte
<Autocomplete {items} on:select={(e) => console.log(e.detail)} />
```

El detalle (`e.detail`) es el valor seleccionado.

## Uso básico

```svelte
<script>
  import Autocomplete from './Autocomplete.svelte';
  let items = ['Madrid','Barcelona','Bilbao'];
  let city = '';
</script>

<Autocomplete {items} bind:selected={city} placeholder="Escribe una ciudad" />
<p>Elegiste: {city}</p>
```

> 🔧 **Consejo**: en implementaciones avanzadas puedes reemplazar `items` con datos traídos
> de una API y mejorar la accesibilidad añadiendo roles ARIA (`listbox`, `option`).


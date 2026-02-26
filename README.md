# Laboratorio de Retos Prácticos de UI en Svelte

Este proyecto es un **laboratorio de componentes de interfaz de usuario (UI)** construidos con **Svelte**.  
La idea es practicar patrones de UI comunes (autocomplete, dropdowns, modales, steppers, etc.) a través de
componentes pequeños, cada uno enfocado en un reto concreto.

Actualmente el primer reto implementado es un **Autocomplete básico**.

---

## Requisitos

- **Node.js**: `>= 20.19` o `>= 22.12`  
  (Versiones anteriores de la rama 22, como `22.0.0`, no son compatibles con la versión actual de Vite.)

- **npm**: recomendado `>= 9`.

---

## Instalación y ejecución

Clona este repositorio y luego ejecuta:

```bash
npm install
npm run dev
```

Por defecto, Vite levantará el proyecto en una URL similar a `http://localhost:5173`.

---

## Estructura del proyecto

- `index.html`  
  Punto de entrada HTML de la aplicación.

- `src/main.js`  
  Monta el componente raíz de Svelte (`App.svelte`) usando la API moderna de Svelte 5 (`mount`).

- `src/App.svelte`  
  Componente raíz del laboratorio. Desde aquí se listan y montan los distintos retos de UI.

- `src/app.css`  
  Estilos globales básicos (reset simple, tipografía, layout principal).

- `src/components/`  
  Carpeta donde viven los **retos de UI** como componentes reutilizables.  
  Cada componente tiene su propio `README.md` con detalles.

  - [Accordion](src/components/Accordion/README.md)
  - [Autocomplete](src/components/Autocomplete/README.md)
  - [Button](src/components/Button/README.md)
  - [Clock](src/components/Clock/README.md)
  - [ColorSquare](src/components/ColorSquare/README.md)
  - [Counter](src/components/Counter/README.md)
  - [Dropdown](src/components/Dropdown/README.md)
  - [Greeting](src/components/Greeting/README.md)
  - [ItemList](src/components/ItemList/README.md)
  - [TextInput](src/components/TextInput/README.md)
  - [Visibility](src/components/Visibility/README.md)

---

## Añadir nuevos retos de UI

Para crear un nuevo reto:

1. Crea una nueva carpeta dentro de `src/components`, por ejemplo:

   ```text
   src/components/Modal/
   src/components/Tooltip/
   src/components/Tabs/
   ```

2. Dentro de esa carpeta, crea un archivo Svelte con el mismo nombre del componente, por ejemplo:

   ```text
   src/components/Modal/Modal.svelte
   ```

3. Implementa el componente de UI en ese archivo (`<script>`, markup y `<style>`).

4. Importa el nuevo componente en `src/App.svelte` y añádelo como una nueva sección del laboratorio,
   con un título y una breve descripción del reto.

De esta forma, `App.svelte` actúa como un **índice interactivo** de todos los retos que vayas creando.

---

## Reto 1: Autocomplete básico

El componente `Autocomplete.svelte` (en `src/components/Autocomplete/Autocomplete.svelte`) implementa:

- Un **campo de entrada** enlazado a una variable reactiva.
- Una **lista estática de sugerencias** (ciudades) filtrada según lo que el usuario introduce.
- Una lista de resultados que se actualiza de forma reactiva cuando cambia el input.
- Manejo básico de selección de sugerencias con el ratón.

En fases posteriores puedes extender este reto para:

- Soportar navegación por teclado (flechas, Enter, Escape).
- Añadir roles ARIA (`listbox`, `option`, etc.) y atributos de accesibilidad.
- Permitir listas dinámicas (por ejemplo, cargadas desde una API).

---

## Scripts disponibles

En `package.json` tienes los siguientes scripts:

- `npm run dev` – Lanza el servidor de desarrollo de Vite.
- `npm run build` – Genera la build de producción.
- `npm run preview` – Sirve la build de producción de forma local.

---

## Licencia

Este laboratorio está pensado como material de práctica personal.  
Puedes adaptarlo y ampliarlo según tus necesidades para seguir practicando Svelte y patrones de UI.


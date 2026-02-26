<script lang="ts">
// Un autocomplete es un componente en la UI que permite a los usuarios
//recibir sugerencias de autocompletado en un campo de texto mientras escribe.

 //Elementos necesarios para constuir un Autocomplete
 /* 
1. Campo de entrada
• 	Un  para enlazar directamente el valor del input con una variable reactiva.
• 	En Svelte, el  elimina la necesidad de escribir un  manual como en React.
2. Gestión de estado reactivo
• 	Variables declaradas con  en el  se vuelven reactivas automáticamente.
• 	Puedes usar la sintaxis  para crear valores derivados (ej. lista filtrada según lo que se escribe).
3. Fuente de datos
• 	Puede ser un array local o datos obtenidos con .
• 	Si usas datos externos, puedes manejar estados de carga () y errores con variables reactivas.
4. Lista de sugerencias
• 	Renderizada con  en el template.
• 	Ejemplo:
  {#if filtered.length > 0}
    <ul>
      {#each filtered as item}
        <li on:click={() => selectItem(item)}>{item}</li>
      {/each}
    </ul>
  {/if}

5. Interacción con teclado y mouse
• 	Eventos como , ,  se manejan directamente en el template.
• 	Puedes usar una variable  para resaltar la opción actual.
6. Accesibilidad
• 	Igual que en otros frameworks: roles ARIA y soporte de teclado.
• 	En Svelte, se agregan atributos directamente en el HTML.
7. Estilos y UX
• 	Puedes usar CSS dentro del mismo archivo .
• 	El estilo puede estar encapsulado automáticamente gracias al scoping de Svelte.
*/
//Declaramos nuestro campo de entrada
let inputField = "";
// Vamos a utilizar una lista estática que muestra sugerencias (Ciudades):
let staticList = ["Mexico City", "New York", "Madrid", "Roma", "Buenos Aires", "London", "Tokyo"];
//Lista filtrada
let filtered = [];

//Ahora declaremos de manera reactiva ($), una lista filtrada
$: filtered = staticList.filter(s => 
  s.toLowerCase().includes(inputField.toLowerCase())
)

//Declaramos una función para seleccionar una sugerencia de lista.
function selectSuggestion(sugerencia) {
  inputField = sugerencia;
  filtered = [];
}

</script>


<section class="autocomplete">
  <div class="autocomplete-input">
    <!-- Aquí irá el campo de entrada del autocomplete -->
     <input bind:value={inputField} placeholder="Escribe una ciudad ..."/>
  </div>
  <!-- COLOCAMOS LA CONDICIÓN PARA HACER EL FILTRADO -->
   {#if filtered.length > 0}
    {#each filtered as s}
      <li on:click={() => selectSuggestion(s)}>{s}</li>
    {/each}
   {/if}
  <div class="autocomplete-list">
    <!-- Aquí irá la lista de sugerencias del autocomplete -->
  </div>
</section>


<style>
.autocomplete-input {
  position: relative;
  width: 100%;
  margin-bottom: 0.5rem;
}

.autocomplete-input input {
  width: 100%;
  padding: 0.5rem 0.75rem;
  font-size: 1rem;
  border: 1px solid #aaa;
  border-radius: 4px;
  box-sizing: border-box;
  outline: none;
  transition: border 0.2s;
}

.autocomplete-input input:focus {
  border: 1.5px solid #007bff;
  background-color: #fafdff;
}
</style>



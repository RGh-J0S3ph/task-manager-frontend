# Preguntas de cierre EC2 F3 A8

## 1. **¿Por qué las reglas de validación se colocaron en una utilidad?**  
   Para separar las reglas del código de presentación y poder reutilizarlas tanto al crear como al editar una tarea. Así, ambos formularios aplican los mismos límites y mensajes.

## 2. **¿Qué significa el retorno string | null de validateTaskTitle?**  
   Devuelve un texto cuando el título no es válido, para explicar el error; devuelve null cuando pasa todas las validaciones. El formulario usa ese resultado para decidir si muestra el mensaje o continúa.

## 3. **¿Qué función cumplen aria-invalid, aria-describedby y role="alert"?**  
   `aria-invalid` comunica a las tecnologías de asistencia que el campo tiene un error. `aria-describedby` relaciona el campo con su texto de ayuda y, si existe, con el mensaje de error. `role="alert"` hace que el mensaje nuevo se anuncie de forma inmediata.

## 4. **¿Por qué query, filter y sortBy son estados controlados?**  
   Porque sus valores determinan lo que muestran los controles y las tareas. Mantenerlos en el estado de React permite que la interfaz y los resultados se actualicen de forma sincronizada cuando el usuario cambia un criterio.

## 5. **¿Por qué visibleTasks no debe almacenarse como estado independiente?**  
   Porque se calcula a partir de `tasks`, `query`, `filter` y `sortBy`. Mantenerlo también como estado duplicaría información y podría dejarla desincronizada; es más fiable derivarlo en cada render.

## 6. **¿Cómo se normaliza una búsqueda?**  
   Se quitan los espacios al principio y al final con `trim()` y se pasa el texto a minúsculas con la configuración regional `es-MX`. Se aplica la misma conversión al título y se busca la coincidencia parcial con `includes()`.

## 7. **¿Por qué se crea una copia antes de utilizar sort?**  
   Porque `sort` modifica el arreglo original. Ordenar una copia evita mutar la lista filtrada —y, por extensión, los datos recibidos como entrada— durante el cálculo de resultados.

## 8. **¿Qué responsabilidad tiene task-query.service.ts?**  
   Encapsula la lógica de consulta de tareas: normaliza la búsqueda, aplica búsqueda y filtro por estado, y ordena los resultados. Así, esa lógica queda separada de los componentes de interfaz.

## 9. **¿Por qué el resultado de JSON.parse se trata como unknown?**  
   Porque los datos de `localStorage` pueden estar malformados o no tener la estructura esperada. `JSON.parse` no garantiza que el valor sea una tarea válida; tratarlo como `unknown` obliga a comprobarlo antes de usarlo como `Task`.

## 10. **¿Qué comprueba la función isTask?**  
    Comprueba que el valor sea un objeto con `id` y `title` de tipo texto, un estado permitido (`pending` o `completed`) y fechas `createdAt` y `updatedAt` que sean textos interpretables como fechas. Solo entonces lo acepta como `Task`.

## 11. **¿Qué ventaja ofrece la inicialización diferida de useState?**  
    Al pasar `() => loadTasks(initialTasks)`, React ejecuta la carga inicial una sola vez al inicializar el estado, en vez de volver a llamar a `loadTasks` en cada render.

## 12. **¿Por qué localStorage se sincroniza mediante useEffect?**  
    Guardar datos es un efecto secundario, por lo que no debe ocurrir durante el render. El efecto guarda las tareas cuando cambia `tasks`, manteniendo el render dedicado a calcular y mostrar la interfaz.

## 13. **¿Por qué TaskSummary recibe tasks y TaskList recibe visibleTasks?**  
    El resumen presenta los totales generales de tareas pendientes y completadas, sin depender de los criterios de búsqueda. La lista, en cambio, debe mostrar solo las tareas que coinciden con la búsqueda, el filtro y el orden elegidos.

## 14. **¿Qué información se pierde y cuál permanece al recargar?**  
    Las tareas se guardan en `localStorage` y se vuelven a cargar, así que permanecen después de recargar la página. Los criterios de consulta, filtro y orden solo están en el estado de React; al recargar vuelven a sus valores iniciales.

## 15. **¿Qué dificultad encontraste y cómo la resolviste?**  

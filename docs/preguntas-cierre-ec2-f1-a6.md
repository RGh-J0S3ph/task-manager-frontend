## 1. ¿Qué función cumple la interfaz Task?

La interfaz `Task` define la estructura de una tarea dentro de la aplicación. En este proyecto, representa el modelo de datos que debe tener cada tarea, con propiedades como `id`, `title`, `status`, `createdAt` y `updatedAt`. Esto permite que TypeScript valide que los objetos de tareas tengan siempre la forma correcta.

## 2. ¿Qué diferencia existe entre Task y TaskStatus?

`Task` es la interfaz completa de un objeto de tarea, mientras que `TaskStatus` es un tipo más específico que solo restringe el valor del campo `status`. En otras palabras, `TaskStatus` define los posibles estados de una tarea, que en este caso son `'pending'` y `'completed'`.

## 3. ¿Qué significa declarar un arreglo como Task[]?

Significa que el arreglo contiene únicamente objetos que cumplen con la estructura de la interfaz `Task`. Es decir, cada elemento del arreglo es una tarea válida con todas las propiedades requeridas.

## 4. ¿Qué hace el método map?

`map` recorre cada elemento de un arreglo y devuelve un nuevo arreglo con el resultado de aplicar una transformación a cada elemento. En React, se usa mucho para renderizar listas a partir de colecciones de datos.

## 5. ¿Qué resultado produce map dentro de TaskList?

Dentro de `TaskList`, `tasks.map((task) => <TaskItem key={task.id} task={task} />)` genera un componente `TaskItem` por cada tarea del arreglo. Es decir, renderiza la lista completa de tareas en la interfaz.

## 6. ¿Para qué utiliza React la propiedad key?

React usa `key` para identificar de manera única cada elemento dentro de una lista y así poder actualizar, insertar o eliminar elementos correctamente. Esto ayuda a React a optimizar el renderizado y evitar errores visuales o de estado.

## 7. ¿Por qué se utiliza task.id y no el índice?

Se usa `task.id` porque es un identificador único y estable para cada tarea. El índice no es confiable si el arreglo cambia, ya que al agregar o eliminar elementos los índices se reacomodan. Con `id`, React identifica correctamente cada elemento.

## 8. ¿Cómo se envía una tarea de TaskList a TaskItem?

Se envía como prop: `task={task}`. En el `map`, cada tarea se pasa al componente `TaskItem` para que pueda renderizar su título, estado y fecha.

## 9. ¿Cómo se comunican App, TaskSummary y TaskList?

`App` es el componente padre y pasa la colección de tareas como props a `TaskSummary` y `TaskList`. `TaskSummary` usa esa colección para calcular el total, pendientes y completadas; `TaskList` la usa para renderizar cada tarea. La comunicación es unidireccional desde `App` hacia los componentes hijos.

## 10. ¿Qué es el renderizado condicional?

Es la capacidad de React de mostrar contenido diferente dependiendo de una condición. En este caso, si `tasks.length === 0`, se muestra un estado vacío; si hay tareas, se renderiza la lista con los `TaskItem`.

## 11. ¿Por qué el resumen se calcula a partir de la colección?

Porque el resumen debe reflejar el estado actual de todas las tareas. Si la colección cambia, el número de tareas totales, pendientes y completadas también cambia automáticamente. Así se mantiene la información sincronizada con los datos reales.

## 12. ¿Qué dificultad encontraste durante la refactorización y cómo la resolviste?

La dificultad principal fue mantener la consistencia del flujo de datos durante la refactorización: definir bien la interfaz `Task`, corregir los props de los componentes y asegurar que la lista se renderizara correctamente. Lo resolví centralizando el modelo de datos con `Task`, tipando la colección como `Task[]` y usando `key={task.id}` para cada elemento de la lista. También verifiqué el flujo de props desde `App` hacia `TaskSummary` y `TaskList`, lo que evitó errores de estructura y renderizado.

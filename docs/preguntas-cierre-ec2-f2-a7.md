# Preguntas de cierre - EC2 F2 A7

## 1. ¿Qué diferencia existe entre una variable local y el estado de React?
Una variable local solo existe dentro del render del componente y no provoca una nueva representación visual cuando cambia.
El estado de React es especial: se guarda en memoria, React lo observa y, cuando cambia, vuelve a renderizar el componente automáticamente.

## 2. ¿Qué valores devuelve useState?
Devuelve un arreglo con exactamente dos elementos:
    - El valor actual del estado 
    - Una función para actualizar ese valor

## 3. ¿Por qué useState se declara en el nivel superior del componente?
Porque React exige que los hooks se llamen en el mismo orden en cada render.

## 4. ¿Qué significa que un campo sea controlado?
Un campo controlado es aquel cuyo valor está ligado al estado de React.

## 5. ¿Por qué handleSubmit utiliza preventDefault?
Evita que el navegador recargue la página al enviar el formulario.

## 6. ¿Cómo comunica TaskForm una nueva tarea a App?
Mediante una prop llamada onAddTask.

## 7. ¿Por qué App funciona como fuente de verdad?
Porque App guarda el arreglo tasks, que es la información central del sistema.

## 8. ¿Cómo se implementa Create sin utilizar push?
No se muta el arreglo original. Se crea un nuevo objeto de tarea y se usa setTasks((currentTasks) => [newTask, ...currentTasks]).

## 9. ¿Cómo permite map actualizar una sola tarea?
map recorre cada elemento del arreglo y devuelve una nueva versión transformada. Cuando encuentra el id que coincide, devuelve la tarea actualizada; en los demás casos, devuelve la tarea sin cambios.

## 10. ¿Cómo utiliza filter la operación Delete?
Crea un nuevo arreglo con todos los elementos que cumplan una condición.

## 11. ¿Por qué se emplea una función actualizadora en setTasks?
Porque React recomienda usar el estado previo para evitar errores cuando varias actualizaciones pasan casi al mismo tiempo.

## 12. ¿Qué información conserva TaskItem como estado local?
Guarda dos piezas de estado local:
    - isEditing: si está en modo edición
    - draftTitle: el texto temporal que se está editando

## 13. ¿Por qué los cambios desaparecen al recargar la página?
Porque los datos están guardados solo en memoria del navegador, no en almacenamiento persistente.

## 14. ¿Qué dificultad encontraste y cómo la resolviste?
Mi reto es esta actividad fue compreder como es que funciona el flujo del CRUD dentro de una aplicación con react. Medinate la documentación y realizando consultas con IA pude resolver este reto.
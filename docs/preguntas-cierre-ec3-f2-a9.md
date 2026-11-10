#  Preguntas de cierre - EC3 F1 A9

## 1. ¿Qué es una aplicación de página única?

Es una app en la que la interfaz se carga una sola vez y las vistas se cambian dinámicamente sin recargar el navegador. En React, esto se logra con enrutamiento del lado del cliente, como `BrowserRouter`, `Routes` y `Route`.

## 2. ¿Qué responsabilidad tiene BrowserRouter?

`BrowserRouter` proporciona el contexto de navegación a toda la aplicación y sincroniza la URL actual con el estado del enrutador. Gracias a él, React Router puede saber qué ruta está activa y renderizar el componente correcto.

## 3. ¿Cuál es la diferencia entre Routes y Route?

`Routes` es el contenedor que define el conjunto de rutas de la app. `Route` es cada regla individual que indica qué componente se muestra cuando la URL coincide con una ruta específica. En otras palabras, `Routes` agrupa y evalúa las rutas, y `Route` define cada caso.

## 4. ¿Qué es una ruta índice?

Es la ruta por defecto que se renderiza cuando la URL coincide con la raíz del sitio, por ejemplo `/`. En React Router se define con la prop `index` dentro de un `Route` padre, y normalmente muestra la página de inicio.

## 5. ¿Qué beneficio ofrece un layout?

Un layout permite reutilizar una estructura visual común en varias páginas, como el header, la navegación y el footer. En esta app, `AppLayout` evita duplicar código y mantiene la misma apariencia en todas las vistas.

## 6. ¿Qué función cumple Outlet?

`Outlet` es un marcador de posición que indica dónde deben renderizarse las rutas hijas dentro del layout. En `AppLayout`, se usa para mostrar la página activa entre el encabezado y el pie de página.

## 7. ¿Qué diferencia existe entre Link y NavLink?

`Link` navega entre rutas sin recargar la página. `NavLink` además puede detectar si la ruta actual está activa y aplicar estilos o clases para resaltar el enlace. Por eso se usa en la navegación principal para marcar la opción seleccionada.

## 8. ¿Por qué no se utilizan enlaces a para navegar internamente?

Porque los enlaces `<a href="/tasks">` provocan una recarga completa de la página, perdiendo el estado de la aplicación y contradiciendo la idea de una SPA. Con `Link` o `NavLink`, la navegación ocurre de forma client-side y se mantiene la experiencia de una sola página.

## 9. ¿Qué representa :taskId?

Representa un segmento dinámico de la URL, es decir, un valor variable que identifica una tarea en particular. Por ejemplo, `/tasks/123` puede corresponder a la tarea con id `123`.

## 10. ¿Cómo se recupera un parámetro dinámico?

Se usa `useParams()`, que devuelve un objeto con los parámetros de la ruta actual. En este proyecto se hace `const { taskId } = useParams<{ taskId: string }>();` para obtener el identificador de la tarea desde la URL.

## 11. ¿Cuándo debe utilizarse useNavigate?

Cuando la navegación debe ocurrir de forma programática, por ejemplo después de eliminar una tarea o de enviar al usuario a otra vista como resultado de una acción. En este caso, se usa para redirigir al usuario a `/tasks` después de borrar una tarea.

## 12. ¿Qué función cumple la ruta *?

La ruta `*` sirve como ruta comodín para capturar cualquier URL que no coincida con las rutas definidas. Se usa para mostrar una página de error o “No encontrado” cuando la ruta solicitada no existe.

## 13. ¿Por qué el estado continúa administrado por App?

Porque es el componente superior de la aplicación y contiene los datos compartidos de todas las tareas. Desde ahí se centralizan las operaciones principales: agregar, editar, eliminar, filtrar y ordenar. Así, todas las páginas pueden recibir la misma información y actuar sobre ella.

## 14. ¿Por qué localStorage permanece en esta actividad?

Porque permite conservar las tareas incluso después de recargar la página o cerrar el navegador. Esto hace que la app se comporte como una pequeña herramienta persistente sin necesidad de backend, manteniendo los datos en el navegador.

## 15. ¿Qué dificultad encontraste y cómo la resolviste?

La dificultad principal fue mantener la navegación y el estado sincronizados, especialmente cuando una tarea se abría por ruta dinámica (`/tasks/:taskId`) y cuando se necesitaba persistir la información en `localStorage`. Para resolverlo, centralicé el estado en `App`, usé `useParams` para leer el id dinámico, y validé la información guardada en `localStorage` para evitar inconsistencias. También utilicé `useNavigate` para redirigir después de eliminar una tarea y mantener una experiencia fluida.

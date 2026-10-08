# Administrador de tareas - Frontend

Aplicación desarrollada con React, TypeScript, Vite y PNPM
para administrar tareas.

## Alcance actual

La aplicación permite visualizar una colección local de tareas
mediante componentes React.
Actualmente incluye:

- Modelo de tarea con TypeScript.
- Cinco tareas locales.
- Renderizado mediante map.
- Uso de claves estables.
- Estados pendiente y completada.
- Resumen calculado.
- Mensaje para una colección vacía.
- Diseño adaptable.
  Los formularios, eventos y operaciones CRUD se implementarán
  en actividades posteriores.

## Tecnologías

- React
- TypeScript
- Vite
- PNPM
- CSS
- Git y GitHub

## Instalación

pnpm install

## Ejecución

pnpm dev

## Validación

pnpm lint
pnpm build

## Estructura principal

- components: componentes visuales.
- data: colección local de tareas.
- models: tipos e interfaces.
- styles: estilos globales.
- docs: preguntas y documentación.

## Modelo Task

Cada tarea contiene id, title, status, createdAt y updatedAt.

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some Oxlint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the Oxlint configuration

If you are developing a production application, we recommend enabling type-aware lint rules by installing `oxlint-tsgolint` and editing `.oxlintrc.json`:

```json
{
  "$schema": "./node_modules/oxlint/configuration_schema.json",
  "plugins": ["react", "typescript", "oxc"],
  "options": {
    "typeAware": true
  },
  "rules": {
    "react/rules-of-hooks": "error",
    "react/only-export-components": ["warn", { "allowConstantExport": true }]
  }
}
```

See the [Oxlint rules documentation](https://oxc.rs/docs/guide/usage/linter/rules) for the full list of rules and categories.

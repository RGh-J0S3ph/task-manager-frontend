# Administrador de tareas - Frontend

Aplicación desarrollada durante el elemento de competencia 2
de Diseño Frontend con Frameworks.

## Tecnologías

- React
- TypeScript
- Vite
- PNPM
- CSS

## Alcance actual

La versión actual contiene la estructura visual del Administrador
de tareas y tres tareas de demostración. Los formularios, filtros
y acciones todavía no tienen comportamiento.

## Instalación

```bash
pnpm install
```

## Ejecución

```bash
pnpm dev
```

## Compilación

```bash
pnpm build
```

## Componentes principales

- AppHeader
- TaskForm
- TaskFilters
- TaskSummary
- TaskList
- TaskItem

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

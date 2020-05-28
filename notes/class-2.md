# Clase #2 - Directivas de Tailwind

Directiva es una instrucción que utiliza tailwind para insertar código en el archivo final de css que genera.

## `@tailwind base;`

Esto inyecta los estilos base de Tailwind y cualquier estilo base registrado por plugins.

## `@tailwind components;`

Esto inyecta las clases de componentes de Tailwind y cualquier clase de componente registrado por los plugins.

## `@tailwind utilities;`

Esto inyecta las clases de utilidad de Tailwind y cualquier clase de utilidad registrada por los plugins.

## `@tailwind screens`

Esta directiva sirve para controlar donde Tailwind inyecta las variaciones responsivas de cada utilidad. Si se omite, Tailwind añadirá estas clases al final de tu css, por defecto.

## Resultaddo

```postcss
@tailwind base;

@tailwind components;

@tailwind utilities;
```

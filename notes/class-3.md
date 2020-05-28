# Personalización y configuración

Ya que Tailwind es un framework para construir UI a la medida, por default, se tiene un archivo opcional llamado tailwind.config.js en la raíz de la carpeta, donde está el package.json.

## Creando un archivo de configuración

Para generar un archivo de configuración para Tailwind, podemos usar el Tailwind CLI:

npx tailwind init
Nota. Podemos utilizar esta herramienta cuando instalamos la dependencia via npm.
Donde como resultado tendremos tailwind.config.js:

```js
module.exports = {
  theme: {},
  variants: {},
  plugins: [],
};
```

Cabe mencionar que cada sección, del archivo de configuración, es opcional.

## La sección Theme

Esta sección es donde definimos los aspectos relacionados con el diseño visual de nuestro sitio.

```js
  theme: {
    screens: {
      sm: '640px',
      md: '768px',
      lg: '1024px',
      xl: '1280px',
    },
    fontFamily: {
      display: ['Gilroy', 'sans-serif'],
      body: ['Graphik', 'sans-serif'],
    },
    borderWidth: {
      default: '1px',
      '0': '0',
      '2': '2px',
      '4': '4px',
    },
    extend: {
      colors: {
        cyan: '#9cdbff',
      },
      spacing: {
        '96': '24rem',
        '128': '32rem',
      }
    }
  }
```

## La sección Variants

Esta sección nos permite controlar el comportamiento de las utilidades core, como responsive variants y pseudo-class variants.

```js
  variants: {
    appearance: ['responsive'],
    // ...
    borderColor: ['responsive', 'hover', 'focus'],
    // ...
    outline: ['responsive', 'focus'],
    // ...
    zIndex: ['responsive'],
  },
```

## La sección Plugins

Esta sección nos permite registrar plugins de terceros con el objetivo de extender utilidades, componentes, estilos, etc.

```js
  plugins: [
    require('tailwindcss-transforms'),
    require('tailwindcss-transitions'),
    require('tailwindcss-border-gradients'),
  ],
```

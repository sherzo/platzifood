# Clase #1 - Instalación y ambiente de desarrollo

Para dar inicio al proyecto abrimos una terminal en la carpeta donde queramos crearlo y ejecutamos el comando:

`npm init`

Nos pide datos de proyecto como: nombre, descripción, autor etc. Una vez concluido el proceso instalamos las dependencias iniciales

`npm install tailwindcss autoprefixer postcss-cli`

Una vez instaldo es necesario debemos ejecutar un comando para iniciar **tailwindcss**. Lo hacemos a través de **npx** con:

`npx tailwindcss init`

Esto generara para nosotros un archivo llamado **tailwind.config.js** que mas adelante iremos cofigurando, por ahora debemos crear otro archivo inicial y una opción para hacerlo es.

`touch postcss.config.js`

Durante el curso se usará [Visual Studio Code](https://code.visualstudio.com/) como editor de código, abrimos el proyecto en dicho editor.

> Recomandacion: Instalar la extensión: _Tailwind CSS IntelliSense_

Al tener el archivo _postcss.config.js_ haremos la siguiente configuración inicial.

`postcss.config.js`

```js
module.exports = {
  plugins: [require("tailwindcss"), require("autoprefixer")],
};
```

Con ella estamos importando los plugins necesarios para dar inicio al uso de tailwindcss.

Ahora crearemos el punto de entrada de nuestro estilos que estará dentro de la carpeta así **css/tailwind.css**. Se llamó al archivo de esta manera pero puede ser llamado de cualquiero otra forma.

Dentro de nuestro archivo agregaremos las directivas del código base de _tailwindcss_ para que todo empiece a funcionar.

`css/tailwind.css`

```css
@tailwind base;

@tailwind components;

@tailwind utilities;
```

Seguido de esto crearemos nuestro archivo _html_ en la carpeta _public_
**public/index.html**

el contenido de este archivo inicialmente será:

`public/index.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Inicio</title>
    <!-- Importamos el archivo que será generado en un momento llamandolo -->
    <link rel="stylesheet" href="css/style.css" />
  </head>
  <body>
    <h1>Hello World</h1>
  </body>
</html>
```

En el archivo **public/index.html** estamos important un archivo llamado **style.css**, este no lo hemos generado aún para generar vamos agragar un comando de **npm** que llamaremos **build** esto dentro de nuestro archivo **package.json** en la raíz del proyecto.

`package.json`

```json
"scripts": {
  "build": "postcss css/tailwind.css -o public/css/style.css"
},
```

Este comando generará nuestro archivo **public/css/styles.css** a partir de la entrada **css/tailwind.css** usando **postcss**.

Ahora para conluir con nuestro entorno de desarrollo usaremos un servidor de desarrollo que será **live-server** el mismo podemos instalarlo con:

`npm install live-server -g`

y podemos utilizarlo de la siguiente manera, desde la raíz de nuestro proyecto ejecutamos el comando dandole como punto de entrado la capeta **public**

`live-server public`

Para facilitar aun mas este proceso podemos agregar este comando a nuestro package.json

Al final debes tener la siguiente estructura de archivos y carpetas.

```js
|css/
|   |--tailwind.css
| node_modules/
| public/
|       |--index.html
|       |--css/
|             |--style.css
| packge.json
| packge-lock.json
| postcss.config.js
| tailwind.config.js
```

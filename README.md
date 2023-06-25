# Herramientas-IDE-TypeScript

En esta sección se hablará un poco sobre herramientas IDE que se pueden utilizar para el desarrollo de TypeScript.

Además de instalar Ts de manera global mediente el modulo npm de NodeJs con el comando: npm install -g typescript, es recomendable seguir estas instrucciones  en el IDE que escojan para optimizar nuestro trabajo como desarrolladores.

El primero IDE que voy a mencionar y el recomendado para el curso, VS CODE (https://code.visualstudio.com/)

Para utilizar este IDE, una vez instalado se pueden seguir las siguientes instrucciones:

1. Abre la carpeta de tu proyecto en Visual Studio Code mediante la opción "File" > "Open Folder" o haciendo click derecho en la carpeta y "abrir con Visual Studio Code". 

2. Si aún no tienes instalada la extensión de TypeScript, ve a la pestaña de extensiones (icono de cubo en la barra lateral izquierda) y busca "TypeScript". Instala la extensión proporcionada por Microsoft.
![image](https://github.com/nicodonazzon/Herramientas-IDE/assets/60930400/19722b40-9a84-4817-a118-e8282373d14d)

3. Una vez instalada la extensión, Visual Studio Code reconocerá automáticamente los archivos TypeScript en tu proyecto y aplicará el resaltado de sintaxis y otras funcionalidades relacionadas con TypeScript.

4. Puedes acceder a las opciones de configuración de TypeScript en Visual Studio Code mediante el archivo tsconfig.json.([Ver al final](#seccion1)) El editor te mostrará advertencias y sugerencias basadas en estas configuraciones.

Otros IDES a tener en cuenta son:

* Visual Studio 2022

  Con este IDE se puede implementar TypeScrypt en un proyecto mediante Nuget Package Manager o instalando una extensión de Ts para VS 2022.

* Atom (Desactualizado, no recomendado, https://github.com/atom/atom/releases/tag/v1.60.0)

   1. Abre Atom en tu computadora.

   2. Haz clic en "File" en la barra de menú superior y selecciona "Settings" o "Preferencias" (dependiendo de tu sistema operativo).

   3. En la ventana de configuración de Atom, selecciona "Install" en el menú lateral izquierdo.

   4. En el campo de búsqueda, escribe "atom-typescript" y presiona Enter.

   5. Debería aparecer el paquete "atom-typescript" en los resultados de búsqueda. Haz clic en "Install" para instalarlo.

* WebStorm (de Pago, https://www.jetbrains.com/es-es/webstorm/download/#section=windows)

  1. Ve al menú "File" y selecciona "Settings" o "Preferences" (dependiendo de tu sistema operativo).

  2. En la ventana de configuración de WebStorm, busca "Languages & Frameworks" o "Idiomas y marcos de trabajo" en el panel izquierdo y haz clic 
  en él para expandirlo.

  3. Selecciona "TypeScript" en la lista de opciones.

  4. Si no tienes TypeScript instalado en tu sistema, WebStorm te ofrecerá la opción de instalarlo automáticamente. Haz clic en "Install" para 
  comenzar la instalación.

  5. Si ya tienes TypeScript instalado en tu sistema, WebStorm te mostrará la ruta de la instalación actual. Puedes verificar que sea la ruta 
  correcta o actualizarla si es necesario.

  6. Haz clic en "OK" o "Aplicar" para guardar los cambios y cerrar la ventana de configuración.

<a name="seccion1"></a>

CONFIGURACIÓN DEL ARCHIVO TSCONFIG.JSON

El archivo `tsconfig.json` es utilizado por TypeScript para configurar y especificar las opciones de compilación del proyecto. Proporciona un control detallado sobre cómo se compilarán los archivos TypeScript en JavaScript, permitiendo personalizar aspectos como el nivel de compatibilidad, los directorios de salida, las opciones de module resolution y más.

A continuación, te explico las principales opciones que puedes configurar en el archivo `tsconfig.json`:

- `compilerOptions`: Este objeto contiene las opciones de configuración para el compilador de TypeScript. Algunas de las opciones más comunes son:

- `target`: Especifica la versión de ECMAScript a la que se debe compilar el código TypeScript. Puedes elegir valores como "es5", "es6", "es2015", "es2016", etc.

- `module`: Indica el formato de módulo que se utilizará en la compilación. Las opciones más comunes son "commonjs" (para entornos Node.js) y "es2015" (para entornos modernos de navegadores).

- `outDir`: Define el directorio de salida para los archivos JavaScript generados por la compilación. Por ejemplo, puedes establecerlo como "dist" para que los archivos se generen en una carpeta llamada "dist".

- `strict`: Habilita o deshabilita el modo estricto de TypeScript, que impone reglas adicionales y realiza comprobaciones más rigurosas para garantizar un código más seguro y robusto.

- `include`: Un arreglo que especifica los patrones de archivos que se deben incluir en la compilación. Por ejemplo, puedes usar `"include": ["src/**/*.ts"]` para incluir todos los archivos `.ts` dentro de la carpeta `src` y sus subcarpetas.

- `exclude`: Un arreglo que especifica los patrones de archivos que se deben excluir de la compilación. Puedes usarlo para evitar que ciertos archivos o carpetas se incluyan en el proceso de compilación. Por ejemplo, `"exclude": ["node_modules"]` excluye la carpeta `node_modules` del proceso de compilación.

Ejemplo genérico del tsconfig:

![image](https://github.com/nicodonazzon/Herramientas-IDE/assets/60930400/f4a9280d-3b73-41b3-a88e-2eec9326a506)


Estos son solo algunos ejemplos de las opciones que puedes configurar en el archivo `tsconfig.json`. Pueden consultar todas opciones en https://www.typescriptlang.org/es/tsconfig

Para compilar, se ejecuta el comando `tsc` en la raíz del proyecto para compilar tu código TypeScript utilizando la configuración especificada en el archivo `tsconfig.json`.

DEPURACIÓN DE CÓDIGO EN TYPESCRIPT

En este apartado voy a dejar una pequeña guía de como configurar VS CODE para depurar el código de Ts en caso de que VS CODE no lo configure automaticamente. 

1. Antes que nada se debe agregar una linea de código al archivo tsconfig.json que diga `"sourceMap" : true`. Esto generará unos archivos que le van a decir a VS CODE como mapear el código de Js a Ts.

![image](https://github.com/nicodonazzon/Herramientas-IDE/assets/60930400/2d643bc8-9bea-4226-9080-67f2b642e17f)

2. Al compilar con el comando tsc, se puede apreciar que ahora en la carpeta donde se crean los .js compilados (generalmente en la carpeta dist si usan un tsconfig generico), se puede ver otro archivo con la extensión .map. No es importante analizar lo que hay adentro es solo para que VS CODE pueda mapear el código para despues depurarlo.

3. Despues hay que ir a la opción Run & Debug de VS Code y hacer click en la opción "crear launch.json file" e indicar la opción de node js.

![image](https://github.com/nicodonazzon/Herramientas-IDE/assets/60930400/172d9c77-5fb0-4c9e-a436-3b4da606d32a)

   Les creará un archivo con un contenido similar a este:

![image](https://github.com/nicodonazzon/Herramientas-IDE/assets/60930400/1a7babd6-0dd4-4b0c-a7b1-a1b963cbc953)

5. Ahora hay que agregar una línea de código `"preLaunchTask" : "tsc: build - tsconfig.json"` al archivo launch.json para que quede así:

![image](https://github.com/nicodonazzon/Herramientas-IDE/assets/60930400/4885a846-dace-4309-9bec-d65342a62fad)

6. Perfecto ahora solo queda marcar un breakpoint y empezar a depurar con el bóton launch.

Eso es todo, nos vemos en el siguente tema del temario. ¡Saludos!



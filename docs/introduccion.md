# Introducción

Lua es un lenguaje de programación ligero, rápido y fácil de aprender, diseñado para ser embebido en aplicaciones. Fue creado en 1993 por Roberto Ierusalimschy, Luiz Henrique de Figueiredo y Waldemar Celes en la Pontifícia Universidade Católica do Rio de Janeiro (PUC-Rio) en Brasil.

Lua es conocido por su simplicidad y flexibilidad, lo que lo hace ideal para una amplia variedad de aplicaciones, desde el desarrollo de videojuegos hasta la automatización de tareas y el scripting en general. Lua se utiliza en muchos juegos populares, como World of Warcraft, Angry Birds y Roblox, así como en aplicaciones embebidas y sistemas operativos.

Entre otras características, Lua ofrece:

- Sintaxis simple y fácil de aprender
- Tipos de datos dinámicos
- Funciones de primera clase
- Soporte para programación orientada a objetos
- Extensibilidad a través de bibliotecas y módulos

En esta página, presentaremos una introducción a Lua, cubriendo los conceptos básicos del lenguaje, su sintaxis y algunas de sus características más importantes. También proporcionaremos ejemplos y recursos para ayudarte a comenzar a programar en Lua.

## Instalación

Vamos a comenzar por instalar Lua en tu sistema. Es importante mencionar, que Lua es un lenguaje de programación interpretado, lo que significa que no necesitas compilar tu código para ejecutarlo. Sin embargo, necesitarás tener el intérprete de Lua instalado en tu máquina para poder ejecutar tus scripts.

Para instalar el interprete de Lua, puedes seguir estos pasos:

1. Visita el sitio web oficial de Lua en [https://www.lua.org/download.html](https://www.lua.org/download.html).
2. Descarga la versión más reciente de Lua para tu sistema operativo.

Nota: Puedes descargar el código fuente y compilarlo tú mismo, o puedes buscar paquetes precompilados para tu sistema operativo. En sistemas basados en Unix, como Linux y macOS, es común usar un gestor de paquetes para instalar Lua. Por ejemplo, en Ubuntu puedes usar el siguiente comando:

```bash
sudo apt-get install lua5.3
``` 

## Ejecutar el intérprete de Lua

Una vez que hayas instalado Lua, puedes ejecutar el intérprete de Lua desde la línea de comandos. Simplemente abre una terminal y escribe `lua` para iniciar el intérprete interactivo. Verás un prompt donde puedes escribir código Lua directamente y ver los resultados inmediatamente.

```bashlua
$ lua
Lua 5.3.5  Copyright (C) 1994-2018 Lua.org, PUC-Rio
> print("¡Hola, Lua!")
¡Hola, Lua!
>
```



Podrás ver que el interprete de Lua te permite ejecutar código línea por línea, lo que es útil para probar pequeñas porciones de código o para aprender el lenguaje de manera interactiva.

También puedes ejecutar scripts de Lua desde la línea de comandos. Para hacer esto, simplemente guarda tu código Lua en un archivo con la extensión `.lua` y luego ejecuta el siguiente comando:

```bash
lua tu_script.lua
```

## Chunks

En Lua, un "chunk" es una porción de código que puede ser ejecutada. Un chunk puede ser tan pequeño como una sola línea de código o tan grande como un programa completo. Cuando ejecutas un script de Lua, el intérprete lo trata como un chunk y lo ejecuta en su totalidad.

Normalmente, cada instrucción en Lua termina con un salto de línea, lo que indica el final de una instrucción. Sin embargo, también puedes usar el punto y coma (`;`) para separar múltiples instrucciones en la misma línea. Por ejemplo:

```lua
print("Hola"); print("Mundo") -- Esto imprimirá "Hola" y "Mundo" en la misma línea
```

## Comentarios

En Lua, puedes agregar comentarios a tu código para explicar lo que hace o para dejar notas para ti mismo o para otros programadores. Los comentarios son ignorados por el intérprete de Lua y no afectan la ejecución del programa.

Para escribir un comentario de una sola línea, puedes usar dos guiones (`--`) seguidos del texto del comentario. Por ejemplo:

```lua
-- Este es un comentario de una sola línea
print("¡Hola, Lua!") -- Esto también es un comentario
```

Para escribir un comentario de varias líneas, puedes usar dos guiones seguidos de dos corchetes (`--[[` y `]]`). Por ejemplo:

```lua
--[[
Este es un comentario de varias líneas.
Puedes escribir todo lo que quieras aquí, y el intérprete de Lua lo ignorará.
]]
print("¡Hola, Lua!")
```
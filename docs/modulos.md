# Modulos

En Lua, los módulos son una forma de organizar y reutilizar código. Un módulo es básicamente un archivo que contiene funciones, variables y otros elementos relacionados que pueden ser utilizados en otros archivos. Los módulos permiten encapsular el código y evitar conflictos de nombres entre diferentes partes de un programa.

Para crear un módulo en Lua, simplemente necesitas crear un archivo con el código que deseas incluir en el módulo. Por ejemplo, puedes crear un archivo llamado `miModulo.lua` con el siguiente contenido:

```lua
local miModulo = {}

function miModulo.saludar(nombre)
    print("Hola, " .. nombre .. "!")
end

return miModulo
```

En este ejemplo, hemos creado un módulo llamado `miModulo` que contiene una función `saludar`. Al final del archivo, utilizamos `return miModulo` para devolver el módulo, lo que permite que otros archivos puedan acceder a sus funciones y variables.

Para utilizar el módulo en otro archivo, puedes usar la función `require`. Por ejemplo, en un archivo llamado `main.lua`, puedes escribir lo siguiente:

```lua
local miModulo = require("miModulo")
miModulo.saludar("Lua") -- Imprime: Hola, Lua!
```
En este ejemplo, hemos requerido el módulo `miModulo` y luego hemos llamado a la función `saludar` que se encuentra dentro del módulo, pasando el nombre "Lua" como argumento.

Esto es solo un ejemplo básico de cómo crear y utilizar módulos en Lua. Los módulos pueden contener muchas funciones, variables y otros elementos, lo que te permite organizar tu código de manera eficiente y reutilizarlo en diferentes partes de tu programa.


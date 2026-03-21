# Tablas

Una tabla en Lua es una estructura de datos que puede almacenar una colección de valores. Las tablas son muy flexibles y pueden ser utilizadas para representar arrays, diccionarios, objetos y más. En Lua, las tablas se crean utilizando llaves `{}` y pueden contener cualquier tipo de valor, incluyendo otras tablas.

## Creación de Tablas
Puedes crear una tabla vacía de la siguiente manera:

```lua
local miTabla = {}
```

Una tabla es en sí un array asociativo, lo que significa que puedes usar cualquier tipo de valor como clave para acceder a los elementos de la tabla. Por ejemplo:

```lua
local miTabla = {
    nombre = "Lua",
    version = 5.4,
    esDinamico = true
}
```

En este ejemplo, hemos creado una tabla con tres campos: `nombre`, `version` y `esDinamico`. Puedes acceder a estos campos utilizando la sintaxis de punto (`.`) o la sintaxis de corchetes (`[]`). Por ejemplo:

```lua
print(miTabla.nombre) -- Imprime: Lua
print(miTabla["version"]) -- Imprime: 5.4
```

Como podemos ver en los ejemplos, se accede a cada campo del array como si de una estructura de datos se tratara, utilizando el nombre del campo como clave para obtener su valor. Las tablas en Lua son muy versátiles y se utilizan ampliamente para organizar y manipular datos de manera eficiente.

## Tablas como Arrays
Las tablas también pueden ser utilizadas como arrays, donde las claves son números enteros consecutivos. Por ejemplo:
```lua
local miArray = { "Lua", "Python", "JavaScript" }
```
En este caso, `miArray` es una tabla que contiene tres elementos, y puedes acceder a ellos utilizando índices numéricos:

```lua
print(miArray[1]) -- Imprime: Lua
print(miArray[2]) -- Imprime: Python
print(miArray[3]) -- Imprime: JavaScript
```

En Lua, los índices de los arrays comienzan en 1, a diferencia de otros lenguajes de programación donde los índices comienzan en 0. Esto es importante tenerlo en cuenta al trabajar con tablas como arrays en Lua.

## Tablas como Diccionarios
Las tablas también pueden ser utilizadas como diccionarios, donde las claves son cadenas de texto u otros tipos de datos. Por ejemplo:
```lua
local miDiccionario = {
    nombre = "Lua",
    tipo = "Lenguaje de programación",
    añoCreacion = 1993
}
```
En este caso, `miDiccionario` es una tabla que contiene información sobre el lenguaje de programación Lua, y puedes acceder a sus campos utilizando las claves correspondientes:

```lua
print(miDiccionario.nombre) -- Imprime: Lua
print(miDiccionario.tipo) -- Imprime: Lenguaje de programación
print(miDiccionario.añoCreacion) -- Imprime: 1993
```

En este caso, las tablas se utilizan para almacenar información de manera estructurada, similar a un diccionario en otros lenguajes de programación. Las claves pueden ser cualquier tipo de valor, lo que hace que las tablas sean una herramienta poderosa para organizar datos en Lua.

## Tablas como Objetos
En Lua, las tablas también pueden ser utilizadas para representar objetos, lo que permite organizar datos y comportamientos relacionados en una sola estructura. Por ejemplo:
```lua
local persona = {
    nombre = "Juan",
    edad = 30,
    saludar = function(self)
        print("Hola, mi nombre es " .. self.nombre)
    end
}
```
En este caso, `persona` es una tabla que representa un objeto con campos para el nombre y la edad, así como un método `saludar` que imprime un saludo utilizando el nombre de la persona. Puedes acceder a los campos y métodos del objeto de la siguiente manera:

```lua
print(persona.nombre) -- Imprime: Juan
print(persona.edad) -- Imprime: 30
persona:saludar() -- Imprime: Hola, mi nombre es Juan
```

En este ejemplo, hemos utilizado la sintaxis de dos puntos (`:`) para llamar al método `saludar`, lo que permite que el método acceda a los campos del objeto utilizando `self`. Las tablas en Lua son una herramienta muy flexible para representar objetos y organizar datos relacionados de manera eficiente.

### Operadores con tablas

En Lua, las tablas no tienen operadores aritméticos o de comparación predefinidos, pero puedes definir tus propios operadores utilizando metatables. Las metatables son tablas especiales que permiten personalizar el comportamiento de las tablas, incluyendo cómo se comportan con los operadores.

Por ejemplo, puedes definir un operador de suma para tablas que representen vectores:

```lua
local Vector = {}
Vector.__add = function(a, b)
    return { x = a.x + b.x, y = a.y + b.y }
end
local v1 = { x = 1, y = 2 }
local v2 = { x = 3, y = 4 }
setmetatable(v1, Vector)
setmetatable(v2, Vector)
local v3 = v1 + v2
print(v3.x) -- Imprime: 4
print(v3.y) -- Imprime: 6
```

En este ejemplo, hemos definido una metatable `Vector` con un operador de suma (`__add`) que toma dos tablas y devuelve una nueva tabla con las coordenadas sumadas. Luego, hemos creado dos vectores `v1` y `v2`, les hemos asignado la metatable `Vector`, y finalmente hemos sumado los dos vectores para obtener un nuevo vector `v3`. Las tablas en Lua son muy flexibles y permiten personalizar su comportamiento de muchas maneras utilizando metatables.
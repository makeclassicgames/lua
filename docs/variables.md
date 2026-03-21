# Variables y Tipos de Datos

En Lua, las variables son contenedores que almacenan valores. Lua es un lenguaje de tipado dinámico, lo que significa que no es necesario declarar el tipo de una variable antes de usarla. Puedes asignar cualquier tipo de valor a una variable y cambiarlo en cualquier momento.

Por ejemplo:

```lua
local miVariable = 42        -- Asignando un número
print(miVariable)           -- Imprime: 42
miVariable = "Hola, Lua!"  -- Asignando una cadena de texto
print(miVariable)           -- Imprime: Hola, Lua!
```

En este ejemplo, `miVariable` primero almacena un número y luego se le asigna una cadena de texto. Lua maneja automáticamente el tipo de dato, por lo que no es necesario especificarlo.

## Identificadores en Lua

Los identificadores en Lua son los nombres que se utilizan para referirse a variables, funciones, tablas y otros elementos del programa. Un identificador debe comenzar con una letra (a-z o A-Z) o un guion bajo (_), seguido de cualquier combinación de letras, dígitos (0-9) y guiones bajos. Los identificadores no pueden ser iguales a las palabras reservadas de Lua.

Algunos ejemplos de identificadores válidos son:

```lua
local nombre = "Lua"
local edad = 30
local _contador = 0
```

**NOTA**: Más adelante explicaremos que significa la palabra reservada `local` y cómo afecta el alcance de las variables. Por ahora, lo importante es entender que los identificadores son los nombres que usamos para referirnos a los valores almacenados en las variables.

## Tipos de Datos en Lua

Lua tiene varios tipos de datos incorporados que puedes usar para almacenar diferentes tipos de información. Los tipos de datos básicos en Lua incluyen:

- **nil**: Representa la ausencia de un valor. Es el valor predeterminado de las variables no inicializadas.
- **boolean**: Representa un valor de verdad, que puede ser `true` o `false`.
- **number**: Representa números, tanto enteros como de punto flotante.
- **string**: Representa secuencias de caracteres, como texto.
- **table**: Representa estructuras de datos complejas, como arrays, diccionarios y objetos.
- **function**: Representa funciones, que son bloques de código reutilizables.
- **userdata**: Representa datos personalizados definidos por el usuario, generalmente utilizados para interactuar con bibliotecas externas.
- **thread**: Representa hilos de ejecución, utilizados para la concurrencia.
En Lua, puedes usar la función `type()` para determinar el tipo de dato de una variable. Por ejemplo:

```lua
local miVariable = 42
print(type(miVariable)) -- Imprime: number
miVariable = "Hola, Lua!"
print(type(miVariable)) -- Imprime: string
```

## Cadenas (Strings)

Las cadenas en Lua son secuencias de caracteres que se pueden definir usando comillas simples (`'`) o comillas dobles (`"`). Por ejemplo:

```lua
local saludo = "Hola, Lua!"
local despedida = 'Adiós, Lua!'
print(saludo)    -- Imprime: Hola, Lua!
print(despedida) -- Imprime: Adiós, Lua!
```

Igualmente, puedes usar comillas dobles dentro de una cadena definida con comillas simples, y viceversa, para incluir comillas en el texto sin necesidad de escapar los caracteres. Por ejemplo:

```lua
local mensaje = 'Ella dijo: "¡Hola, Lua!"'
print(mensaje) -- Imprime: Ella dijo: "¡Hola, Lua!"
```

También puedes usar la barra invertida (`\`) para escapar caracteres especiales dentro de una cadena. Por ejemplo:

```lua
local mensaje = "Ella dijo: \"¡Hola, Lua!\""
print(mensaje) -- Imprime: Ella dijo: "¡Hola, Lua!"
```

Los caradteres de escape comunes incluyen:

| Carácter de escape | Descripción |
|--------------------|-------------|
| `\n`               | Nueva línea  |
| `\t`               | Tabulación   |
| `\\`               | Barra invertida |
| `\"`               | Comillas dobles |
| `\'`               | Comillas simples |
| `\r`               | Retorno de carro |
| `\b`               | Retroceso    |
| `\f`               | Avance de página (Formulario) |
| `\a`               | Alerta (sonido) |
| `\v`               | Tabulación vertical |

Además puedes usar código ASCII en formato hexadecimal (`\xXX`) o en formato octal (`\XXX`) para representar caracteres específicos. Por ejemplo:

```lua
local letraA = "\x41" -- Código ASCII para 'A', formato octal.
local letraB = "\66"   -- Código ASCII para 'B'.
print(letraA) -- Imprime: A
print(letraB) -- Imprime: B
```

En Lua, también puedes usar corchetes dobles (`[[` y `]]`) para definir cadenas de texto multilínea sin necesidad de escapar caracteres especiales. Por ejemplo:

```lua
local textoMultilinea = [[
Este es un texto
multilínea en Lua.
Puedes escribir todo lo que quieras aquí,
y el intérprete de Lua lo tratará como una sola cadena.
]]
print(textoMultilinea)
```
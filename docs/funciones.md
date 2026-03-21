# Funciones

Vamos a hablar sobre las funciones en Lua. Las funciones son bloques de código reutilizables que realizan una tarea específica. En Lua, las funciones son de primera clase, lo que significa que pueden ser asignadas a variables, pasadas como argumentos a otras funciones y devueltas como valores desde otras funciones.

## Definición de Funciones

En Lua, puedes definir una función utilizando la palabra clave `function`, seguida del nombre de la función y una lista de parámetros entre paréntesis. El cuerpo de la función se escribe entre `end`. Por ejemplo:

```lua
function saludar(nombre)
    print("Hola, " .. nombre .. "!")
end
saludar("Lua") -- Imprime: Hola, Lua!
```

En este ejemplo, hemos definido una función llamada `saludar` que toma un parámetro `nombre` y imprime un saludo personalizado. Luego, llamamos a la función pasando el argumento "Lua", lo que resulta en la impresión del mensaje de saludo.

## Funciones Anónimas

En Lua, también puedes definir funciones anónimas, que son funciones sin un nombre. Estas funciones se pueden asignar a variables o pasar como argumentos a otras funciones. Por ejemplo:

```lua
local sumar = function(a, b)
    return a + b
end
print(sumar(3, 5)) -- Imprime: 8
```

En este ejemplo, hemos definido una función anónima que suma dos números y la hemos asignado a la variable `sumar`. Luego, llamamos a la función pasando los argumentos 3 y 5, lo que resulta en la impresión del resultado de la suma.

## Funciones con Retorno

Las funciones en Lua pueden devolver valores utilizando la palabra clave `return`. Puedes devolver cualquier tipo de dato, incluyendo múltiples valores. Por ejemplo:

```lua
function dividir(a, b)
    if b == 0 then
        return nil, "Error: División por cero"
    else
        return a / b
    end
end

local resultado, error = dividir(10, 2)

if error then
    print(error)
else
    print("Resultado: " .. resultado) -- Imprime: Resultado: 5
end
```

En este ejemplo, la función `dividir` devuelve el resultado de la división si el divisor no es cero, o devuelve `nil` y un mensaje de error si el divisor es cero. Luego, llamamos a la función y manejamos el resultado y el error de manera adecuada.

### Múltiples valores de retorno

En Lua, una función puede devolver múltiples valores separados por comas. Por ejemplo:

```lua
function coordenadas()
    return 10, 20
end

local x, y = coordenadas()

print("Coordenadas: (" .. x .. ", " .. y .. ")") -- Imprime: Coordenadas: (10, 20)
```

Como vemos en este ejemplo, la función `coordenadas` devuelve dos valores, que luego se asignan a las variables `x` y `y`. Esto es útil para devolver múltiples resultados desde una función sin necesidad de usar tablas u otras estructuras de datos. Puedes observar el operador de concatenación (`..`) para construir la cadena de texto que muestra las coordenadas.

## Funciones Recursivas

Las funciones en Lua también pueden ser recursivas, lo que significa que pueden llamarse a sí mismas para resolver un problema. Por ejemplo, aquí hay una función recursiva para calcular el factorial de un número:

```lua
function factorial(n)
    if n == 0 then
        return 1
    else
        return n * factorial(n - 1)
    end
end

print(factorial(5)) -- Imprime: 120
```

En este ejemplo, la función `factorial` se llama a sí misma con un valor decreciente de `n` hasta que llega a 0, momento en el cual devuelve 1. El resultado es el factorial de 5, que es 120.

## Funciones en tablas

En Lua, las funciones también pueden ser almacenadas en tablas, lo que permite organizar el código de manera más estructurada. Por ejemplo:

```lua
local miTabla = {
    saludar = function(nombre)
        print("Hola, " .. nombre .. "!")
    end,
    sumar = function(a, b)
        return a + b
    end
}
miTabla.saludar("Lua") -- Imprime: Hola, Lua!
print(miTabla.sumar(3, 5)) -- Imprime: 8
```

En este ejemplo, hemos creado una tabla llamada `miTabla` que contiene dos funciones: `saludar` y `sumar`. Luego, llamamos a estas funciones utilizando la sintaxis de acceso a campos de la tabla.


Como hemos visto, las funciones en Lua son una parte fundamental del lenguaje y ofrecen una gran flexibilidad para organizar y reutilizar el código. Ya sea que estés definiendo funciones con nombre, funciones anónimas, funciones recursivas o funciones almacenadas en tablas, Lua te proporciona las herramientas necesarias para trabajar con funciones de manera efectiva.


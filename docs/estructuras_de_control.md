# Estructuras de Control

En esta sección se describen las estructuras de control disponibles en Lua, que se utilizan para controlar el flujo de ejecución de un programa.

## Estructuras de control condicionales

Las estructuras de control condicionales permiten ejecutar diferentes bloques de código según ciertas condiciones. En Lua, las estructuras de control condicionales incluyen `if`, `elseif` y `else`. La sintaxis básica es la siguiente:

```lua
if condición then
    -- Bloque de código a ejecutar si la condición es verdadera
elseif otra_condición then
    -- Bloque de código a ejecutar si la otra condición es verdadera
else
    -- Bloque de código a ejecutar si ninguna de las condiciones anteriores es verdadera
end
```

Por ejemplo:

```lua
local edad = 25
if edad < 18 then
    print("Eres menor de edad.")
elseif edad >= 18 and edad < 65 then
    print("Eres un adulto.")
else
    print("Eres un adulto mayor.")
end
```

En este ejemplo, el programa evalúa la variable `edad` y ejecuta el bloque de código correspondiente según el rango de edad.

## Estructuras de control de repetición

Las estructuras de control de repetición permiten ejecutar un bloque de código varias veces. En Lua, las estructuras de control de repetición incluyen `while`, `repeat` y `for`. La sintaxis básica es la siguiente:

### Estructura `while`

```lua
while condición do
    -- Bloque de código a ejecutar mientras la condición sea verdadera
end
```

### Estructura `repeat`

```lua
repeat
    -- Bloque de código a ejecutar al menos una vez y luego repetidamente mientras la condición sea falsa
until condición
```

### Estructura `for`

```lua
for variable = inicio, fin, paso do
    -- Bloque de código a ejecutar para cada valor de variable desde inicio hasta fin con un incremento de paso
end
```

Por ejemplo:

```lua
-- Usando while
local contador = 1
while contador <= 5 do
    print("Contador: " .. contador)
    contador = contador + 1
end

-- Usando repeat
local numero = 1
repeat
    print("Número: " .. numero)
    numero = numero + 1
until numero > 5
-- Usando for
for i = 1, 5 do
    print("Índice: " .. i)
end
```

En este ejemplo, se muestran las tres estructuras de control de repetición en acción, cada una ejecutando un bloque de código que imprime números del 1 al 5.

### break y continue

En Lua, puedes usar la palabra clave `break` para salir de un bucle antes de que se complete su ejecución. Por ejemplo:

```lua
for i = 1, 10 do
    if i == 5 then
        break -- Sale del bucle cuando i es igual a 5
    end
    print("Índice: " .. i)
end
```

En este ejemplo, el bucle `for` se detiene cuando `i` alcanza el valor de 5, por lo que solo se imprimirán los índices del 1 al 4.

Lua no tiene una palabra clave `continue` para saltar a la siguiente iteración de un bucle, pero puedes lograr un efecto similar utilizando una estructura condicional. Por ejemplo:

```lua

for i = 1, 10 do
    if i % 2 == 0 then
        -- Si i es par, saltamos a la siguiente iteración
        goto continue
    end
    print("Índice impar: " .. i)
    ::continue::
end
```
En este ejemplo, se utiliza `goto` para saltar a la etiqueta `continue` cuando `i` es un número par, lo que hace que solo se impriman los índices impares del 1 al 10.

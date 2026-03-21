# Operadores

En esta sección se describen los operadores disponibles en Lua, que se utilizan para realizar operaciones matemáticas, lógicas y de comparación entre valores.

## Operadores aritméticos

| Operador | Descripción |
|----------|-------------|
| `+`      | Suma        |
| `-`      | Resta       |
| `*`      | Multiplicación |
| `/`      | División     |
| `%`      | Módulo (resto de la división) |
| `^`      | Exponenciación (potencia) |
| `-`      | Negación (unaria) |
| `#`      | Longitud (para cadenas y tablas) |

## Operadores de comparación

| Operador | Descripción |
|----------|-------------|
| `==`     | Igual a      |
| `~=`     | Distinto de  |
| `<`      | Menor que    |
| `>`      | Mayor que    |
| `<=`     | Menor o igual que |
| `>=`     | Mayor o igual que |

## Operadores lógicos

| Operador | Descripción |
|----------|-------------|
| `and`    | Conjunción lógica (y) |
| `or`     | Disyunción lógica (o) |
| `not`    | Negación lógica (no) |

## Precedencia de operadores

En Lua, la precedencia de los operadores determina el orden en que se evalúan las expresiones. La siguiente tabla muestra la precedencia de los operadores, de mayor a menor:

| Precedencia | Operadores |
|-------------|------------|
| 1           | `^`        |
| 2           | `not`, `#`, `-` (unaria) |
| 3           | `*`, `/`, `%` |
| 4           | `+`, `-`   |
| 5           | `..` (concatenación de cadenas) |
| 6           | `<`, `>`, `<=`, `>=`, `~=`, `==` |
| 7           | `and`      |
| 8           | `or`       |

Es importante tener en cuenta la precedencia de los operadores al escribir expresiones complejas para asegurarse de que se evalúen en el orden correcto. Si es necesario, puedes usar paréntesis para cambiar el orden de evaluación y hacer que una parte específica de la expresión se evalúe primero. Por ejemplo:

```lua
local resultado = (3 + 4) * 2 -- Sin paréntesis, se evaluaría como 3 + (4 * 2)
print(resultado) -- Imprime: 14
```

En este ejemplo, los paréntesis aseguran que la suma se realice antes de la multiplicación, lo que da como resultado 14 en lugar de 11.

En resumen, los operadores en Lua son herramientas fundamentales para realizar operaciones matemáticas, lógicas y de comparación. Conocer su funcionamiento y precedencia es esencial para escribir código efectivo y correcto en Lua.

Más adelante, veremos algunos operadores extra usados en diferentes contextos, como el operador de concatenación de cadenas (`..`) y el operador de longitud (`#`), que tienen usos específicos en Lua.
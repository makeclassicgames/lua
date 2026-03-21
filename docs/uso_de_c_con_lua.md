# Uso de C en Lua

Lua es un lenguaje de programación ligero y rápido que se puede integrar fácilmente con código escrito en C. Esto permite a los desarrolladores aprovechar la eficiencia y el rendimiento de C mientras mantienen la flexibilidad y facilidad de uso de Lua. En esta sección, exploraremos cómo usar C con Lua, incluyendo cómo escribir funciones en C que pueden ser llamadas desde Lua, cómo manejar datos entre ambos lenguajes y cómo compilar y ejecutar código C junto con Lua.

## Escribir funciones en C para Lua
Para escribir funciones en C que puedan ser llamadas desde Lua, debes seguir algunos pasos básicos. Primero, necesitas incluir la biblioteca de Lua en tu código C y luego definir las funciones que deseas exponer a Lua. Aquí hay un ejemplo simple de cómo hacerlo:

```c
#include <lua.h>
#include <lauxlib.h>
#include <lualib.h> 

// Función C que será llamada desde Lua
int miFuncion(lua_State *L) {
    // Obtener el número de argumentos pasados desde Lua
    int n = lua_gettop(L);
    // Verificar que se haya pasado al menos un argumento
    if (n < 1) {
        lua_pushstring(L, "Error: Se requiere al menos un argumento");
        return 1; // Retorna el error a Lua
    }
    // Obtener el primer argumento como un número
    double num = luaL_checknumber(L, 1);
    // Realizar alguna operación con el número (por ejemplo, multiplicarlo por 2)
    double resultado = num * 2;
    // Devolver el resultado a Lua
    lua_pushnumber(L, resultado);
    return 1; // Indica que se está devolviendo un valor a Lua
}
```

En este ejemplo, hemos definido una función C llamada `miFuncion` que toma un número como argumento, lo multiplica por 2 y devuelve el resultado a Lua. La función utiliza la API de Lua para interactuar con la pila de Lua, lo que permite obtener argumentos y devolver resultados de manera eficiente.

Veremos más adelante algunas de las funciones utilizadas en este ejemplo, como `lua_gettop`, `luaL_checknumber` y `lua_pushnumber`, que son parte de la API de Lua para manejar la interacción entre C y Lua.

## Compilar y ejecutar código C con Lua

Para compilar y ejecutar código C que utiliza Lua, necesitas tener la biblioteca de Lua instalada en tu sistema. Luego, puedes compilar tu código C utilizando un compilador como `gcc` y enlazando la biblioteca de Lua. Aquí hay un ejemplo de cómo hacerlo:

```
gcc -o miPrograma miPrograma.c -llua
```

Como has podido observar, el comando de compilación incluye la opción `-llua`, que indica al compilador que enlace la biblioteca de Lua. Después de compilar tu programa, puedes ejecutarlo y ver cómo interactúa con Lua.

Pero te preguntarás, ¿cómo se llama a la función `miFuncion` desde Lua? Para hacer esto, necesitas registrar la función C en Lua para que pueda ser llamada como una función normal de Lua. Esto se hace utilizando la función `lua_register` o creando una tabla de funciones y registrándola como un módulo. Aquí hay un ejemplo de cómo registrar la función `miFuncion`:

```c
// Registrar la función en Lua
lua_register(L, "miFuncion", miFuncion);
```

En este ejemplo, estamos registrando la función `miFuncion` con el nombre "miFuncion" en Lua. Esto significa que ahora puedes llamar a esta función desde Lua como si fuera una función nativa de Lua. Por ejemplo, en tu script de Lua, podrías escribir:

```lua
local resultado = miFuncion(5)
print(resultado) -- Imprime: 10
```

En este ejemplo, estamos llamando a la función `miFuncion` desde Lua, pasando el número 5 como argumento. La función C multiplica este número por 2 y devuelve el resultado, que luego se imprime en la consola.

### Manejo de datos entre C y Lua

Cuando trabajas con C y Lua, es importante entender cómo manejar los datos entre ambos lenguajes. Lua utiliza una pila para pasar argumentos y devolver resultados entre C y Lua. La API de Lua proporciona funciones para manipular esta pila, lo que te permite obtener argumentos, devolver resultados y manejar errores de manera eficiente.

Por ejemplo, en la función `miFuncion`, utilizamos `lua_gettop` para obtener el número de argumentos pasados desde Lua, `luaL_checknumber` para verificar que el primer argumento sea un número y obtener su valor, y `lua_pushnumber` para devolver el resultado a Lua. Estas funciones son parte de la API de Lua y te permiten interactuar con la pila de Lua de manera segura y eficiente.

### Cargar una biblioteca C en Lua

Además de registrar funciones individuales, también puedes cargar una biblioteca completa escrita en C en Lua. Esto se hace creando un módulo en C que contiene varias funciones y luego registrando ese módulo en Lua. Aquí hay un ejemplo de cómo crear un módulo en C:

```c
#include <lua.h>
#include <lauxlib.h>
#include <lualib.h>
// Función C que será parte del módulo
int miFuncion(lua_State *L) {
    // ... implementación de la función ...
}
// Función para registrar el módulo
int luaopen_miModulo(lua_State *L) {
    lua_register(L, "miFuncion", miFuncion);
    return 0; // Retorna el número de resultados devueltos a Lua
}
```
En este ejemplo, hemos creado un módulo llamado `miModulo` que contiene la función `miFuncion`. La función `luaopen_miModulo` es la función de inicialización del módulo que se llama cuando el módulo es cargado en Lua. En esta función, registramos la función `miFuncion` para que esté disponible en Lua.

Para cargar este módulo en Lua, puedes usar la función `require` de Lua, que buscará el módulo y lo cargará. Por ejemplo:

```lua
local miModulo = require("miModulo")
local resultado = miModulo.miFuncion(5)
print(resultado) -- Imprime: 10
```

Puedes encontrar más información sobre la API de Lua y cómo manejar datos entre C y Lua en la [documentación oficial de Lua](https://www.lua.org/pil/24.html), que proporciona una referencia completa de todas las funciones disponibles para interactuar con Lua desde C.
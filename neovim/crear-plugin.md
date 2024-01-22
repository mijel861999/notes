# Como crear tu plugin en neovim

Este tutorial lo copié de  

[Neovim Tu primer Plugin !!!](Neovim Tu primer Plugin !!!)  

# Qué es "LUA"

Lua es un lenguaje de programación de scripting ligero, rápido y de propósito general. Es diseñado para ser incorporado en otras aplicaciones como un lenguaje de extensión. Neovim, al igual que Vim, admite la extensión de sus funcionalidades mediante scripting, y Lua se ha convertido en el lenguaje principal para escribir plugins en Neovim.  
  
En el contexto de Neovim, puedes utilizar Lua para personalizar y extender sus funcionalidades de una manera más potente y expresiva que usando Vimscript, que era el lenguaje de scripting principal en Vim. Lua es conocido por su simplicidad, eficiencia y facilidad de integración.  

# Primeros pasos

Para crear tu plugin, al utilizar lua, necesitaremos crear una carpeta con el mismo nombre, y dentro de esta carpeta crear una carpeta con el mismo nombre del plugin, en este caso será "my_plugin", ya dentro de esta carpeta, crearemos el archivo "init.lua". Agregaremos una línea para imprimir

```print"Hola mundo")```    
Para que se corra este arhivo, necesitaremos agregarlo al runpath de neovim, lo haremos con este comando

```set runpath+=./```

O al iniciar neovim, puedes ingresarlo con este comando

```nvim -c "set rtp+=./"```  
Ahora, para correr este plugin, lo que haremos será escribir este comando

```lua requrie("nombre_plugin")```

Si intentamos ejecutar esto por segunda vez, veremos que no funciona el print. Necesitaremos hacer que neovim olvide nuestro plugin y volver a cargarlo. Para ver si está cargado el plugin utilizaremos este comando

```lua print(package.loaded["nombre_plugin")]))```

# Recuperación de contraseña

Primero, se necesita una tabla intermedia para poder almacenar un token y el id o correo del usuario, esto para poder saber la valides del enlace para el cambio de contraseña. A continuación los pasos

1. Cuando presiona en olvide contraseña. Generar token y almacenarlo en la nueva tabla que comentamos.
2. Enviar el correo de recuperación de contraseña con el token en la url.
3. Dentro de la vista del url que enviamos, hacer la comprobación si el token es válido o no, si no es válido mostrar mensaje de error.
4. Hacer el cambio de la contraseña.
5. Hacer la redirección del login.

# Laravel

Tendremos que dividir los métodos y rutas según cada paso.

## Primer método - Generar Token - Paso 1

Método que recibe el email del usuario, corrobora que exista, si existe genera un item en la tabla de recover_password, sino, retorna una respuesta negativa.

## Segundo método - Envio de correo - Paso 2

Método que envia un correo de recuperación con el token en el enlace.

## Tercer método - Comprobar que el token no ha expirado - Paso 3

Método que recibe el token, este comprueba si es válido todavía, si no es válido, enviar mensaje de error.

## Cuarto método - Cambio de contraseña - Paso 4

Método que recibe la nueva contraseña y hace el cambio, esta contraseña debe ir encriptada.

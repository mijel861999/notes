# Qué se necesita?  

Para enviar un correo por laravel, o en general, para cualquier framework y lenguaje de programación, necesitaremos un correo electrónico, este correo electrónico necesitará una contraseña especial que es generada para aplicaciones.

# Routes

En las rutas crearemos una para el envio del correo, es una ruta cualquiera.

# Controlador

Para el controlador crearemos una función con una caracteristica especial.
```

public function sendEmail(Request $request) {
        
        foreach(['mijel.dev@gmail.com'] as $recipient) {
            Mail::to($recipient)->send(new recuperarContrasenaMail());
        }

        return response([
            "ok" => true,
            "message" => "Envío exitoso",
            ], HttpFoundationResponse::HTTP_OK);   
    }
```


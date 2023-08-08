# Respuestas

Indica tu nombre a continuación: César Soto Barrera

Por cada etapa agrega una sección abajo y escribe las respuestas a las preguntas de cada etapa.

## ETAPA 1

¿Cuál es la diferencia entre los archivos con el verbo `Create` con los archivos con el verbo `Add`?

R: Los archivos con el verbo Create crean las tablas de la base de datos.
R: Los archivos con el verbo Add permiten agregar datos a las tablas ya creadas. 

¿Cómo se llama el servicio que se declara en el archivo `docker-compose.yml`?

R: El servicio se llama 'flyway'

¿Cuál es el comando que se ejecuta en el servicio declarado?

R: el comando es el 'migration' que escanea los archivos .sql y los ejecuta. 

## ETAPA 2

¿Qué pasa si cambias el nombre del servicio de `postgres` a `db`? ¿Qué otros cambios tendrías que hacer?

R: Si se cambia a db todas las referencias al servicio postgres dejarán de funcionar. 
R: Se debería actualizar la variable de entorno "POSTGRES_SERVER", el depends_on del servicio "flyway".
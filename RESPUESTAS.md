# Respuestas

Indica tu nombre a continuación: César Soto Barrera

Por cada etapa agrega una sección abajo y escribe las respuestas a las preguntas de cada etapa.

## ETAPA 1

¿Cuál es la diferencia entre los archivos con el verbo Create con los archivos con el verbo Add?

R: Los archivos con el verbo Create crean las tablas de la base de datos. R: Los archivos con el verbo Add permiten agregar datos a las tablas ya creadas.

¿Cómo se llama el servicio que se declara en el archivo docker-compose.yml?

R: El servicio se llama 'flyway'

¿Cuál es el comando que se ejecuta en el servicio declarado?

R: el comando es el 'migration' que escanea los archivos .sql y los ejecuta.

## ETAPA 2

¿Qué pasa si cambias el nombre del servicio de postgres a db? ¿Qué otros cambios tendrías que hacer?

R: Si se cambia a db todas las referencias al servicio postgres dejarán de funcionar. R: Se debería actualizar la variable de entorno "POSTGRES_SERVER", el depends_on del servicio "flyway".

## ETAPA 3

Revisa el archivo movies-api/Dockerfile.

¿Qué te llama la atención?

R: Que tiene una secuencia de instrucciones para obtener construir la aplicación desde los fuentes de la y otra para ejecutar el deploy.

Revisa el archivo docker-compose.yml.

¿Cómo se relacionan el archivo docker-compose.yml y el archivo movies-api/Dockerfile?

R: en context del build del docker-compose.yml se especifica el directorio donde se obtendrá la imagen de la aplicación, que en el dockerfile se define cómo construir y dónde estará disponible. Es el directorio ./movies-api

¿Qué crees que hace el atributo context debajo de build (está en la linea 6 del archivo docker-compose.yml)?

R: context define un directorio en el cual se ubicará el recurso que permita construir la imagen. En este caso el dockerfile.

## ETAPA 4

Compara los archivos `Dockerfile` de `movies-api` y `movies-front`. 

Compara el atributo `build` del servicio `movies-api` con el de `movies-front`. 

¿Cuál es la diferencia? 

R: que en cada caso en el build se indica la ruta desde la cual docker-compose tomará los recursos para construir la imagen con la especificación del dockerfile. 
En el caso de build: movies-front indica que en el directorio del proyecto en la carpeta "movies-front" está los elementos para construir la imagen de movies-front. En este caso es un directorio pero podría ser una url de github por ejemplo. 
En el caso de context: ./movies-api especifica la ruta especifica de dentro del directorio del proyecto donde se encuentran los recursos y el archivo dockerfile para construir la imagen. 

¿Qué pasa si los dejas iguales?

Si quedan como build: movies-front y build: movies-api funcionará igualmente, ya que ambos directorios están en la carpeta padre del proyecto. 
Si ambos quedan con context: ./movies-front y context: ./movies-api en el build, igual funcionará porque es lo mismo que en el caso anterior. 
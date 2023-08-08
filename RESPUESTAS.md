# Respuestas

Indica tu nombre a continuación: César Soto Barrera

Por cada etapa agrega una sección abajo y escribe las respuestas a las preguntas de cada etapa.

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
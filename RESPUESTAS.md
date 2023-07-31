# Respuestas

Indica tu nombre a continuación: Eduardo Galaz

Por cada etapa agrega una sección abajo y escribe las respuestas a las preguntas de cada etapa.

## ETAPA 1

Revisa el contenido del diretorio sql_migrations.

¿Cuál es la diferencia entre los archivos con el verbo `Create` con los archivos con el verbo `Add`?

**R**: El verbo `Create` se encarga de crear la tabla en la base de datos, definiendo sus atributos y los tipos de datos de estos últimos. En cambio, el verbo `Add` se encarga de almacenar nuevos registros en las tablas.

Revisa el contenido del archivo `docker-compose.yml`. 

¿Cómo se llama el servicio que se declara en el archivo `docker-compose.yml`?

**R**: El servicio se llama `flyway`.

¿Cuál es el comando que se ejecuta en el servicio declarado?

**R**: El comando ejecutado en el servicio `flyway` es `-locations=filesystem:/flyway/sql -connectRetries=60 migrate`.

## ETAPA 2

¿Qué pasa si cambias el nombre del servicio de `postgres` a `db`? ¿Qué otros cambios tendrías que hacer?

**R**: Al cambiar el nombre del servicio `postgres` por `db` también se debiese cambiar el nombre de la dependencia del servicio `flyway`, ya que esta última está relacionada con `postgres`. Adicionalmente, se debe modificar el valor de la variable `POSTGRES_SERVER` encontrada en el archivo `.env`.

## ETAPA 3

Revisa el archivo `movies-api/Dockerfile`.

¿Qué te llama la atención?

**R**: Que posee las instrucciones para compilar y desplegar la aplicación `movies-api`. Para la compilación utiliza Go, mientras que para el despliegue utiliza Debian.

Revisa el archivo `docker-compose.yml`.

¿Cómo se relacionan el archivo `docker-compose.yml` y el archivo `movies-api/Dockerfile`?

**R**: Se relacionan a partir del servicio `movies-api` declarado en `docker-compose.yml`, ya que dicho servicio utiliza las instrucciones de `movies-api/Dockerfile` para crear una imagen personalizada.

¿Qué crees que hace el atributo `context` debajo de `build` (está en la linea 6 del archivo `docker-compose.yml`)?

**R**: Ejecuta la ruta del directorio `./movies-api` donde se encuentra el `Dockerfile` con las instrucciones de una imagen personalizada.

## ETAPA 4

Compara los archivos `Dockerfile` de `movies-api` y `movies-front`. 

¿Cuál es la diferencia? 

**R**: Los lenguajes utilizados son muy distintos. Por lo cual, conllevan a que se deban realizar distintos pasos. 
El frontend (`movies-front`) solo requiere compilar sin necesidad de crear un binario o que se deba desplegar. En cambio, el backend (`movies-api`) requiere construirse y desplegarse. 

Compara el atributo `build` del servicio `movies-api` con el de `movies-front`. 

¿Qué pasa si los dejas iguales?

**R**: No habría problemas, ya que ambas formas son correctas para llamar a ruta que contiene el `Dockerfile`.
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
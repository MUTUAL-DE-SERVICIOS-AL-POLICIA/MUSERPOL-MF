## Dev

1. Clonar el repositorio
2. Crear un .env basado en el .env.example
3. Ejecutar  el comando `git submodule update --init --recursive` para reconstruir los sub-modulos
4. para cada sub-modulo crear un .env basado en su propio .env. example
5. Ejecutar el comando `docker compose build --no-cache && docker compose up`

## Pasos para añadir/crear los Git Submodules (un nuevo microservicio)

1. Crear un nuevo repositorio en GitHub
2. Copiar el Url de nuevo repositorio y añadir en el clonado del repositorio padre MUSERPOL-MS local ejecutar:

git submodule add <repository_url> <directory_name>

3. Añadir los cambios al repositorio  MUSERPOL-MS (git add, git commit, git push) Ej:

git add .
git commit -m "Add submodule"
git push

## Pasos después de clonar el repositorio MUSERPOL-MS

1. Inicializar y actualizar Sub-módulos, cuando alguien clona el repositorio por primera vez, debe de ejecutar el siguiente comando para inicializar y actualizar los sub-módulos

git submodule update --init --recursive

2. Para actualizar las referencias de los sub-módulos

git submodule update --remote

## Importante

Si se trabaja en el repositorio que tiene los sub-módulos, primero actualizar y hacer push en el sub-módulo y después en el repositorio principal.

Si se hace al revés, se perderán las referencias de los sub-módulos en el repositorio principal y tendremos que resolver conflictos.

## Prod

Ejecutar

```
docker compose -f docker-compose.prod.yml build --no-cache && docker compose -f docker-compose.prod.yml up -d

```
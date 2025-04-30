## LEVANTAR PROYECTOS CON DOCKER COMPOSE

## PASOS PARA LEVANTAR EL PROYECTO

1. Clonar el repositorio forkeado e ingresar a la misma

```
cd MUSERPOL-MF
```

2. Crear un .env basado en el .env.example y llenar las variables de entorno correspondientes

```
cp .env.example .env
```

3. Ejecutar el siguiente comando para reconstruir los sub-modulos

```
git submodule update --init --recursive
```

## DESPUÉS DE CREAR LOS SUB MÓDULOS INGRESAR A CADA UNO Y REALIZAR LO SIGUIENTE

4. Crear un .env basado en su propio .env. example y llenar las variables de entorno correspondientes para cada sub módulo o proyecto frontend

```
cd beneficiary-frontend
```

```
cp .env.example .env
```

Configurar las variables de entorno correspondientes y salir `cd ..`

```
cd login-hub-frontend
```

```
cp .env.example .env
```

Configurar las variables de entorno correspondientes y salir `cd ..`

## DESPUÉS DE CONFIGURAR TODAS LOS .ENVS LEVANTAR CON DOCKER PARA VERSIÓN DEV - DESARROLLO

5. Comando para construir las imágenes y levantar los contenedores

```
docker compose build --no-cache && docker compose up
```

## DESPUÉS DE CONFIGURAR TODAS LOS .ENVS LEVANTAR CON DOCKER PARA VERSIÓN PROD - PRODUCCIÓN

5. Comando para construir las imágenes y levantar los contenedores en producción

```
docker compose -f docker-compose.prod.yml build --no-cache && docker compose -f docker-compose.prod.yml up -d
```

## ////////////////////////////////////

## PARA EMPEZAR A COLABORAR

Cuando ya se tiene el los sub módulos se debe ingresar a cada uno y realizar lo siguiente

```
cd beneficiary-frontend
```

```
checkout main
```

```
git remote add origin https://github.com/{nombre_colaborador}/beneficiary-frontend.git
git remote add upstream https://github.com/MUTUAL-DE-SERVICIOS-AL-POLICIA/beneficiary-frontend.git
```

Para redirigir a la rama principal `cd ..`

```
cd login-hub-frontend
```

```
checkout main
```

```
git remote add origin https://github.com/{nombre_colaborador}/login-hub-frontend.git
git remote add upstream https://github.com/MUTUAL-DE-SERVICIOS-AL-POLICIA/login-hub-frontend.git
```

Y PODRÁN REALIZAR LOS PULL REQUEST COMO SE HACE REGULARMENTE DE LOCAL -> REPOSITORIO PERSONAL -> REPOSITORIO PRINCIPAL

## /////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

## CUANDO SE CREA UN NUEVO PROYECTO FRONTEND Y SE REQUIERA AÑADIR AL REPOSITORIO PRINCIPAL COMO SUB MÓDULO REALIZAR LO SIGUIENTE

## Pasos para añadir/crear los Git Submodules (un nuevo frontend)

1. Copiar el URL del nuevo repositorio y añadir en el clonado del repositorio padre MUSERPOL-MS local ejecutar:

```
git submodule add <enlace_del_nuevo_repositorio> <nombre_de_carpeta>
```

2. Añadir los cambios al repositorio MUSERPOL-MF (git add, git commit, git push) Ej:

git add .
git commit -m "Add submodule"
git push

3. Realizar un pull request

## ///////////////////////////////////////

INSTALACIÓN INDEPENDIENTE

Para levantar los proyectos de forma independiente sin docker compose
revisar los README de cada sub módulo ubicados en su repositorio.

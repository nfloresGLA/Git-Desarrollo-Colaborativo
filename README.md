# Github - EducacionIT.

## Configuracion __inicial__ (Primera vez post instalacion)

``` js
1. Configurar el nombre de usuario de manera global.
> git config --global user.name "nombre de usuario"

2. Configurar el email del usuario de manera global.
> git config --global user.email "mail@mail.com"

2.5 (Opcional) Verificacion de los datos anteriores.
> git config user.name 
> git config user.email

Esto nos mostrara el nombre / email asignados.
```

## Configuracion inicial de __cada repositorio__
``` js
1. En la carpeta que elijamos como Repositorio Local. *
> git init
> git remote add origin "link generado por git del repositorio"

// *. Hay que realizarlos <una sola vez> por repositorio
``` 

## Configuracion continua de cada repositorio
``` js
1. Ver el estado de nuestros archivos. (Cargados y no cargados)
> git status (Working directory)

2. Agregar archivos al <Staging area>.
> git add <nombre archivo/s>

3. Agregar archivo/s al tracked.
> git commit -m "Mensaje descriptivo del commit"

4. Guardar los archivos trackeados al repositorio remoto.
> git push origin rama
``` 
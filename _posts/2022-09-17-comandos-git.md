---
title: Comandos Git que todo desarrollador debe saber
published: true
---

 Si estamos trabajando en un proyecto o pretendemos tener una web en Git el saber estos comandos nos ayudara bastante, dejo esta lista a la cual considero son los comandos basicos por aprender, existen otros mas pero estos "creo yo" son los mas importantes.

## Git Clone

clona un repositorio tal cual

 ```bash
git clone <https://link-con-nombre-del-repositorio>

``` 
## Git Branch

Para manejar las *ramas* (muy importante)

```bash
git branch <nombre de la rama>

```

### Listar las ramas existentes

```bash
git branch --list

```

### Borrar una rama

```bash
git branch -d <nombre de la rama>

```
### Cambiarte a otra rama

```bash
git branch -b <nombre de la rama>

```
# Git Add

Con este comando agregas los archivos a los que has realizado cambios

```bash 
git add <archivo>

```

## Agregar todo de una vez

Lo mismo que el anterior, solo que aqui agregas todo de golpe.

```bash 
git add -A

```

# Git Commit
Comentario despues de haber realizado los cambios necesarios

```bash 
git commit -m "comentario"

```

# Git Push
Con este comando subes los cambios al repo, esto puede tardar unos minutos en visualizarse

```bash 
git push <link del repo> <nombre de la rama>

```

ejemplo:

```bash 
git push https://github.com/vegatronica/vegatronica.github.io master

```

### Otra forma

```bash
git push -u origin <nombre-de-tu-rama>

```


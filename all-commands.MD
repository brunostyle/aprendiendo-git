# Git Commands Cheat Sheet

## LOG

- **git log**  
  Muestra una lista de commits.

- **git log -[numero]**  
  Limita la cantidad de commits.

- **git log --author=[autor]**  
  Muestra solo commits hechos por un autor específico.

- **git log --grep=[palabra]**  
  Busca commits que contengan una palabra en el mensaje.

- **git log --since=["DD-MM-YYYY"] --until=["DD-MM-YYYY"]**  
  Muestra commits entre dos fechas específicas.

- **git log --oneline**  
  Muestra cada commit en una línea.

- **git log --graph**  
  Muestra un gráfico ASCII del árbol de ramas.

- **git log --all**  
  Muestra commits de todas las ramas.

- **git log --pretty=format:"%h - %an - %s - %ar"**  
  Da una vista compacta y legible:  
  **%h**: hash corto, **%an**: autor, **%s**: mensaje, **%ar**: tiempo relativo

## BRANCH

- **git branch**  
  Lista ramas locales.

- **git branch -r**  
  Lista ramas remotas.

- **git branch -a**  
  Lista todas las ramas.

- **git branch -v**  
  Muestra el último commit de cada rama local.

- **git switch -c nueva-rama**  
  Crea y cambia a nueva rama.

- **git switch [nombre rama]**  
  Cambia de rama.

- **git branch -d / -D [nombre rama]**  
  Elimina la rama (normal / forzado).

- **git branch -m [nombre nuevo]**  
  Renombra la rama actual.

- **git branch -m [nombre viejo] [nombre nuevo]**  
  Renombra otra rama.

- **git branch --merged**  
  Ver ramas que ya fueron fusionadas a la actual.

- **git branch --no-merged**  
  Ver ramas que no han sido fusionadas.

## RESTORE

- **git restore [nombre archivo]**  
  Restaura archivo desde staging o commit.

- **git restore --source=[nombre rama o commit] [nombre archivo]**  
  Restaura archivo desde otra rama.

## COMMIT

- **git commit -m [mensaje]**  
  Guarda una instantánea del estado actual del proyecto en el historial de Git.

- **git add .**  
- **git commit --amend**  
  Permite modificar el último commit, ya sea el mensaje o añadir archivos olvidados.
  
- **git add .**  
- **git commit --amend --no-edit**  
  Mantiene el mensaje anterior tal cual, útil para agregar un archivo que olvidaste.

## LS-TREE

- **git ls-tree -r --name-only HEAD**  
  Lista todos los archivos que tiene el ultimo commit

- **git ls-tree -r --name-only [id commit]**  
  Lista todos los archivos que tiene un commit determinado

- **git ls-tree HEAD:src/**  
  Lista el contenido de la carpeta src/ en el último commit

## RESET

- **git reset --soft HEAD~1**  
  Elimina el último commit, pero conservar los cambios en el área de staging

- **git reset --mixed HEAD**  
  Deshace el git add sin perder los cambios

- **git reset --hard HEAD~1**  
  Elimina el ultimo commit

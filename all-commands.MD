# Git Commands Cheat Sheet

## LOG

- **git log**  
  Muestra una lista de commits.

- **git log -1**  
  Muestra el último commit.

- **git log -n [numero]**  
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

- **git commit --amend**  
  Permite modificar el último commit, ya sea el mensaje o añadir archivos olvidados.

- **git commit --amend --no-edit**  
  Mantiene el mensaje anterior tal cual, útil para agregar un archivo que olvidaste.

## PRUEBA

- **nueva rama**  
  (Nota: Este comando parece incompleto o es un comentario)
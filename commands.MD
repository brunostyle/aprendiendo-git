# Comandos de Git

## 📦 Repositorio y configuración
- **GIT INIT**
  - **git init**  
    Inicializa un nuevo repositorio Git en un directorio

- **GIT CLONE**
  - **git clone [url]**  
    Copia un repositorio remoto a tu máquina local
  - **git clone --depth [numero] [url]**  
    Clona solo los últimos n commits
  - **git clone --branch [nombre] [url]**  
    Clona directamente una rama específica

- **GIT CONFIG**
  - **git config --list**  
    Muestra todas las configuraciones actuales
  - **git config --global -e**  
    Muestra las configuraciones hechas por el usuario
  - **git config --global user.name [nombre]**  
    Define el nombre de usuario que se usará en todos los repos (a nivel global).
  - **git config --global user.email [email]**  
    Define el correo que se usará en todos los repos (a nivel global).
  - **git config user.name [nombre]**  
    Define el nombre solo para el repositorio actual.
  - **git config user.email [email]**  
    Define el email solo para el repositorio actual.
  - **git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)%an%C(reset) - %C(dim white)(%ar)%C(reset) - %C(bold white)%s%C(reset) %C(bold yellow)%d%C(reset)' --all"**  
    Configura un alias para git log
  - **git config --global init.defaultBranch main**  
    Cambiar el nombre de la rama principal por defecto
  - **git config --global pull.ff only**  
    Configura git pull para que use fast-forward por defecto cuando sea posible
  - **git config --global core.editor "code --wait"**  
  - **git config --global -e**  
    Establece visual studio code como editor de configuración de git
  - **git config --global core.autocrlf true**  
    Estandariza los saltos de línea en windows
  - **git config --global core.autocrlf input**  
    Estandariza los saltos de línea en linux/mac

---

## 📄 Archivos y cambios
- **GIT ADD**
  - **git add [nombre-archivo]**  
    Agrega archivos o cambios específicos al staging area
  - **git add .**  
    Agrega todos los cambios del directorio actual y subdirectorios al staging area

- **GIT RESTORE**
  - **git restore [nombre-archivo]**  
    Restaura archivo desde staging o commit.
  - **git restore --source=[nombre rama o commit] [nombre archivo]**  
    Restaura archivo desde otra rama.
---

## 📥 Confirmaciones (commits)
- **GIT COMMIT**
  - **git commit -m [mensaje]**  
    Guarda una instantánea del estado actual del proyecto en el historial de Git.
  - **git commit --amend -m**  
    Permite modificar el mensaje del último commit
  - **git commit --amend --no-edit**  
    Mantiene el mensaje anterior, útil para agregar un archivo que olvidaste.

- **GIT STATUS**
  - **git status**  
    Muestra el estado actual del directorio de trabajo y del área de preparación
  - **git status --short**  
    Muestra el estado actual del directorio de trabajo y del área de preparación resumido

- **GIT RESET**
  - **git reset --soft HEAD~1**  
    Elimina el último commit, pero conservar los cambios en el área de staging
  - **git reset --mixed HEAD**  
    Deshace el git add sin perder los cambios
  - **git reset --hard HEAD~1**  
    Elimina el ultimo commit

- **GIT REVERT**
  - **git revert [hash]**  
    Crea un nuevo commit que revierte los cambios introducidos por un commit anterior
  - **git revert --continue**  
    Continúa con el revert después de resolver conflictos manualmente
  - **git revert --abort**  
    Cancela un revert en proceso y vuelve al estado anterior
  - **git revert --no-edit [hash]**  
    Mantiene el mensaje anterior
    
---

## 🕓 Historial
- **GIT LOG**
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

- **GIT SHORTLOG**
  - **git shortlog**  
    Ideal para ver quién ha contribuido y cuántos commits hizo
  - **git shortlog -se**  
    Ver solo la cantidad de commits por autor y email

- **GIT SHOW**
  - **git show**  
    Muestra el último commit (mensaje, autor, fecha, y cambios realizados)
  - **git show [hash]**  
    Muestra un commit específico por hash
  - **git show --name-only --oneline**  
    Muestra solo los nombres de archivos modificados.
  - **git show --name-status --oneline**  
    Muestra el nombre de archivos y el tipo de cambio
      - A = Agregado
      - M = Modificado
      - D = Eliminado

- **GIT LS-TREE**
  - **git ls-tree -r --name-only HEAD**  
    Lista todos los archivos que tiene el ultimo commit
  - **git ls-tree -r --name-only [id-commit]**  
    Lista todos los archivos que tiene un commit determinado
  - **git ls-tree HEAD:src/**  
    Lista el contenido de la carpeta src/ en el último commit

- **GIT BLAME**
  - **git blame [nombre-archivo]**  
    Muestra quién modificó cada línea de un archivo

- **GIT REFLOG**
  - **git reflog**  
    Muestra el historial de cambios en referencias

---

## 🌿 Ramas
- **GIT BRANCH**
  - **git branch**  
    Lista ramas locales.
  - **git branch -r**  
    Lista ramas remotas.
  - **git branch -a**  
    Lista todas las ramas.
  - **git branch -v**  
    Muestra el último commit de cada rama local.
  - **git branch -d / -D [nombre-rama]**  
    Elimina la rama (normal / forzado).
  - **git branch -m [nombre-nuevo]**  
    Renombra la rama actual.
  - **git branch -m [nombre-viejo] [nombre-nuevo]**  
    Renombra otra rama.
  - **git branch --merged**  
    Ver ramas que ya fueron fusionadas a la actual.
  - **git branch --no-merged**  
    Ver ramas que no han sido fusionadas.

- **GIT SWITCH**
  - **git switch -c [nombre-rama]**  
    Crea y cambia a nueva rama.
  - **git switch [nombre-rama]**  
    Cambia de rama.

- **GIT MERGE**
  - **git merge [nombre-rama]**  
    combina los cambios de una rama en otra
  - **git merge --continue**  
    Continúa con el merge después de resolver conflictos manualmente
  - **git merge --abort**  
    Cancela un merge en proceso
  - **git merge --ff-only [nombre-rama]**  
    Solo permite el merge si se puede hacer como fast-forward, si no es posible, aborta el merge. Útil para mantener historiales lineales

- **GIT REBASE**
  - **git rebase [nombre-rama]**  
    Mueve los commits de una rama y los aplica sobre la rama en la que estas ubicado
  - **git rebase --continue**  
    Continúa un rebase interrumpido por conflictos
  - **git rebase --abort**  
    Cancela un rebase en proceso y vuelve al estado anterior
  - **git rebase -i HEAD~[numero]**  
    Rebase interactivo: te permite reordenar, modificar, combinar o eliminar commits.

- **GIT CHERRY-PICK**
  - **git cherry-pick [hash]**  
    Aplica uno o más commits específicos desde otra rama a la rama actual
  - **git rebase --continue**  
    Continúa el cherry-pick interrumpido por conflictos
  - **git rebase --abort**  
    Cancela el cherry-pick en proceso y vuelve al estado anterior
  - **git cherry-pick --no-commit [hash]**  
    Aplica los cambios al working directory y staging, pero no hace commit
    
---

## 📁 Cambios temporales (Stash)
- **GIT STASH**
  - **git stash**  
    Guarda todos los cambios actuales y limpia el directorio
  - **git stash push -m [mensaje]**  
    Guarda cambios con un mensaje personalizado
  - **git stash pop**  
    Aplica y elimina el stash más reciente
  - **git stash apply stash@{[numero]}**  
    Aplica los cambios de un stash específico (pero no lo borra de la pila)
  - **git stash drop stash@{[numero]}**  
    Elimina un stash específico
  - **git stash list**  
    Muestra todas las stashes guardadas
  - **git stash show**  
    Muestra los cambios del stash más reciente
  - **git stash clear**  
    Elimina todos los stashes guardados

---

## 🔍 Comparación y búsqueda
- **GIT GREP**
  - **git grep [texto]**  
    Busca todas las líneas que contengan una palabra en el proyecto
  - **git grep [texto] -- [archivo]**  
    Busca solo en archivos específicos
  - **git grep [texto] HEAD**  
    Busca en el ultimo commit
  - **git grep [texto] [hash]**  
    Busca en un commit específico
  - **git grep [texto] [rama]**  
    Busca en una rama especifica
  - **git grep -i [texto]**  
    Ignora mayúsculas/minúsculas
  - **git grep -w [texto]**  
    Coincidencias exactas de palabras
  - **git grep --count [texto]**  
    Muestra solo la cantidad de coincidencias por archivo

---

## 🔄 Sincronización remota
- **GIT REMOTE**
  - **git remote**  
    Muestra una lista de nombres de remotos configurados
  - **git remote -v**  
    Muestra los remotos con sus URLs y si se usan para fetch o push
  - **git remote show [nombre]**  
    Muestra detalles de un remoto
  - **git remote add [nombre] [url]**  
    Agrega un nuevo remoto
  - **git remote remove [nombre]**  
    Elimina un remoto
  - **git remote rename [viejo] [nuevo]**  
    Cambia el nombre de un remoto
    
- **GIT FETCH**
  - **git fetch**  
    Obtiene los cambios más recientes sin aplicarlos directamente a la rama actual
  - **git fetch --prune**  
    Limpia referencias remotas locales obsoletas

- **GIT PULL**
  - **git pull**  
    Actualiza tu rama local con los cambios más recientes del repositorio remoto
  - **git pull --rebase**  
    En lugar de hacer un merge, aplica los cambios del remoto sobre tu trabajo local mediante rebase, manteniendo un historial más limpio
  - **git pull --ff-only**  
    Solo permite la integración si se puede hacer con fast-forward. Falla si no es posible.

- **GIT PUSH**
  - **git push -u origin main**  
    Establece una relación de seguimiento entre tu rama local y la rama remota. Después de usarla una vez, basta con git push sin argumentos
  - **git push**  
    Se utiliza para subir los cambios locales (commits) a un repositorio remoto
  - **git push --force**  
    Forza el push, sobrescribiendo el historial remoto. ⚠️ ¡Peligroso si otros trabajan sobre la misma rama!
  - **git push --tags**  
    Empuja todas las etiquetas locales al remoto
  - **git push origin --delete [nombre-rama]**  
    Elimina una rama remota
    
---
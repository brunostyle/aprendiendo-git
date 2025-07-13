# Comandos de Git

## 📦 Repositorio y configuración
- **GIT INIT**
  - **git init**  
    Inicializa un nuevo repositorio Git vacío en el directorio actual

- **GIT CLONE**
  - **git clone [url]**  
    Copia un repositorio remoto completo en tu máquina local
  - **git clone --depth [numero] [url]**  
    Clona solo los últimos n commits del repositorio remoto
  - **git clone --branch [nombre] [url]**  
    Clona directamente una rama específica del repositorio remoto

- **GIT CONFIG**
  - **git config --global --list**  
    Muestra todas las configuraciones actuales de Git
  - **git config --global -e**  
    Abre el archivo de configuración global en el editor predeterminado
  - **git config --global user.name [nombre]**  
    Establece tu nombre global para todos los repositorios
  - **git config --global user.email [email]**  
    Establece tu email global para todos los repositorios
  - **git config user.name [nombre]**  
    Establece tu nombre local solo para el repositorio actual
  - **git config user.email [email]**  
    Establece el email local solo para el repositorio actual
  - **git config --global init.defaultBranch main**  
    Configura "main" como la rama por defecto en nuevos repositorios
  - **git config --global pull.ff only**  
    Configura git pull para que use fast-forward por defecto cuando sea posible
  - **git config --global core.editor "code --wait"**  
    Establece Visual Studio Code como el editor predeterminado de Git
  - **git config --global core.autocrlf true**  
    Normaliza los saltos de línea en entornos Windows
  - **git config --global core.autocrlf input**  
    Normaliza los saltos de línea en Linux/Mac

---

## 📄 Archivos y cambios
- **GIT ADD**
  - **git add [nombre-archivo]**  
    Agrega un archivo específico al staging area para incluirlo en el próximo commit
  - **git add .**  
    Agrega todos los archivos nuevos o modificados del directorio actual y subdirectorios al staging area

- **GIT RESTORE**
  - **git restore [nombre-archivo]**  
    Restaura el contenido del archivo desde el último commit
---

## 📥 Confirmaciones (commits)
- **GIT COMMIT**
  - **git commit -m [mensaje]**  
    Crea un nuevo commit con los cambios agregados al staging area y asigna un mensaje descriptivo
  - **git commit -am [mensaje]**  
    Agrega los archivos modificados ya rastreados al staging area y hace el commit con el mensaje indicado
  - **git commit --amend -m [mensaje]**  
    Modifica el último commit, reemplazando su mensaje
  - **git commit --amend --no-edit**  
    Mantiene el mensaje anterior, útil para agregar archivos que olvidaste

- **GIT STATUS**
  - **git status**  
    Muestra el estado actual del directorio de trabajo y del staging area
  - **git status --short**  
    Muestra el estado actual del directorio de trabajo y del staging area resumido

- **GIT RESET**
  - **git reset --soft HEAD~1**  
    Elimina el último commit, pero conservar los cambios en el staging area
  - **git reset --mixed HEAD**  
    Deshace el git add, quitando los cambios del staging area, pero manteniéndolos en el directorio de trabajo
  - **git reset --hard HEAD~1**  
    Elimina el último commit y descarta todos los cambios realizados 

- **GIT REVERT**
  - **git revert [hash]**  
    Crea un nuevo commit que revierte los cambios introducidos por un commit anterior
  - **git revert --continue**  
    Continúa con el revert interrumpido por conflictos
  - **git revert --abort**  
    Cancela un revert en proceso y vuelve al estado anterior
  - **git revert --no-edit [hash]**  
    Crea un nuevo commit que revierte los cambios introducidos por un commit anterior pero mantiene el mensaje anterior

---

## 🕓 Historial
- **GIT LOG**
  - **git log**  
    Muestra el historial completo de commits en la rama actual
  - **git log -[numero]**  
    Muestra los últimos n commits
  - **git log --oneline**  
    Muestra cada commit en una línea
  - **git log --graph**  
    Muestra un gráfico ASCII con la estructura de ramas y fusiones
  - **git log --all**  
    Muestra commits de todas las ramas
  - **git log --author=[autor]**  
    Muestra solo commits hechos por un autor específico
  - **git log --grep=[palabra]**  
    Busca commits que contengan una palabra en el mensaje
  - **git log --since=[fecha]**  
    Muestra los commits desde esa fecha en adelante
  - **git log --until=[fecha]**  
    Muestra los commits hasta esa fecha inclusive

- **GIT SHORTLOG**
  - **git shortlog**  
    Muestra un resumen agrupado por autor con la lista de commits
  - **git shortlog -se**  
    Muestra solo la cantidad de commits por autor, incluyendo el correo electrónico

- **GIT SHOW**
  - **git show**  
    Muestra los detalles del último commit: autor, fecha, mensaje y cambios
  - **git show [hash]**  
    Muestra la información completa de un commit específico
  - **git show --name-only**  
    Muestra solo los nombres de archivos modificados
  - **git show --name-status**  
    Muestra el nombre de archivos y el tipo de cambio
      - A = Agregado
      - M = Modificado
      - D = Eliminado

- **GIT LS-TREE**
  - **git ls-tree -r --name-only HEAD**  
    Lista todos los archivos que tiene el ultimo commit
  - **git ls-tree -r --name-only [id-commit]**  
    Lista todos los archivos que tiene un commit especifico
  - **git ls-tree -r --name-only HEAD:[nombre-carpeta]**  
    Lista todos los archivos que tiene una carpeta especifica

- **GIT BLAME**
  - **git blame [nombre-archivo]**  
    Muestra quién modificó cada línea de un archivo y en qué commit

- **GIT REFLOG**
  - **git reflog**  
    Muestra el historial de cambios en referencias

---

## 🌿 Ramas
- **GIT BRANCH**
  - **git branch**  
    Muestra la lista de ramas locales
  - **git branch -r**  
    Muestra la lista de ramas remotas
  - **git branch -a**  
    Muestra la lista de todas las ramas
  - **git branch -v**  
    Muestra el último commit de cada rama local
  - **git branch -d / -D [nombre-rama]**  
    Elimina la rama (fusionada / no fusionada)
  - **git branch -m [nombre-nuevo]**  
    Renombra la rama actual
  - **git branch -m [nombre-viejo] [nombre-nuevo]**  
    Renombra una rama específica
  - **git branch --merged**  
    Muestra las ramas que ya fueron fusionadas con la rama actual
  - **git branch --no-merged**  
    Muestra las ramas que aún no fueron fusionadas con la rama actual

- **GIT SWITCH**
  - **git switch [nombre-rama]**  
    Cambia a la rama especificada
  - **git switch -c [nombre-rama]**  
    Crea una nueva rama y cambia a ella
  - **git switch --detach [hash]**  
    Mueve el HEAD a un commit específico sin afectar ninguna rama

- **GIT MERGE**
  - **git merge [nombre-rama]**  
    Fusiona la rama especificada con la rama actual
  - **git merge --continue**  
    Continúa con el merge interrumpido por conflictos
  - **git merge --abort**  
    Cancela un merge en proceso y vuelve al estado anterior
  - **git merge --ff-only [nombre-rama]**  
    Realiza la fusión solo si se puede aplicar mediante fast-forward, si no es posible, aborta el merge. Útil para mantener historiales lineales

- **GIT REBASE**
  - **git rebase [nombre-rama]**  
    Aplica los commits de la rama actual sobre la rama especificada
  - **git rebase --continue**  
    Continúa un rebase interrumpido por conflictos
  - **git rebase --abort**  
    Cancela un rebase en proceso y vuelve al estado anterior
  - **git rebase -i HEAD~[numero]**  
    Rebase interactivo: te permite reordenar, modificar, combinar o eliminar commits

- **GIT CHERRY-PICK**
  - **git cherry-pick [hash]**  
    Aplica un commit específico desde otra rama a la rama actual
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
  - **git grep -i [texto]**  
    ignore-case
  - **git grep -w [texto]**  
    word-regex
  - **git grep -c [texto]**  
    count
  - **git grep -n [texto]**  
    number-line
    

---

## 🔄 Sincronización remota
- **GIT REMOTE**
  - **git remote**  
    Muestra la lista de nombres de remotos configurados
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
    Descarga los cambios más recientes del repositorio remoto, pero no los aplica en tu rama actual
  - **git fetch --prune**  
    Limpia referencias locales de ramas remotas que ya no existen

- **GIT PULL**
  - **git pull**  
    Descarga y aplica los cambios del repositorio remoto en tu rama actual
  - **git pull --rebase**  
    Reemplaza el merge automático por un rebase, mantiene un historial más limpio
  - **git pull --ff-only**  
    Solo realiza el pull si se puede aplicar como fast-forward. Falla si no es posible

- **GIT PUSH**
  - **git push -u origin main**  
    Establece una rama de seguimiento para futuras sincronizaciones. Después de usarla una vez, basta con git push sin argumentos
  - **git push**  
    Sube los commits locales al repositorio remoto
  - **git push --force**  
    Forza el push, sobrescribe el historial remoto con tu historial local. ⚠️ ¡Peligroso si otros trabajan sobre la misma rama!
  - **git push --tags**  
    Sube todas las etiquetas locales al repositorio remoto
  - **git push origin --delete [nombre-rama]**  
    Elimina una rama remota específica
    
---
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
  - **git add [nombre archivo]**  
    Agrega archivos o cambios específicos al staging area
  - **git add .**  
    Agrega todos los cambios del directorio actual y subdirectorios al staging area

<!-- - **GIT MV** -->
<!-- - **GIT RM** -->

- **GIT RESTORE**
  - **git restore [nombre archivo]**  
    Restaura archivo desde staging o commit.
  - **git restore --source=[nombre rama o commit] [nombre archivo]**  
    Restaura archivo desde otra rama.
---

## 📥 Confirmaciones (commits)

- **GIT COMMIT**
  - **git commit -m [mensaje]**  
    Guarda una instantánea del estado actual del proyecto en el historial de Git.
  - **git commit --amend**  
    Permite modificar el último commit, ya sea el mensaje o añadir archivos olvidados.
  - **git commit --amend --no-edit**  
    Mantiene el mensaje anterior tal cual, útil para agregar un archivo que olvidaste.

- **GIT STATUS**
  - **git status**  
    Muestra el estado actual del directorio de trabajo y del área de preparación
  - **git status --short**  
    Muestra el estado actual del directorio de trabajo y del área de preparación resumido

<!-- - **GIT DIFF** -->

- **GIT RESET**
  - **git reset --soft HEAD~1**  
    Elimina el último commit, pero conservar los cambios en el área de staging
  - **git reset --mixed HEAD**  
    Deshace el git add sin perder los cambios
  - **git reset --hard HEAD~1**  
    Elimina el ultimo commit

<!-- - **GIT REVERT** -->

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

- **GIT LS-TREE**
  - **git ls-tree -r --name-only HEAD**  
    Lista todos los archivos que tiene el ultimo commit
  - **git ls-tree -r --name-only [id commit]**  
    Lista todos los archivos que tiene un commit determinado
  - **git ls-tree HEAD:src/**  
    Lista el contenido de la carpeta src/ en el último commit

<!-- - **GIT SHOW** -->
<!-- - **GIT BLAME** -->

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

- **GIT SWITCH**
  - **git switch -c [nombre rama]**  
    Crea y cambia a nueva rama.
  - **git switch [nombre rama]**  
    Cambia de rama.

- **GIT MERGE**
  - **git merge [nombre rama]**  
    combina los cambios de una rama en otra

<!-- - **GIT REBASE** -->
<!-- - **GIT CHERRY-PICK** -->

---

## 🔄 Sincronización remota

<!-- - **GIT REMOTE** -->
<!-- - **GIT FETCH** -->
<!-- - **GIT PULL** -->
<!-- - **GIT PUSH** -->

---
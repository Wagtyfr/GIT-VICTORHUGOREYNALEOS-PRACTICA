# Práctica: repositorio local y sincronización con GitHub

**Nombre:** Victor Hugo Reyna Leos  
**Matrícula:** 2630104  
**Repositorio:** practica-git-victor-hugo-reyna-leos

## Objetivo

Crear un repositorio con Git, conectarlo con GitHub y comprobar que los cambios se puedan enviar y recibir. La idea es entender cómo guardar versiones del trabajo y mantener actualizados los archivos en ambos lugares.

## Avance de la práctica

La parte local está preparada: carpeta del proyecto, rama `main`, archivos y primer commit. Todavía falta conectar la cuenta de GitHub para crear el repositorio público y comprobar las dos sincronizaciones. Los pasos 3, 4 y 5 describen lo que falta realizar.

## Procedimiento

### 1. Crear el repositorio local

Se creó la carpeta `practica-git-victor-hugo-reyna-leos`. Dentro de ella se inició Git y se dejó la rama principal con el nombre `main`.

```powershell
git init
git branch -M main
```

Esto permite que Git lleve el historial del proyecto. También se configuraron el nombre del estudiante y el correo de su cuenta para identificar los commits. Esa configuración se aplicó únicamente a este repositorio.

Después se crearon `README.md` y `datos.txt`. El primero contiene la explicación de la práctica y el segundo tiene el texto que se irá modificando.

### 2. Registrar los primeros cambios

Primero se revisó qué archivos detectaba Git. Después se agregaron al área de preparación y se volvió a revisar su estado.

```powershell
git status
git add .
git status
```

El área de preparación sirve para elegir los cambios que van a entrar en el siguiente commit. Agregarlos ahí todavía no los envía a GitHub.

El primer registro del historial se guardó con este comando:

```powershell
git commit -m "Primer commit"
```

### 3. Conectar con GitHub y enviar los archivos

**Pendiente de realizar.**

En GitHub se debe crear un repositorio público llamado `practica-git-victor-hugo-reyna-leos`. Debe comenzar vacío, sin agregar automáticamente README, licencia ni `.gitignore`, porque los archivos saldrán del repositorio local.

Después se copia su URL y se registra con el nombre `origin`:

```powershell
git remote add origin URL_DEL_REPOSITORIO
git remote -v
git push -u origin main
```

`URL_DEL_REPOSITORIO` se reemplaza por la dirección real que muestre GitHub. `origin` es el nombre que se usa para identificar esa conexión. Con el primer `push` se envían los commits de `main`; la opción `-u` deja configurado el destino para los siguientes envíos.

Para comprobarlo, se abrirá el repositorio en GitHub y se revisará que aparezcan los dos archivos.

### 4. Recibir un cambio de GitHub en el repositorio local

**Pendiente de realizar.**

Desde la página de GitHub se abrirá `datos.txt`, se presionará el botón de editar y se agregará esta línea:

```text
Este archivo fue modificado desde GitHub.
```

El cambio se guardará desde GitHub con un commit llamado `Actualización desde GitHub`. Después, dentro de la carpeta local, se ejecutará:

```powershell
git pull origin main
```

Este comando trae los cambios de la rama remota y los integra en la rama actual. Se abrirá el archivo local para comprobar que tenga la nueva línea. Así se revisará el recorrido GitHub → repositorio local.

### 5. Enviar otro cambio del repositorio local a GitHub

**Pendiente de realizar, después del paso 4.**

Se agregará al archivo local `datos.txt` la siguiente línea:

```text
Este archivo fue modificado desde el repositorio local.
```

Después se revisará el estado, se preparará el cambio, se guardará en un commit y se enviará:

```powershell
git status
git add .
git commit -m "Actualización desde repositorio local"
git push
```

Al abrir otra vez el archivo en GitHub deberá aparecer esa línea. Esto comprobará el recorrido repositorio local → GitHub.

También se revisará que no queden cambios pendientes y que el historial incluya los commits de la práctica:

```powershell
git status
git log --oneline
```

## Comandos de Git y su función

Los comandos de la parte local ya se utilizaron. Los que conectan con GitHub quedan preparados para los pasos pendientes.

| Comando | Para qué sirve |
| --- | --- |
| `git init` | Inicia un repositorio en la carpeta actual. |
| `git branch -M main` | Cambia el nombre de la rama actual a `main`. |
| `git config user.name "Victor Hugo Reyna Leos"` | Define el nombre que se registrará en los nuevos commits. |
| `git config user.email CORREO_DE_LA_CUENTA` | Define el correo que se registrará en los nuevos commits. |
| `git status` | Muestra la rama actual y los cambios pendientes o preparados. |
| `git add .` | Prepara los cambios de la carpeta actual y sus subcarpetas. |
| `git commit -m "Primer commit"` | Guarda los cambios preparados en el historial local. |
| `git remote add origin URL_DEL_REPOSITORIO` | Guarda la dirección del repositorio remoto con el nombre `origin`. |
| `git remote -v` | Muestra las direcciones configuradas para recibir y enviar cambios. |
| `git push -u origin main` | Envía `main` y deja configurado su seguimiento remoto. |
| `git pull origin main` | Descarga e integra los cambios de la rama remota `main`. |
| `git commit -m "Actualización desde repositorio local"` | Registra el segundo cambio local con un mensaje que lo identifica. |
| `git push` | Envía los commits al destino que ya quedó configurado. |
| `git log --oneline` | Muestra el historial resumido, con un commit por línea. |

## Archivos del repositorio

| Archivo | Contenido |
| --- | --- |
| `README.md` | Nombre, matrícula, objetivo, explicación del procedimiento, comandos y conclusión. |
| `datos.txt` | Texto inicial de la práctica. Se usará para comprobar los cambios desde GitHub y desde el repositorio local. |

## Conclusión personal

Con la parte local entendí que guardar un archivo y hacer un commit son pasos diferentes. Primero modifico el archivo, después preparo el cambio con `git add` y al final lo registro con `git commit`. Así puedo llevar un historial de lo que voy haciendo.

También entendí para qué sirven `push` y `pull`: uno envía los commits y el otro trae e integra los cambios. Todavía falta comprobar esa parte con GitHub. Al terminarla podré revisar cómo se mantiene el mismo trabajo actualizado en los dos lugares.

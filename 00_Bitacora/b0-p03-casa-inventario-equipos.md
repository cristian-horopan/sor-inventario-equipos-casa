- **Alumno:** Cristian Raul Horopan
- **Bloque:** B0.P03
- **Fase / ejercicio:** B0.P03 · Casa · Inventario de equipos con Git y GitHub
- **Fecha de inicio:** 01/11/2026
- **Fecha de entrega:** 01/11/2026
---

## Qué se pedía
Crear un inventario de equipos desde cero, versionarlo con Git en tres entregas y publicarlo en GitHub.
## ⌨Comandos y pasos importantes
- git --version: comprueba la versión de Git instalada.
    
- git config --global user.name: consulta el nombre configurado en Git.
    
- git config --global user.email: consulta el correo configurado en Git.
    
- ls -l ~/.ssh/id_ed25519 ~/.ssh/id_ed25519.pub: comprueba que existen las claves SSH.
    
- ssh -T git@github.com: comprueba la conexión SSH con GitHub.
    
- pwd: muestra la ruta de la carpeta actual.
    
- git init: inicializa un repositorio Git.
    
- git branch -M main: establece el nombre de la rama principal como main.
    
- git status: muestra el estado de los archivos.
    
- git remote add origin URL: conecta el repositorio local con GitHub.
    
- git remote -v: muestra las direcciones del repositorio remoto.
    
- git add archivo: prepara un archivo para guardarlo en el siguiente commit.
    
- git diff: muestra los cambios que todavía no se han preparado.
    
- git diff --cached: muestra los cambios que ya están preparados.
    
- git diff --cached --stat: resume los archivos preparados.
    
- git commit -m "mensaje": guarda una versión en el historial local.
    
- git push: sube los commits a GitHub.
    
- git log --oneline: muestra el historial de commits de forma resumida.
    
- git switch --detach CODIGO: permite consultar una versión antigua sin cambiar de rama.
    
- git switch main: regresa a la rama principal.
    
- git check-ignore -v archivo: comprueba qué regla de .gitignore excluye un archivo.
## Qué he hecho
Primero preparé el entorno de trabajo y creé una bóveda nueva en Obsidian llamada Boveda_Inventario_Casa, con sus carpetas correspondientes.

Después creé los archivos iniciales del proyecto: .gitignore, para excluir los vídeos y archivos innecesarios; README.md, con la descripción del inventario; inventario/equipos.csv, con los equipos EQ01 y EQ02; y la bitácora de la práctica.

A continuación, inicialicé Git dentro de la carpeta 01_Proyecto, establecí la rama principal como main y conecté el repositorio local con GitHub mediante SSH.

Realicé las tres versiones del inventario:

Primera versión: creé el inventario inicial con EQ01 y EQ02 y guardé los archivos en el primer commit.

Segunda versión: cambié la ubicación de EQ01 de Aula-1 a Aula-3 y el estado de EQ02 de disponible a mantenimiento.

Tercera versión: añadí el equipo EQ03, la ficha de mantenimiento de EQ02, los criterios de estado y una imagen de ejemplo. También actualicé el README.

En cada versión utilicé git add, git commit y git push para preparar, guardar y subir los cambios.

Finalmente, consulté el historial de Git para comprobar las versiones anteriores y regresé a la rama main para recuperar la versión más reciente.
## Qué me ha fallado y cómo lo he resuelto
Al principio la ruta de verificación SSH fallaba por un error tipográfico en el nombre del archivo de la clave (escribí id_25519 en lugar de id_ed25519). Se corrigió escribiendo el comando correcto.

Incidencia 2: Error al realizar git push

Cuando intenté subir los cambios al repositorio con el comando git push, no funcionó porque todavía no había realizado el commit. Primero tenía que guardar los cambios en el historial local con git add y git commit. Después de hacer el commit, pude realizar el git push para subirlos a GitHub.

Solución: Realizar primero el commit de los cambios y, a continuación, ejecutar git push.
## Respuestas a las preguntas
1. ¿Por qué el repositorio está en 01_Proyecto y no en la raíz de la bóveda?

Porque así solamente se guardan en Git los archivos del proyecto y no se incluyen otros elementos de Obsidian, las configuraciones o las grabaciones. De esta manera el repositorio queda más organizado.

2. ¿Qué dos celdas de datos cambiaste en la segunda versión y cómo se ven en diff?

Cambié la ubicación de EQ01 de Aula-1 a Aula-3 y el estado de EQ02 de disponible a mantenimiento. En git diff aparecen las líneas antiguas eliminadas con un signo menos y las nuevas añadidas con un signo más.

3. ¿Qué diferencia hay entre editar una fila y preparar ese cambio con add?

Editar una fila significa modificar el archivo y guardar los cambios en el ordenador. Utilizar git add significa seleccionar esos cambios para incluirlos en el siguiente commit. No se guarda una versión en el historial hasta ejecutar git commit.

4. ¿Por qué la ficha nueva aparece en status y no en el diff de equipos.csv?

Porque la ficha de mantenimiento es un archivo nuevo y todavía no está incluido en el historial de Git. git status muestra los archivos nuevos sin seguimiento, mientras que git diff muestra los cambios en archivos que Git ya conoce.

5. ¿Qué archivos preparaste individualmente en la ampliación y qué mostró diff --cached?

Preparé individualmente los siguientes cinco archivos: la ficha de mantenimiento de EQ02, los criterios de estado, la imagen del equipo, el inventario CSV y el README.

Con git diff --cached pude revisar los cambios preparados antes de realizar el commit y comprobar que solamente estaban seleccionados los archivos necesarios.

6. ¿Cómo demostraste que los clips existen y están ignorados sin subirlos?

Comprobando que los dos archivos MP4 existían en la carpeta de vídeos y que se podían reproducir. Después utilicé git check-ignore -v para comprobar que estaban excluidos por la regla *.mp4 del archivo .gitignore.

7. ¿Qué ubicación y estado recuperaste al visitar el primer commit y qué ocurrió con EQ03?

Al consultar el primer commit, EQ01 volvió a aparecer en Aula-1 y EQ02 como disponible. EQ03 no aparecía porque todavía no se había añadido en esa primera versión. Después regresé a main y recuperé la versión más reciente.

8. ¿Por qué este CSV necesita historial y qué limitaciones tiene frente a un inventario multiusuario real?

Porque los equipos pueden cambiar de ubicación, estado o incorporarse nuevos. El historial permite consultar los cambios y recuperar versiones anteriores. Sin embargo, un CSV no permite gestionar correctamente muchos usuarios trabajando al mismo tiempo ni ofrece permisos, validación avanzada o edición simultánea.

9. ¿Cómo comprobaste la subida de la bitácora y por qué su cierre ocurre después del vídeo?

Comprobando el repositorio en GitHub y revisando que la bitácora tuviera su contenido completo y los enlaces correspondientes. El cierre se realiza después del vídeo porque primero hay que terminar la grabación, subirla a YouTube y conseguir sus enlaces para incorporarlos a la bitácora.
## Enlaces
- **Vídeo de esta fase:** https://youtu.be/-jrsg7RZMgg
- **Playlist:** https://www.youtube.com/playlist?list=PLbapTCrs4v18
## Dudas / a repasar
- Repasar la diferencia entre git add, git commit y git push.
    
- Entender mejor las diferencias entre git diff y git diff --cached.
    
- Practicar cómo consultar versiones antiguas utilizando git switch --detach.
    
- Repasar cómo funciona .gitignore y por qué no elimina archivos que ya están versionados.
    
- Comprender mejor cómo se organiza el historial de commits y cómo volver a main.
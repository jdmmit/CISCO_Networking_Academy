Imprimir el directorio de trabajo
Para descubrir dónde se encuentra actualmente dentro del sistema de archivos, puede utilizar el comando pwd. El comando pwd imprime el directorio de trabajo (print working directory), su ubicación actual dentro del sistema de archivos:

pwd [OPCIONES]
A tener en cuenta

¡No encienda su impresora todavía! En los inicios de la computación, el resultado de un comando se enviaba directamente a impresoras físicas. Este método ha sido reemplazado por pantallas de vídeo que muestran información más rápidamente. Aún así, actualmente seguimos utilizando la palabra imprimir (print) aunque el resultado se esté mostrando en una pantalla.

sysadmin@localhost:~$ pwd
/home/sysadmin
El resultado del comando anterior indica que el usuario está actualmente en su carpeta de inicio, tal y como muestra el sistema de archivos siguiente.

Sistema de archivos que muestra el directorio root en la parte superior y los directorios debajo, incluido el directorio de inicio. Debajo del directorio de inicio hay un directorio sysadmin resaltado y los directorios dentro de sysadmin (es decir, Documents) que se muestran a continuación.
Considere esto

Observe que nuestras máquinas virtuales emplean un indicador para mostrar el directorio de trabajo actual, resaltado en color azul. En el primer mensaje, el carácter ~ azul es equivalente a /home/sysadmin, y representa el directorio de inicio del usuario.

sysadmin@localhost:~$
Después de cambiar de directorio (aprenderemos cómo hacerlo en la siguiente sección), la nueva ubicación también se puede confirmar en el nuevo indicador, que nuevamente se muestra en azul.

sysadmin@localhost:/etc/calendar$

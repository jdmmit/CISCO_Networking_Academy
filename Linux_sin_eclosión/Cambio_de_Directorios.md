Cambio de Directorios
Los archivos se utilizan para almacenar datos como texto, gráficos y programas. Los directorios son un tipo de archivo utilizado para almacenar otros archivos: proporcionan una estructura organizativa jerárquica. La siguiente imagen muestra una versión abreviada de la estructura del sistema de archivos de nuestras máquinas virtuales.

Filesystem hierarchy with root directory at the top. No highlighted directories.
Al iniciar una máquina virtual nueva, ya sea abriendo el curso o después de usar el botón de reinicio, usted inicia una sesión como usuario sysadmin en su directorio principal, resaltado en azul a continuación:

Filesystem showing root directory at the top and directories underneath, including home directory. Under the home directory is a highlighted sysadmin directory and the directories inside of sysadmin (i.e., Documents) shown below.
Utilice el comando cd (change directory) para cambiar de directorio y navegar por la estructura del sistema de archivos.

cd [opciones] [ruta]
Si examina el gráfico anterior, notará que el directorio Documents se encuentra dentro del directorio de inicio home, donde usted se encuentra actualmente. Para desplazarse al directorio Documents, utilícelo como argumento para el comando cd:

sysadmin@localhost:~$ cd Documents  
sysadmin@localhost:~/Documents$
Los directorios son equivalentes a las carpetas en Windows y Mac OS. Al igual que estos sistemas operativos más populares, una estructura de directorios Linux también tiene un nivel superior. No se llama “Mi PC”, sino directorio raíz (root) y está representado por el carácter /. Para desplazarse al directorio root, utilice el carácter / como argumento del comando cd.

sysadmin@localhost:~/Documents$ cd /
sysadmin@localhost:/$
Filesystem hierarchy with highlighted root directory at the top.
El argumento para el comando cd es más que el nombre de un directorio, en realidad es una ruta (path). Una ruta es una lista de directorios separados por el carácter /. Por ejemplo, /home/sysadmin es la ruta a su directorio de inicio:

Filesystem hierarchy with highlighted root directory at the top, highlighted home directory underneath and highlighted sysadmin directory under home directory.
Imagine que el sistema de archivos es un mapa, las rutas son las instrucciones que indican paso a paso la ubicación de cualquier archivo dentro del sistema de archivos. Hay dos tipos de rutas: absolutas y relativas. Las rutas absolutas comienzan en la raíz del sistema de archivos, las rutas relativas comienzan en su ubicación actual.

Rutas absolutas
Una ruta absoluta le permite especificar la ubicación exacta de un directorio. Siempre comienza en el directorio root, por lo tanto siempre comienza con el carácter /. La ruta al directorio de inicio (home) /home/sysadmin es una ruta absoluta. La ruta comienza en el directorio root /, se mueve al directorio de inicio home y, a continuación, al directorio sysadmin. Esta ruta en una interfaz gráfica de usuario (GUI) como la de su ordenador personal aparecería así:

Utilice esta ruta como argumento para el comando cd para volver al directorio principal del usuario sysadmin.

sysadmin@localhost:/$ cd /home/sysadmin
sysadmin@localhost:~$
Que no aparezca un resultado en la línea de comandos significa que el comando se ha ejecutado correctamente. Continúe y confirme que es así usando el comando pwd:

sysadmin@localhost:~$ pwd  
/home/sysadmin
Rutas relativas
Una ruta relativa ubica un archivo en relación con la ubicación actual del usuario en el sistema de archivos. Las rutas relativas no comienzan con el carácter /, comienzan con el nombre de un directorio. Eche otro vistazo al primer ejemplo de comando cd. En este caso, el argumento es un ejemplo de la ruta relativa más simple: el nombre de un directorio en su ubicación actual.

sysadmin@localhost:~$ cd Documents  
sysadmin@localhost:~/Documents$
Filesystem hierarchy showing root at the top and directories underneath, including home directory. Highlighted sysadmin directory representing current location under home directory. Highlighted path to Documents directory under sysadmin directory.
La siguiente imagen muestra un mapa de los archivos contenidos en el directorio sysadmin. Actualmente se encuentra en el directorio Documents y desea desplazarse al directorio Art:

Filesystem system hierarchy showing sysadmin directory at the top, including highlighted Documents directory underneath as well as directories underneath the Documents directory, including the School directory. The highlighted Art directory is located underneath the School directory.
Una ruta relativa comienza con el directorio actual, sin embargo, éste no se incluye en la ruta. El primer paso sería pasar al directorio School y, a continuación, pasar al directorio Art. Utilice el carácter / para separar los nombres de directorio. El resultado School/Art es una ruta relativa desde el directorio Documents hasta el directorio Art:

Filesystem system hierarchy showing sysadmin directory at the top and a relative path to the Art directory.
Utilice la ruta relativa como argumento para el comando cd para desplazarse al directorio Art.

sysadmin@localhost:~/Documents$ cd School/Art
sysadmin@localhost:~/Documents/School/Art$
Utilice el comando pwd para confirmar que el cambio ha ocurrido:

sysadmin@localhost:~/Documents/School/Art$ pwd  
/home/sysadmin/Documents/School/Art
A tener en cuenta

El resultado del comando pwd es la ruta absoluta al directorio Art.

Filesystem system hierarchy showing root directory at the top and a relative path to the Art directory.
A tener en cuenta

En el ejemplo anterior, el comando cd siguió la ruta School/Art:

cd School/Art
Una ruta también se puede dividir en varios comandos cd. El siguiente conjunto de comandos lograría los mismos resultados:

cd School
cd Art
Accesos Directos o Atajos
Dos puntos ..

Independientemente del directorio en el que se encuentre, el carácter .. siempre representa un directorio superior en relación al directorio actual, a veces denominado directorio padre. Por ejemplo, para pasar del directorio Art al directorio School:

sysadmin@localhost:~/Documents/School/Art$ cd ..  
sysadmin@localhost:~/Documents/School$
Un punto .

Independientemente del directorio en el que se encuentre, el carácter . siempre representa su directorio actual. Para el comando cd, este atajo no es muy útil, pero será útil para los comandos que estudiaremos en las secciones siguientes.

El símbolo ~

El directorio principal del usuario actual está representado por el carácter ~ . Como se indicó anteriormente, siempre comienza su sesión como usuario sysadmin, cuyo directorio de inicio se encuentra en /home/sysadmin. Para volver a su directorio de inicio en cualquier momento, puede ejecutar el siguiente comando:

sysadmin@localhost:~/Documents/School$ cd ~
sysadmin@localhost:~$

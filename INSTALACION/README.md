# Instalacion maquina virtual Debian 12 en vmware

## Objetivo
Mostrar el proceso de instalacion de la maquina virtual donde desplegaremos nuestro servidor

## Pasos
1. **CREACION MAQUINA VIRTUAL
Como se menciono anteriormente haremos uso del hipervisor vmware, version 17.5.2
El siguiente enlace, es de la pagina oficial de Debiam, descargara el DVD(Imagen iso) con el que iniciaremos la instalacion:
https://www.debian.org/download
Una vez concluida la descarga vamos a nuestro virtualizador
Elegimos la seccion "File", damos en create a new virtual machine.
Nos aparecera una ventana preguntandonos por el archivo, elegimos browse y buscamos el archivo iso recien descargado.
Avanzamos, nos pediran un nombre para la maquina virtual, yo usare debian.
Nos pedira escoger la cantidad de memoria de nuestro disco duro a utilizar para la maquina virtual, lo recomendable son 20gb, pero puedes darle cuanto 
consideres necesaria.
Damos en finish y nos aparecerea la maquina virtual nuevo, damos en power para iniciarla.
2. **INSTALACION DEBIAN
Ahora que tenemos la maquina virtual donde alojaremos nuestro debian, sigue instalar el SO.
Damos play en el triangulo verde para arrancar el iso.
Nos apareceran varias formas de instalacion, elegimos "Graphical install"
3. **IDIOMA
Nos desplegara una lista de idiomas para nuestro debian, elegimos Español[spanish] y damos en continuar.
4. **REGION
Nos desplegara una lista de pais en base al idioma que estaremos usando, es importante seleccionar donde vivimos para que la maquina tenga zona horaria 
correcta, en mi caso usare Mexico.
5. **TECLADO
Lo siguiente es configurar el teclado en base a la region. Esto es importante si queremos que coincida el ASCII asi como las teclas de nuestro teclado
fisico con la MV, por ejemplo, si escogieram el teclado estadounidense(US) en lugar del latinoamericano, esta seleccion no cuenta con la letra "ñ".
Elegimos teclado y esperamos que carguen algunas configuraciones.
6. **NOMBRAR SERVIDOR
Para continuar con la instalacion, nos pedira un nombre para el servidor que estemos manejando, puedes elegir el que gustes, en mi caso lo nombrare odin.
No hay problemas si el nombre del servidor es diferente al que maneja nuestra maquina virtual, no afecta el funcionamiento de este.
7. **NOMBRAR DOMINIO
Lo siguiente sera nombrar el dominio, pero,¿que es el dominio?.
El dominio es algo asi como una etiqueta que agrupa servicios o equipos dentro de una misma red, por ejemplo en internet, todos los recuros de google
pertenecen al dominio google.com.
En el caso de una red local, puede usarse para diferenciar dispositivos en una red, por ejemplo "preparatorioX.edu"
Si tenemos varias computadoras podria ser 
-pc01.preparatorioX.edu
-pc02.preparatorioX.edu
-pc03.preparatorioX.edu
en este caso tomare "asgard.local", identificaria mi servidor como "odin.asgard.local".
8. **DEFINIR CONTRASEÑA ROOT
Lo siguiente que nos pediran, es una contraseña que usara el usuario ROOT.
Esto es algo de suma importancia para la seguridad de nuestro servidor por los privilegios que porta este usuario, lo recomendable es una combinacion
alfanumerica usando mayusculas, minusculas y con al menos 3 caracteres especiales, no usar suceciones de numeros como "12345,54321,2222,11111" o numeros como fechas de nacimiento que
podrian ser adivinadas por ciber delincuentes.
9. **CREACION DE USUARIO
Lo siguiente es crear un usuario ordinario. Estos se diferencian de los superusuarios(root) por la cantidad de permisos, tiene limitaciones ya que si un
usuario ordinario comete un error, solo afectara configuraciones y archivos propios, ademas de que tareas cotidianas com navegar en internet o subir documentos
y si llegara a ser comprometido, no podria afectar tanto al sistema o archivos criticos.
En este caso lo llamara thor, pero puedes llamarlo como gustes.
10. **CONTRASEÑA USUARIO
Tal como lo hicimos para root, nuestro usuario ordinario necesita una contraseña, es importante recordar las recomendaciones, ya que aun que no tenga los mismos
privilegios que root, igual una brecha de seguridad por ahi puede causar mucho daño.
11. **ZONA HORARIA
Complementando lo antes dicho del pais, debemos escoger una zona horaria especifica, en este caso de Jalisco es zona horaria central
12. **PARTICION DE DISCO
Lo siguiente es elegir la forma en la que nuestro disco duro sera dividido.
Se nos va a desplegar 4 opciones diferentes
-Guiada -utilizar todo el disco: Esta opción configura el particionado de forma automática utilizando todo el disco disponible sin configuraciones adicionales.
-Guiada -utilizar todo el disco y configurar LVM: Esta opcion configura el particionado utilizando LVM (Logical Volume Manager), que permite manejar 
particiones lógicas de manera más flexible.
-Guiada -utilizar todo el disco y configurar LVM cifrado:Similar a la opción anterior (LVM), pero añade cifrado a las particiones. Toda la información en el 
disco se almacena cifrada.
-Manual: Te permite configurar las particiones de forma manual, creando particiones personalizadas según tus necesidades.
En mi caso debido a que no necesitaremos nada tan especifico y al ser a nivel local, utilizaremos la primera opcion por sencillez.
Nos mostrara el disco duro a particionar, lo elegimos y damos en continuar.
Seleccionar el primer esquema para realizar la partición del disco [Todos los
ficheros en una partición].
Si todo salio bien, procedera la divicion del disco, debemos aceptar los cambios realizados en nuestro disco.
13. **INSTALACION 
Va a iniciar la instalacion, esperamos a que se llene la barra de carga.
14. **ESCANEO DE MEDIOS DE INSTALACION 
Elegimos que No queremos un escaneo de medios de instalacion y esperamos a que concluya.
15. **ESTADISTICAS
Escogemos que no deseamos enviarle estadisticas a los desarrolladores.
16. **ENTORNO
Debemos habilitar configuracion del entorno predeterminadas, en este caso debemos marcar
-Entorno de escritorio Debian: Este nos permitira contar con una interfaz grafica.
-GNOME: Es una interfaz gráfica que permite interactuar con el sistema de forma visual, en lugar de depender únicamente de la terminal.
-Utilidades estandar del sistema: Conjunto de herramientas básicas y esenciales necesarias para que tu sistema operativo Debian funcione correctamente.
Las marcamos y damos en continuar.
Esperamos a que finalice y aceptamos el arrancador de GRUB.
17. **DISCO DE ARRANQUE
Elegimos un disco duro que usaremos como disco de arranque.
18. **ARRANQUE
Una vez finalizada la instalacion, le damos en continuar, nos aparecera una pantalla, debemos elegir DEBIAN/GNU Linux
19. **USUARIO 
Nos aparecera el usuario qeu creamos, lo elegimos, colocamos la contraseña y entramos
20. **DEBIAN
Al ingresar nos aparecera una pantalla de bienvenida, debemos elegir nuevamente idioma y siguiente, lo mismo con el teclado, elegimos latinoamericano.
Nos preguntara por privacidad,lo apagamos y omitimos la conexion a cuentas.
21. **TERMINAL
Ingresamos a la terminal y nos volvemos root con su - y la contraseña que creamos.
Debemos editar el archivo de repositorios con este comando: "nano /etc/apt/sources.list" usaremos el editor de texto para ingresar lo siguiente
deb http://deb.debian.org/debian/ stable main
deb http://ftp.debian.org/debian/ stable main
deb http://deb.debian.org/debian/ stable-updates main contrib
deb http://deb.debian.org/debian-security/ stable-security main contrib
deb https://deb.debian.org/debian bookworm main non-free-firmware
Al terminar la edición del archivo, guardar con “Ctrl+O” seguido de “Enter”, salir
con “Ctrl+X
22. **ACTUALIZACION
Ahora se deberá de hacer actualización de los paquetes con: 
Lo sigueitne seria instalar tools para la terminal usando apt install open-vm-tools
y para el escritorio con apt install open-vm-tools-desktop
23. **APAGADO
Por ultimo para apagar el server usamos shutdown now






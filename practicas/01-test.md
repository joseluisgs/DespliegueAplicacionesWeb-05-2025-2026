
### 50 Preguntas Tipo Test sobre FTP y Almacenamiento de Archivos

- [50 Preguntas Tipo Test sobre FTP y Almacenamiento de Archivos](#50-preguntas-tipo-test-sobre-ftp-y-almacenamiento-de-archivos)
  - [I. Fundamentos y Arquitectura del FTP](#i-fundamentos-y-arquitectura-del-ftp)
  - [II. Asignación de Puertos y Modos de Conexión](#ii-asignación-de-puertos-y-modos-de-conexión)
  - [III. Comandos FTP](#iii-comandos-ftp)
  - [IV. Códigos de Respuesta FTP](#iv-códigos-de-respuesta-ftp)
  - [V. VSFTPD y Configuración](#v-vsftpd-y-configuración)
  - [VI. Seguridad: FTPS y SFTP](#vi-seguridad-ftps-y-sftp)


#### I. Fundamentos y Arquitectura del FTP

1.  ¿En qué protocolo se basa principalmente el FTP (File Transfer Protocol)?
    A. Protocolo de Datagramas de Usuario (UDP)
    B. Protocolo de Transferencia de Hipertexto (HTTP)
    C. Protocolo de Control de Transmisión (TCP)
    D. Protocolo de Mensajes de Control de Internet (ICMP)

2.  ¿Cuál es una característica clave del FTP que lo distingue y que requiere dos conexiones TCP separadas entre el cliente y el servidor?
    A. La necesidad de cifrado SSL/TLS obligatorio
    B. La arquitectura cliente-servidor
    C. La autenticación por medio de claves SSH
    D. La gestión de bases de datos

3.  ¿Cuál es el propósito del **Canal de Control (o Comandos)** en una conexión FTP?
    A. Se utiliza para la transferencia real de archivos y contenido de directorios
    B. Se utiliza para enviar instrucciones (comandos) y recibir respuestas
    C. Se utiliza para la gestión de permisos en el sistema de archivos
    D. Permite que los comandos se detengan durante la transferencia de datos

4.  ¿Cuál es el propósito del **Canal de Datos** en una conexión FTP?
    A. Se utiliza para la transferencia real de archivos y contenido de directorios
    B. Se utiliza para enviar comandos como `GET`, `PUT`, `PORT`, o `PASV`
    C. Se utiliza para la asignación de puertos aleatorios
    D. Se utiliza exclusivamente para la autenticación del usuario

5.  Según las fuentes, ¿qué protocolo de transferencia de archivos se considera más seguro que el FTP clásico y funciona sobre SSL/TLS?
    A. SSH (Secure Shell)
    B. SFTP (SSH File Transfer Protocol)
    C. FTPS (FTP sobre SSL/TLS)
    D. HTTP (HyperText Transfer Protocol)

#### II. Asignación de Puertos y Modos de Conexión

6.  En la asignación de puertos FTP, ¿qué puerto utiliza el **Servidor** para el **Canal de Control** tanto en Modo Activo como en Modo Pasivo?
    A. 20
    B. 21
    C. 22
    D. 80

7.  En el **FTP Modo Activo**, ¿qué puerto utiliza el Servidor para el Canal de Datos?
    A. 21
    B. P + 1
    C. 20
    D. Un puerto en el Rango Q

8.  En el **FTP Modo Pasivo**, ¿qué tipo de puerto de datos utiliza el Servidor?
    A. El puerto fijo 20
    B. Un puerto aleatorio en el Rango Q (>1023)
    C. El puerto 21
    D. El puerto P + 1

9.  Si un Cliente abre un puerto aleatorio **P** para el Control, ¿cuál será el puerto que el Cliente intentará utilizar para la conexión de **Datos** en ambos modos (Activo y Pasivo)?
    A. P
    B. P + 1
    C. 21
    D. 20

10. ¿Quién **inicia** la conexión del Canal de Datos en el **FTP Modo Activo** (el predeterminado)?
    A. El Cliente
    B. El Servidor
    C. El Firewall del Cliente
    D. El router NAT

11. ¿Cuál es el principal inconveniente que surge en el Modo Activo debido a quién inicia la conexión de datos?
    A. El riesgo de seguridad en el Servidor (debe abrir un rango de puertos)
    B. La necesidad de certificados SSL
    C. El bloqueo por el Firewall del Cliente
    D. La conexión es más lenta que en el Modo Pasivo

12. ¿Quién **inicia** la conexión del Canal de Datos en el **FTP Modo Pasivo**?
    A. El Servidor
    B. El Cliente
    C. El Firewall del Servidor
    D. El router NAT

13. ¿Qué comando envía el Cliente al Servidor para iniciar la conexión de Control en el **Modo Pasivo**?
    A. PORT
    B. PUT
    C. PASV
    D. GET

14. En el Modo Pasivo, ¿por qué el Firewall del Cliente generalmente permite la conexión de datos?
    A. Porque la conexión de datos es cifrada
    B. Porque la conexión es iniciada por el Cliente (es una conexión de salida)
    C. Porque el Servidor utiliza un puerto fijo
    D. Porque se utiliza el puerto 21

15. ¿Cuál es el riesgo de seguridad principal del Modo Pasivo?
    A. Que el Servidor tiene que iniciar la conexión de datos
    B. Que el Cliente debe abrir un puerto mayor a 1023
    C. Que el Servidor necesita abrir un amplio rango de puertos (Rango Q)
    D. El Firewall del Cliente no bloquea

#### III. Comandos FTP

16. ¿Qué comando utiliza el Cliente para iniciar una conexión con un servidor FTP?
    A. close puerta
    B. open puerta
    C. quit
    D. status

17. ¿Qué comando debe utilizar el cliente para finalizar una conexión FTP y la sesión de trabajo con el programa cliente?
    A. close o disconnect
    B. bye o quit
    C. !
    D. user

18. Si un usuario quiere **obtener** un archivo del servidor, ¿qué comando debe usar?
    A. put archivo
    B. mput archivos
    C. get archivo
    D. send nombre del archivo

19. ¿Qué comando permite al usuario cambiar el directorio de trabajo **localmente**?
    A. cd directorio
    B. lcd directorio
    C. pwd
    D. rmdir directorio

20. ¿Qué comando FTP se utiliza para **enviar** un archivo al directorio activo del servidor?
    A. get archivo
    B. rename archivo
    C. put archivo
    D. dir

21. ¿Qué comando muestra el directorio activo actual en el servidor?
    A. status
    B. ls
    C. prompt
    D. pwd

22. ¿Qué modo de transferencia debe activar el usuario si quiere transferir archivos binarios?
    A. ascii
    B. literal
    C. bin o binary
    D. hash

23. ¿Qué comando permite borrar múltiples archivos basado en un patrón que se aplica al nombre?
    A. delete archivo
    B. rmdir directorio
    C. mdelete patrón
    D. prompt

24. Si un usuario desea saber el estado actual de la conexión, ¿qué comando debe utilizar?
    A. ? o help
    B. noop
    C. status
    D. bell

25. El comando `literal` (o `quote`) permite ejecutar qué tipo de comandos?
    A. Comandos del cliente local
    B. Comandos del servidor de forma remota
    C. Comandos del firewall
    D. Comandos de la línea de comandos temporal

#### IV. Códigos de Respuesta FTP

26. Si el primer dígito de un código de respuesta FTP es **2**, ¿qué indica?
    A. Un error o una respuesta incompleta
    B. Éxito de la respuesta
    C. No hay respuesta
    D. Un error de autenticación

27. Si el primer dígito de un código de respuesta FTP es **4** o **5**, ¿qué indica?
    A. Éxito de la respuesta
    B. Un error de sintaxis
    C. No hay respuesta
    D. Una respuesta incompleta

28. Si el segundo dígito de un código de respuesta es **x2z**, ¿a qué categoría de problemas se refiere la respuesta?
    A. Sintaxis
    B. Conexiones
    C. Sistema de archivos
    D. Información

29. Si el segundo dígito de un código de respuesta es **x5z**, ¿a qué categoría de problemas se refiere la respuesta?
    A. Autenticación y contabilidad
    B. Conexiones
    C. Sintaxis
    D. Sistema de archivos

30. En un código de respuesta FTP, ¿qué dígito se utiliza para proporcionar detalles adicionales dentro de las categorías definidas?
    A. El primer dígito
    B. El segundo dígito
    C. El tercer dígito
    D. El cuarto dígito

#### V. VSFTPD y Configuración

31. ¿Qué servidor FTP para Unix se destaca por su seguridad y se denomina "Very Secure FTP Daemon"?
    A. OpenSSH
    B. FileZilla Server
    C. VSFTPD
    D. Apache Tomcat

32. En el archivo de configuración de `vsftpd` (`vsftpd.conf`), ¿qué opción permite a los usuarios anónimos iniciar sesión?
    A. local_enable
    B. write_enable
    C. anonymous_enable
    D. userlist_enable

33. ¿Qué opción de configuración de VSFTPD, si se establece en "YES", determina si las operaciones de escritura (como crear o eliminar archivos) están permitidas?
    A. chroot_local_user
    B. write_enable
    C. pasv_enable
    D. listen

34. ¿Cuál es el propósito de las opciones `pasv_min_port` y `pasv_max_port` en la configuración de VSFTPD?
    A. Definen el puerto de control (21)
    B. Definen el rango de puertos para las conexiones de datos en modo pasivo
    C. Definen los puertos que el cliente debe usar para el control
    D. Definen el puerto de datos en modo activo (20)

35. ¿Cómo se denomina el proceso de limitar a los usuarios locales a su directorio de inicio después de iniciar sesión en VSFTPD?
    A. Logging
    B. Chroot
    C. NAT
    D. SSL

36. En VSFTPD, ¿qué directiva es la "mágica" para encerrar al usuario en su directorio *home*?
    A. write_enable=YES
    B. allow_writeable_chroot=YES
    C. chroot_local_user=YES
    D. listen=YES

37. Para evitar el famoso error "500 OOPS" cuando la carpeta raíz del usuario enjaulado tiene permisos de escritura, ¿qué directiva se debe usar en VSFTPD?
    A. chroot_local_user=NO
    B. pasv_enable=NO
    C. allow_writeable_chroot=YES
    D. local_enable=NO

38. Al configurar VSFTPD con Docker, ¿qué bandera se utiliza para vincular un archivo o directorio del host al contenedor, asegurando un acceso persistente a los archivos?
    A. `-p`
    B. `-e`
    C. `--name`
    D. `-v`

39. Si en una configuración de Docker para VSFTPD se utilizan los puertos `-p 21100-21110:21100-21110`, ¿a qué corresponde este rango de puertos?
    A. Conexión de Control
    B. Conexión de Datos en Modo Activo
    C. Conexión de Datos en Modo Pasivo
    D. Conexión SSH

40. En el proceso para añadir más usuarios virtuales a VSFTPD en Docker, ¿qué herramienta se utiliza para convertir el archivo de texto `virtual_users.txt` en una base de datos hash que vsftpd puede utilizar para autenticar a los usuarios?
    A. `db_load`
    B. `docker restart`
    C. `mkdir`
    D. `echo`

#### VI. Seguridad: FTPS y SFTP

41. ¿Cuál es la diferencia fundamental entre **SFTP** y **FTPS**?
    A. SFTP usa el puerto 21; FTPS usa el puerto 22.
    B. FTPS es el FTP tradicional con SSL/TLS; SFTP funciona sobre SSH.
    C. SFTP no requiere cifrado; FTPS sí.
    D. FTPS es el protocolo nativo de OpenSSH; SFTP es el nativo de VSFTPD.

42. Para asegurar una conexión FTPS, la conexión debe utilizar el cifrado:
    A. SSH File Transfer Protocol
    B. FTP implícito sobre TLS
    C. Requiere FTP explícito sobre TLS (Explicit FTP over TLS)
    D. OpenSSL en Modo Pasivo

43. Al generar certificados para FTPS con OpenSSL, ¿qué archivo es la **Clave Privada** que no se debe compartir?
    A. `vsftpd.crt`
    B. `vsftpd.key`
    C. `sftp_key.pub`
    D. `vsftpd.conf`

44. ¿Qué protocolo de red proporciona autenticación fuerte y cifrado de datos y se utiliza como base para SFTP?
    A. FTP
    B. OpenSSL
    C. SSH (Secure Shell)
    D. TCP

45. ¿Cuál es una ventaja clave de usar OpenSSH para un servidor SFTP en comparación con FTP/FTPS, según las fuentes?
    A. Requiere múltiples puertos de conexión
    B. Proporciona cifrado total de extremo a extremo por defecto
    C. Permite el acceso sin necesidad de autenticación
    D. Es incompatible con la autenticación por llaves

46. En la autenticación mediante **pares de claves criptográficas SSH**, ¿cuál es la "cerradura" que se pone dentro del servidor Docker (la que puede ser compartida)?
    A. La Clave Privada (`sftp_key`)
    B. La Clave Pública (`sftp_key.pub`)
    C. La contraseña
    D. El certificado SSL

47. ¿Qué puerto se utiliza típicamente para las conexiones SFTP sobre SSH?
    A. 20
    B. 21
    C. 22
    D. 80

48. Cuando se configura la "jaula" (Chrooting) en un servidor SFTP con la imagen `atmoz/sftp`, ¿qué significa que el usuario verá su carpeta como si fuera la raíz (/)?
    A. Que podrá subir de nivel para ver archivos de configuración del servidor
    B. Que estará confinado estrictamente a su directorio asignado
    C. Que la transferencia de archivos fallará
    D. Que se requiere un certificado autofirmado

49. Si se usa la imagen `atmoz/sftp` y el "truco" del Chroot, el usuario tendrá permisos de escritura en la subcarpeta `/home/miusuario/archivos`, mientras que la carpeta raíz `/home/miusuario/` será propiedad de:
    A. El usuario `miusuario`
    B. El usuario `root`
    C. El grupo `ftp`
    D. El usuario `daemon`

50. Cuando se utiliza FTP en un servicio como Spring Boot o similar, ¿qué librería de Apache se menciona para su uso?
    A. `spring-boot-starter-web`
    B. `java.io.File`
    C. `commons-net`
    D. `OpenSSL`
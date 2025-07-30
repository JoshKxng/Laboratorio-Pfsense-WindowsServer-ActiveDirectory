# 🧪 Laboratorio: pfSense en Windows Server 2019 + Active Directory

Este laboratorio, simula una red empresarial en entorno virtual con **pfSense** y **Windows Server 2019**, integrando funcionalidades clave como:

- Configuración de Active Directory
- Control de navegación con proxy transparente (Squid)
- Filtrado de contenido con SquidGuard
- Reglas de firewall personalizadas
- Autenticación de usuarios por grupos
- Acceso remoto con SSH

---

## 🖥️ Tecnologías utilizadas

||
|---------------------------|
| 🪟 **Windows Server 2019** |
| 🔐 **Squid + SquidGuard** |
| 🔑 **Active Directory** |
| 📡 **DHCP, DNS, Firewall** |

---

## 📌 Creando nuestro servidor e integrando Active Directory
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/41.%20Integraci%C3%B3n%20de%20Pfsense%20con%20Windows%20Server%20y%20Active%20Directory/02%20-%20AD%20ya%20instalado.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/41.%20Integraci%C3%B3n%20de%20Pfsense%20con%20Windows%20Server%20y%20Active%20Directory/01.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/41.%20Integraci%C3%B3n%20de%20Pfsense%20con%20Windows%20Server%20y%20Active%20Directory/02%20-%20AD%20funcionando.png)

---
## 📌 Aca vemos integración exitosa entre pfSense y Active Directory. Configuré AD en Windows Server 2019, creando el usuario "pfsense" en el dominio "Joshua.host" y estableciendo las credenciales necesarias
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/42.%20Primer%20Practica.%20Usamos%20Active%20Directory%2C%20creamos%20usuario%20y%20lo%20vinculamos%20con%20pf/00%20-%20Creando%20Usuario%20en%20Windows%20Server.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/42.%20Primer%20Practica.%20Usamos%20Active%20Directory%2C%20creamos%20usuario%20y%20lo%20vinculamos%20con%20pf/01%20-%20Usuario%20pfsense%20creado.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/42.%20Primer%20Practica.%20Usamos%20Active%20Directory%2C%20creamos%20usuario%20y%20lo%20vinculamos%20con%20pf/02%20-%20Vista%20avanzada%20de%20AD%20.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/42.%20Primer%20Practica.%20Usamos%20Active%20Directory%2C%20creamos%20usuario%20y%20lo%20vinculamos%20con%20pf/02b%20-%20Search%20Scope.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/42.%20Primer%20Practica.%20Usamos%20Active%20Directory%2C%20creamos%20usuario%20y%20lo%20vinculamos%20con%20pf/02c%20-%20Search%20Scope.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/42.%20Primer%20Practica.%20Usamos%20Active%20Directory%2C%20creamos%20usuario%20y%20lo%20vinculamos%20con%20pf/03%20-%20Server%20Autentificado.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/42.%20Primer%20Practica.%20Usamos%20Active%20Directory%2C%20creamos%20usuario%20y%20lo%20vinculamos%20con%20pf/03b%20-%20Server%20Autentificado.png)

---

## 📌 Acá configuramos el servidor LDAP en pfSense con los siguientes parámetros clave:
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/42.%20Primer%20Practica.%20Usamos%20Active%20Directory%2C%20creamos%20usuario%20y%20lo%20vinculamos%20con%20pf/04%20-%20Nuevo%20Usuario%20en%20pfsense.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/42.%20Primer%20Practica.%20Usamos%20Active%20Directory%2C%20creamos%20usuario%20y%20lo%20vinculamos%20con%20pf/04b-%20Configuracion%20Correcta.png)
## 📌 Acá vemos que el logeo fue éxitoso.
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/42.%20Primer%20Practica.%20Usamos%20Active%20Directory%2C%20creamos%20usuario%20y%20lo%20vinculamos%20con%20pf/05%20-%20Ingresando%20con%20nuestro%20nuevo%20usuario%20pfsense.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/42.%20Primer%20Practica.%20Usamos%20Active%20Directory%2C%20creamos%20usuario%20y%20lo%20vinculamos%20con%20pf/05b%20-%20Ingresando%20con%20nuestro%20nuevo%20usuario%20pfsense.png)

---
## 📌 Ahora vinculamos nuestro AD con el servicio de Squid.
## Acá cree un nuevo usuario
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/43.%20Vinculamos%20nuestro%20Active%20Directory%20con%20Squid/00.png)

---
## 📌 Configuré la autenticación general de Squid modificando los parámetros por defecto que traía
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/43.%20Vinculamos%20nuestro%20Active%20Directory%20con%20Squid/01.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/43.%20Vinculamos%20nuestro%20Active%20Directory%20con%20Squid/02.png)

---
## 📌 Con nuestro Proxy activado y el servicio de Squid en funcionamiento, podemos ver como el navegador le pide al usuario que hemos creado, una credencial y una contraseña para poder navegar.
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/43.%20Vinculamos%20nuestro%20Active%20Directory%20con%20Squid/Captura%20de%20pantalla%202025-07-29%20231248.png)

---
## 📌 Ahora implementamos una blacklist. ¿Para que sirve esto? Esto nos sirve para el bloqueo a distintas páginas de internet según su contenido. Ideal para una organización que cuenta con empleados y necesita mantener un control seguro.
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/44.%20Instalaci%C3%B3n%20y%20configuraci%C3%B3n%20de%20squidguard/Captura%20de%20pantalla%202025-07-29%20235946.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/44.%20Instalaci%C3%B3n%20y%20configuraci%C3%B3n%20de%20squidguard/Captura%20de%20pantalla%202025-07-29%20235916.png)

---
## 📌 Acá podemos ver las categorias que trae la blacklist que hemos instalado. Podemos permitir o denegar el acceso a estas categorias. Por ejemplo, vamos a bloquear el acceso a todas las páginas que sean Redes Sociales para evitar que nuestros empleados ingresen a ellas.
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/44.%20Instalaci%C3%B3n%20y%20configuraci%C3%B3n%20de%20squidguard/Captura%20de%20pantalla%202025-07-30%20001834.png)

---
## 📌 Ahora bien, podemos ingresar a Google y verificar si nuestra regla se cumple.
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/44.%20Instalaci%C3%B3n%20y%20configuraci%C3%B3n%20de%20squidguard/Captura%20de%20pantalla%202025-07-30%20002901.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/44.%20Instalaci%C3%B3n%20y%20configuraci%C3%B3n%20de%20squidguard/Captura%20de%20pantalla%202025-07-30%20003302.png)

---
## 📌 Efectivamente, la regla que hemos aplicado funciona
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/44.%20Instalaci%C3%B3n%20y%20configuraci%C3%B3n%20de%20squidguard/Captura%20de%20pantalla%202025-07-30%20003233.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/44.%20Instalaci%C3%B3n%20y%20configuraci%C3%B3n%20de%20squidguard/Captura%20de%20pantalla%202025-07-30%20003017.png)

---
## 📌 Por último vamos a implementar el servicio de SquidGuard con active directory y configurar permisos por grupo

---
## 📌 Configuramos nuestro servicio SquidGuard con los parámetros referentes a nuestro AD
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/45.%20Integracion%20de%20squidguard%20con%20active%20directory%20y%20permisos%20por%20grupo/01.png)

---
## 📌 Creamos nuestro grupo de "bloqueados" como filtro para identificar usuarios
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/45.%20Integracion%20de%20squidguard%20con%20active%20directory%20y%20permisos%20por%20grupo/02.png)

---
## 📌 Agregamos al usuario JoshuaRanure al grupo de los bloqueados
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/45.%20Integracion%20de%20squidguard%20con%20active%20directory%20y%20permisos%20por%20grupo/03.png)

---
## 📌 Dentro de la query ingresamos los datos correctos desde el controlador de dominio Active Directory
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/45.%20Integracion%20de%20squidguard%20con%20active%20directory%20y%20permisos%20por%20grupo/04.png)

---
## 📌 Ahora vamos a nuestra blacklist y vamos a Denegar el acceso a los sitios que sean Redes Sociales
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/45.%20Integracion%20de%20squidguard%20con%20active%20directory%20y%20permisos%20por%20grupo/05.png)

---
## 📌 Y ahora vamos a intentar acceder a una red social, desde el navegador de Google Chrome y veremos que el usuario no podrá acceder a ella.
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/45.%20Integracion%20de%20squidguard%20con%20active%20directory%20y%20permisos%20por%20grupo/06.png)

---
## 📌 Importante, si el usuario intentase acceder por el modo incógnito, támpoco podría. Por lo tanto, nuestra configuración ha sido éxitosa.
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/45.%20Integracion%20de%20squidguard%20con%20active%20directory%20y%20permisos%20por%20grupo/07.png)

---
## 🏆🫶 Muchas gracias por quedarte hasta el final!

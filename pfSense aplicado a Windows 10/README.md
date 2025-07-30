# 🧪 Pruebas Iniciales con pfSense en Windows 10

Este apartado documenta las configuraciones y pruebas realizadas en un entorno controlado con **pfSense** y una VM con **Windows 10**.

📌 El objetivo de esta fase fue **familiarizarme con la interfaz, funciones clave y comportamiento del firewall pfSense**, antes de integrarlo con Windows Server y Active Directory.

Durante estas prácticas, apliqué configuraciones esenciales como:

- **Creación de usuarios y reglas personalizadas 🔐**
- **Ajustes de red y DHCP en pfSense 🌐**
- **Habilitación del acceso remoto mediante SSH usando KiTTY 💻**
- **Pruebas de conectividad desde redes internas y externas 🔄**

---
### 📌 Primero para familiarizarme con pfSense, empecé a implementar las configuraciones del Firewall en una VM de Windows 10. Como se puede ver, tenemos por un lado la VM con la CLI de pfSense y por el otro, tenemos la VM de Windows 10 con la GUI de pfSense.
 
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/01.png)

---

### 📌 Creación de usuarios en pfSense
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/02%20-%20Creacion%20de%20usuarios%20Pfsense.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/02b%20-%20Creacion%20de%20usuarios%20Pfsense.png)

---
### 📌 Creación de Reglas para un usuario
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/03%20-%20Creaci%C3%B3n%20de%20reglas.png)

---
### 📌 Regla aplicada al usuario ´Usuario_Invitado´
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/03%20-%20Regla%20aplicada%20al%20usuario%20Usuario_Invitado.png)

---
### 📌 Modificando red LAN
### Se cambió la configuración de red de la interfaz LAN en pfSense, lo cual es necesario para establecer una red interna con un rango distinto al de fábrica 192.168.1.1 | Le asigné la IP 192.168.2.1

![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/05%20-%20Modificando%20red%20LAN.png)

---

### 📌 Desactivamos momentáneamente el Firewall para entrar desde afuera. Esto se hace cuando se quiere probar la comunicación desde pfSense hacia el servidor
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/06%20-%20Firewall%20desactivado%20para%20entrar%20desde%20afuera.png)

---

### 📌 Entrando desde afuera a la nueva IP. Este paso valida que la red esté funcionando correctamente y que se pueda acceder al servidor luego de cambiar la IP de pfSense.
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/07%20-%20Entrando%20desde%20afuera%20a%20la%20nueva%20IP.png)

---

### 📌 DHCP Server Modificado
### Acá modificamos el rango de direcciones IP asignadas por el servidor DHCP de pfSense, para que nos entregue nuevas direcciones dentro del nuevo rango de la LAN

![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/08%20-%20DHCP%20Server%20Modificado.png)

----

### 📌 Se activó el servicio SSH (Secure Shell) desde la configuración de pfSense. Esto nos permite acceder a pfSense por consola usando un cliente como KiTTY

![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/09A-%20Activando%20Secure%20Shell.png)

----
### 📌 Acá vemos la regla creada dentro del firewall de pfSense. Es una regla en la interfaz LAN que permite tráfico entrante al puerto 22 (SSH). Esto permite que clientes como KiTTY puedan conectarse desde una máquina conectada a la misma red LAN.
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/09B-%20Regla%20activada.png)

----
### 📌Utilizamos KiTTY para conectarnos al firewall pfSense por SSH. Al hacer clic en “Open”, KiTTY abre una terminal para ingresar usuario y contraseña (en este caso, admin y la contraseña de pfSense). Esto permite administrar pfSense por consola remota
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/11%20-%20Kitty.png)
![](https://github.com/JoshKxng/Laboratorio-Pfsense-WindowsServer-ActiveDirectory/blob/main/pfSense%20Imagenes/12.png)

---

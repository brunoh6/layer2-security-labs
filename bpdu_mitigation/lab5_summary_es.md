# Resumen del Laboratorio 5 – Metasploit y Pivoting

## Objetivo
Este laboratorio se centró en el uso de Metasploit para obtener acceso a una máquina vulnerable, ejecutar una reverse shell, explorar redes internas y realizar escalamiento de privilegios y persistencia.

## Herramientas y Entorno
- Kali Linux
- Máquina virtual lab-msf
- Metasploit Framework
- Wireshark
- ProxyChains
- Jupyter Notebooks
- EVE-NG (para red simulada)

## Pasos Clave

### Acceso Inicial
- Se identificó la IP de la VM objetivo (192.168.36.162) mediante captura de paquetes y escaneo Nmap.
- Se utilizó el módulo `scanner/http/http_login` con listas por defecto.
- Se obtuvo acceso exitoso con las credenciales `admin:Password`.
- Acceso verificado en el panel administrativo con comandos (`ps aux`, `whoami`, etc.).

### Reverse Shell
- Se configuró Netcat en Kali como listener.
- Se generó payload en revshells.com.
- Se estableció una shell remota con payload en Python.
- Se actualizó la sesión a Meterpreter para funcionalidades avanzadas (`hashdump`, `screenshot`, etc.).

### Técnica de Pivoting
- Uso de `autoroute` en Meterpreter para habilitar enrutamiento interno.
- Configuración de proxy SOCKS y ProxyChains.
- Escaneo de la red 192.168.10.0/24 con `nmap` a través del proxy.
- Descubrimiento de múltiples hosts con SSH/HTTP abiertos.
- Redirección de puertos y acceso SSH a 192.168.10.20.

### Enumeración Interna
- Identificación de versión OpenSSH.
- Uso de CVE para enumerar usuarios y luego acceso por fuerza bruta.
- Credenciales encontradas: `user:P@ssw0rd`.
- Lectura de archivo sensible tras ingreso exitoso.

### Persistencia
- Uso de `post/linux/manage/adduser` para crear usuario privilegiado `paolo`.
- Adición de clave pública SSH para acceso sin contraseña.
- Verificación de acceso sudo y privilegios de comandos.

## Conclusión
Este laboratorio demostró un ciclo completo de ataque: reconocimiento, explotación, post-explotación (pivoting, escaneo interno) y establecimiento de persistencia. El uso de Metasploit y ProxyChains ilustra técnicas reales del Red Team en redes segmentadas.

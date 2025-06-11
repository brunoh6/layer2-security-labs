# Resumen del Laboratorio 4 – Seguridad de Capa 2 con Scapy

## Objetivo
Este laboratorio se centró en simular ataques de capa 2 y aplicar medidas de protección utilizando Scapy, Jupyter y configuraciones de switches.

## Herramientas y Entorno
- Switches Cisco (SW1-SW5)
- Servidor Linux con Scapy y Jupyter
- EVE-NG
- VPCs
- Protocolos DHCP, ARP, STP

## Secciones Clave

### Configuración de la Topología
- Red interna configurada con GW1 (192.168.6.1) y VPCs.
- Asignación de IP estáticas y por DHCP.
- Reglas de NAT y ACL en el router para acceso a Internet.

### Protección DHCP
- Simulación de ataque DHCP starvation con script de Scapy.
- Intento de servidor DHCP falso.
- Activación de DHCP snooping para bloquear ofertas falsas.
- Seguridad de puerto configurada para limitar direcciones MAC.

### Protección ARP
- Ataque ARP spoofing simulado con Scapy.
- Inspección ARP dinámica activada en la VLAN 1.
- Puertos confiables definidos; ataques bloqueados.

### Protección STP
- Ataque STP simulado cambiando el root bridge con paquetes maliciosos.
- Activación del filtro BPDU en puertos de acceso para bloquear manipulación.

## Conclusión
La seguridad en capa 2 es esencial contra amenazas internas. El laboratorio demostró ataques reales y medidas efectivas de protección usando Scapy y funciones de Cisco.

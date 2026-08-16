# Configuración de Infraestructura de Red — Liceo Electrotecnia "Ramón Barros Luco"

Repositorio de respaldo y documentación de las configuraciones de red implementadas 
en el marco del proyecto **"Diseño y Mejoramiento de la Infraestructura de Red de un Liceo"** 
(Taller de Integración Profesional, IP San Sebastián).

## Contexto del proyecto

El liceo contaba con una red plana sin segmentación, sin monitoreo de enlaces y con 
control de acceso WiFi basado en filtrado manual de direcciones MAC. Este repositorio 
documenta las configuraciones resultantes del rediseño, orientado a tres pilares:

- **Seguridad y control de acceso**: autenticación WPA2-Enterprise vía FreeRADIUS
- **Optimización del rendimiento**: segmentación por VLANs y QoS
- **Gestión proactiva**: monitoreo centralizado con Zabbix

## Contenido del repositorio

| Carpeta / Archivo | Descripción |
|---|---|
| `/freeradius/clients.conf` | Definición de clientes RADIUS (NAS) autorizados |
| `/freeradius/users` | Usuarios de prueba para autenticación WPA2-Enterprise |
| `/switches/cisco-2960/` | Configuración de VLANs y etiquetado 802.1Q |
| `/switches/meraki/` | Configuración de switches core Meraki MS220 |
| `/zabbix/` | Plantillas SNMP y configuración de alertas |
| `/docs/topologia.png` | Diagrama de topología lógica posterior a la implementación |

## Arquitectura de red

- **VLAN 10** — Administrativa (prioridad alta)
- **VLAN 20** — Docentes/Pedagógica (prioridad media)
- **VLAN 30** — Estudiantes (prioridad baja, con traffic shaping)
- **VLAN 40** — Cámaras y NVR (prioridad crítica, aislada)

## Servicios implementados

- **FreeRADIUS 3.2.8** sobre Ubuntu Server 26.04 — autenticación centralizada 802.1X/WPA2-Enterprise
- **Zabbix 7.0 LTS** sobre Ubuntu Server 26.04 — monitoreo SNMP de switches y enlaces, con alertas por correo

## Estado del proyecto

🟢 Configuración validada en entorno de maqueta (VMware).  
⏳

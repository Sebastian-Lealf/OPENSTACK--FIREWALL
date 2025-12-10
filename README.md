# LABORATORIO DE UN FIREWALL CON OPENSTACK Y DEBIAN

Guia breve y estructurada del laboratorio de firewall sobre OpenStack y Debian.

## Datos generales
- Docente: Jorge Eliecer Gomez Gomez
- Integrantes: Diaz Cabarcas Camilo Andres; Garcia Molina Javier Andres; Gonzalez Echavarria Andres Camilo; Leal Florez Sebastian Jose
- Universidad de Cordoba – Facultad de Ingenierias – Ingenieria en Sistemas – Monteria, Cordoba – 2025

## Alcance del laboratorio
- Plataforma: VirtualBox como hipervisor, Debian como base, OpenStack/DevStack para redes y VMs.
- Redes: subred interna 192.168.100.0/24, router con SNAT, DHCP y DNS (8.8.8.8, 1.1.1.1).
- Firewall: UFW en modo deny incoming / allow outgoing; reglas para 22/80/443/8080 y tráfico interno.
- Validación: generación de tráfico controlado, capturas con tcpdump/Wireshark y revisión de puertos permitidos/bloqueados.

## Entregables
- Documento: `Laboratorio Firewall Openstack.pdf`.
- Video: https://www.youtube.com/watch?v=tVFbZFyOUEc.

## Flujo resumido
1) Instalar VirtualBox y crear VM Debian.
2) Desplegar DevStack (OpenStack) y crear red, subred, router y grupos de seguridad.
3) Lanzar instancias Debian (servidor y cliente) con cloud-init para acceso y red.
4) Aplicar UFW con políticas por defecto y puertos permitidos; habilitar logging.
5) Generar tráfico de prueba (SSH, HTTP/S, 8080, ICMP, MySQL, RDP) y capturar en cliente/servidor/host.
6) Analizar .pcap en Wireshark para confirmar allow/deny según las reglas.

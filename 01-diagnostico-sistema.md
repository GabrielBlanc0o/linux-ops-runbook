# Capítulo 1: Guía de Diagnóstico Inicial en Linux (System Health)

Este documento detalla el procedimiento estándar de comprobación del estado del servidor y solución de problemas iniciales para entornos Linux (Ubuntu Server / Debian).

---

## 1. Inspección de Recursos Físicos

### Memoria RAM
Para verificar la memoria disponible antes de que ocurra un evento de *Out Of Memory (OOM)*:
```bash
free -h
```
### Almacenamiento en Disco
Para revisar la capacidad ocupada en las particiones del sistema:

```bash
df -h
```
*Si el punto de montaje / supera el 85% de ocupacion , es recomendalbe purgar logs antiguos*
*o archivos temporales antes de que los servicios dejen de escribir datos.*

### Carga del Procesador y Tiempo de Actividad 
Muestra el tiempo encendido y el promedio de carga (load average) a 1, 5 y 15 minutos.

```bash
uptime
```

## 2. Diagnostico de Red y Servicios

###  Estado de Puertos TCP/UDP Activos
Para comprobar que servicios estan escuchando peticiones en la red: 

```bash
sudo ss -tulpn
```
Por ejemplo: 

Netid  |   State   |   Recv-Q   |  Send-Q      |                         Local Address:Port       |     Peer Address:Port  |
Process          |                                                                                                        


tcp    |   LISTEN   |  0       |   4096        |                                  [::]:22          |            [::]:*    |     users:(("sshd",pid=5827,fd=4),("systemd",pid=1,fd=188))    


### Verificacion de Servicios con Systemd
Ver el estado de un servicio o esta fallando

```bash 
sudo systemctl status ssh
```

### Inspeccion de Registros (Logs)
Para examinar los ultimos eventos de un servicio especifico:
```bash 
sudo journalctl -u ssh -n 20
```
Y para monitorear el registro global del sistema en tiempo real:
```bash
tail -f /var/log/syslog
```
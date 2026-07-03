# Proyecto SO I - Grupo 6
## Despliegue de Nextcloud mediante Podman en modo rootless sobre AWS EC2

Proyecto desarrollado para el curso **Sistemas Operativos I** de la **Universidad ESAN**.

## Integrantes

- Adriano Andre Catacora Iriarte
- Cesar Emanuel Dioses Santos
- Diego Alonso Moreno Chujutalli
- Karen Noelia Ramírez Quevedo

## Descripción

Este proyecto consiste en el despliegue de **Nextcloud** utilizando **Podman en modo rootless** sobre una instancia **Ubuntu Server 24.04 LTS** en **AWS EC2**.

La solución implementa un contenedor para **Nextcloud** y otro para **MariaDB**, conectados mediante una red privada y utilizando volúmenes persistentes para conservar la información.

---

## Tecnologías utilizadas

- Podman (Rootless)
- Quadlet (.container)
- Nextcloud
- MariaDB
- Ubuntu Server 24.04 LTS
- Amazon EC2
- DuckDNS
- systemd

---

## Contenido del repositorio

```
.
├── nextcloud.container
├── mariadb.container
├── Informe_Tecnico_Nextcloud_Grupo6.pdf
└── README.md
```

### Archivos

- **nextcloud.container**: configuración del servicio Nextcloud mediante Quadlet.
- **mariadb.container**: configuración del servicio MariaDB.
- **Informe_Tecnico_Nextcloud_Grupo6.pdf**: informe técnico del proyecto.
- **README.md**: documentación del repositorio.

---

## Despliegue

Los contenedores fueron administrados mediante **Quadlet** y **systemd**, permitiendo el inicio automático de los servicios.

Una vez instalados los archivos `.container`, los servicios pueden administrarse con:

```bash
systemctl --user daemon-reload
systemctl --user start mariadb
systemctl --user start nextcloud

systemctl --user status mariadb
systemctl --user status nextcloud
```

---

## Evidencias realizadas

Durante el desarrollo se verificó:

- Estado de los contenedores con `podman ps`
- Procesos mediante `podman top`
- Namespaces utilizando `lsns`
- Consumo de CPU y memoria con `podman stats`
- Modificación de límites de recursos mediante `podman update`
- Persistencia de datos utilizando volúmenes de Podman

---

## Video de demostración

> https://drive.google.com/file/d/1KCzdMkJSKK445VmmHROS0qDdtLV-uH4x/view?usp=sharing

---

## Aplicación desplegada

[http://grupo6-nextcloud.duckdns.org
](http://3.129.51.85/login?redirect_url=/apps/files/files/175?dir%3D/Proyecto%2520SO)
---

## Referencias

- Podman Documentation: https://docs.podman.io
- Operating Systems: Three Easy Pieces: https://ostep.org
- Silberschatz, Galvin & Gagne. *Operating System Concepts* (10th Edition).
- Stallings, W. *Operating Systems: Internals and Design Principles* (9th Edition).

---

**Curso:** Sistemas Operativos I  
**Universidad ESAN**  
**Ciclo 2026-I**

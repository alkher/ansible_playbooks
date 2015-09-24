*****************
Ansible Playbooks
*****************

Repositorio con diversos playbooks para realizar tareas sencillas.

.. contents:: Contenido

Requisitos
==========

:Ansible: `ansible`_ versión 1.2 y posteriores.
:Variables: Revisar las variables antes de ejecutar el playbook.

**********************
Instalar elasticsearch
**********************

**instalar_es.yml**

Instalación y configuración de eleasticsearch en un stack ELK_.

*****************
Instalar logstash
*****************

**instalar_ls.yml**

Instalación y configuración de logstash en un stack ELK_.

******************************
Cambiar contraseña de usuarios
******************************

**cambiar_password.yml**

Cambiar la contraseña de un usuario.

Variables
=========

	**usuario**: root        # Usuario
    **password**: $6$1/K.Dax # contraseña [Generada con: mkpasswd --method=SHA-512]

*****************************
Añadir elementos a /etc/hosts
*****************************

**modificar_etc_hosts.yml**

Añadir entradas a /etc/hosts.

****************
Trabajar con LVM
****************

**linux_lvm.yml**

Crear, eliminar y/o modificar un volumen lógico.

Verificado en CentOS 6 y 7.

Variables
=========

	**lvm_ope**: ''          # Operación que se quiere realizar, los valores posibles son: 'crear', 'borrar' y 'extender'.
    **vgname**: 'datos-vg'   # Nombre del VG.
    **disks**: '/dev/sdb'    # Discos para el VG ('/dev/sdb,/dev/sdc,/dev/sdd,...'). En el caso de una extensión hay que indicar todos los discos, no solo el que se añade.
    **lvname**: 'datos-lv'   # Nombre del LV.
    **mnt_point**: '/datos'  # Punto de montaje para el LV.
    **lvsize**: '100%FREE'   # Tamaño del LV ('10G' para un LV de 10 GB, '512' para uno de 512 MB).
    **fs_type**: 'ext4'      # Tipo del filesystem para el LV (ext3, ext4, xfs, ...).
    **extend_opt**: '-L+10G' # Opciones de lvextend ('-L+10G' para incrementar 10 GB el tamaño, '-l+100%FREE' para usar todo el espacio libre).

.. _ELK: https://www.elastic.co/products
.. _ansible: http://www.ansible.com/home
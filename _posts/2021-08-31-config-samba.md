---
title: Configuracion Basica Samba
published: true
---

 Samba es un servidor de archivos y aunque puede parecer complejo en realidad solo requiere
de algunas configuraciones basicas para poder funcionar sin problemas.

Lo primero, instalamos Samba

```bash
sudo apt install samba
```
Verificamos su estado...

```bash
sudo systemctl status smbd
```
Deberia darnos algo asi:

>smbd.service - Samba SMB Daemon
>  Loaded: loaded (/lib/systemd/system/smbd.service; disabled; vendor preset: disabled)
>  Active: inactive (dead)
>  Docs: man:smbd(8)
>        man:samba(7)
>        man:smb.conf(5)



Bien, ahora por `seguridad` haremos un respaldo del archivo de configuracion de samba, esto
es por si la cag*** podamos dejar todo como estaba. El archivo se encuentra 
en `/etc/samba/smb.conf`

Tal cual hacemos..


```bash
sudo cp /etc/samba/smb.conf smb.conf.save
```

Con esto ya tendriamos nuestro respaldo hecho.

Vamos a crear un directorio donde alojaremos los archivos que vamos a compartir:

```bash
mkdir files
```


Ahora debemos editar nuestro archivo de configuracion y al final agregamos lo siguiente:

```bash
[files]
path=/home/user/files
browseable= yes
writeable= yes
only guest= no
create mask=0777
directory mask=0777
public= no

```
Para que esto funcione, debemos de crear una contraseña para nuestro usuario, esta debe ser
diferente a la que utilizamos normalmente, por seguridad debe ser asi.

```bash
smbpasswd -a usuario
```

Con esto practicamente ya tendriamos todo hecho

Reinicamos el servicio Samba

```bash
sudo systemctl restart smbd
```

Buscamos nuestro servicio, sabremos la IP y depaso veremos si esta corriendo.

```bash
findsmb
```

Utilizaremos `smbclient` para conectarnos al servidor

```bash
smbclient -U meta //192.168.0.28/files
```

Deberia de aparecernos algo asi
```bash
smb:\>
```
Y listo, ya podemos gestionar nuestro servidor, espero que les haya servido, proximamente
el video, bytes.

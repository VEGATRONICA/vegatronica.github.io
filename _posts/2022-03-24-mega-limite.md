---
title: Saltar Limite de Mega en Linux
published: true
---

Cuando descargamos algo de Mega y sobre todo algo pesado al poco nos salta el mensaje que hemos superado el limite
de descarga permitido y tendremos que esperar(bastante) para seguir descargando donde nos quedamos u otra cosa,
pero hay manera de hacer lo mismo en linux de lo que hacia **megadownloader** en winbug :)

En primera necesitaremos una aplicacion llamada **Megabasterd** que corre en java la cual
podemos descargar de aqui
[Descarga](https://github.com/tonikelope/megabasterd/releases/tag/v7.50)

Posteriormente debemos instalar 2 utilidades mas **tor** y **privoxy**

```bash
sudo apt install tor
sudo apt install privoxy
```
Ahora vamos a configurar algunas cosas para dejar todo funcionando, abrimos la configuracion de Megabasterd
e introducimos en la seccion de Proxy lo siguiente:

```bash
Proxy HTTP: 127.0.0.1
Puerto: 8118
```
Con esto ya quedaria megabasterd listo, ahora solo falta editar un archivo y todo deberia andar bien, para eso editamos
en la siguiente ruta

```bash
sudo nano /etc/privoxy/config/
```
Y en la ultima linea colocamos lo siguiente tal cual(muy importante)

```bash
forward-socks4a / localhost:9050 .
```
Ahora ya solo faltaria iniciar los servicios cuando el limite de descarga se acabe.

```bash
sudo /etc/init.d/tor start
sudo /etc/init.d/privoxy start
```

Y para cambiar la IP solo basta detener e iniciar nuevamente los servicios, se podria hacer comodamente un
script para hacer esto de manera automatica y no estarlo escribiendo:

```bash
sudo /etc/init.d/tor stop
sudo /etc/init.d/privoxy stop
sudo /etc/init.d/tor start
sudo /etc/init.d/privoxy start
```

Tambien otro forma de iniciar los servicios podria ser...

```bash
sudo systemctl start tor
sudo systemctl start privoxy

```
Y esto seria todo, espero que te haya sido de utilidad, bytes

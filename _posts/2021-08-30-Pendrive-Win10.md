---
title: Crea una Pendrive de Windows 10 desde Linux
published: true
---

Con solamente utilizar la terminal y algunas pequeñas herramientas nos podemos armar una
pendrive de Winbug 10 desde Linux, , esto sirve para `Winbug 8, 8.1 y 10` sin embargo
no funciona para `Winbug 7`

  Aunque podria dar algunos errores en la ejecucion aqui la lista de comandos por si falta
alguna herramienta, despues de eso el proceso es bastante sencillo aunque tardara dependiendo
de la velocidad de tu PC.

```bash
curl -L  https://git.io/bootiso -O
sudo apt install wimtools
sudo apt install syslinux
sudo apt install extlinux
sudo apt install jq
sudo apt install bc

```
 Por supuesto no puede faltar el video, espero les sea de utilidad, dejo el link ya que
Github aun no permite embebber los videos, oh por lo menos eso creo yo.

Bytes.

[Link hacia el video](https://www.youtube.com/watch?v=yXm-JovCWHk&t=210s).

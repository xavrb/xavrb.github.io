---
layout: post
title: Encontrando el archivo que ocupa más
tags: [espacio, shell]
---

Dropbox me notificó que me estaba quedando sin espacio por que el cupon universitario iba a expirar. ¿El problema? No sabía qué estaba ocupando tanto espacio en mi cuenta.


# Entra un shell
Ahí es cuando un simple comando de shell nos puede salvar horas de búsqueda. Y claro, puede intentar hacerlo con una gui como Nautilus o thunar, pero el problema es que estas aplicaciones intentan cargar el mayor número de *thumbnails* posibles, y en general es lento el proceso de ordenar por tamaño.

## Solución
Un simple comando, spoiler:

{% highlight bash %}
du -sh * | sort -hr | head -n10
{% endhighlight %}

`du` es, literalmente lo que necesaitaba (disk usage), y entrega un resumen de el espacio usado en el directorio donde lo ejecutes, a saber:  
* **-s**: entrega un resumen nadamás (summarize)  
* **-h**: human-readable, para  los no-máquinas allá afuera. Entrega lo que ocupan los directorios en M(MB), G(GB), etc.  

`sort`, comando para ordenar.

* **-h**: human-numeric-sort, compara entre la salida que nos dio `-h` del comando anterior.  
* **-r**: reversa.

`head -n10`: Entrega los primeros 10 resultados.


Y listo, con eso podemos hacer una búsqueda precisa para encontrar aquello que está saturando esas cuentas de Dropbox.  





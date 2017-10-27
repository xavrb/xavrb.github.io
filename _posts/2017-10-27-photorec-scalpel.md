---
layout: post
title: Análisis forense no formal con Photorec y Scalpel: O cómo recuperar las fotos que borraste por accidente
tags: [recuperación]
---


¿Qué es peor que eliminar un archivo por accidente?, no encontrarlo ni en la papelera de reciclaje. `*horror.ogg*`  

# Análisis forense no formal con Photorec y Scalpel  

## ¿Se fueron para siempre?

TL;DR; **No.**  
Cuando elminamos un archivo de cualquier dispositivo de almacenamiento (ya sea una USB, un disco duro externo o el que viene con nuestra PC) lo único que el sistema operativo hace es `*marcar*` el espacio de almacenamiento ocupado por ese archivo como `Disponible`. Pero el compendio de `0`s y `1`s de nuestro archivo sigue ahí, por un tiempo.  
¿Hasta cuando? Hasta que el sistema necesite ese espacio para algún otro archivo y decida utilizarlo. Es por eso que en estos casos las escrituras a disco (o al dispositivo de almacenamiento) son nuestro peor enemigo, y empieza nuestra carrera contra el tiempo. Esto en caso de que sea el disco duro de nuestra PC, por que, en dispositivos de almacenamiento como USB's realmente se escribe hasta que nosotros digamos, pero no te confíes tanto.  

Este post realmente es un experimento con las dos herramientas antes mencionadas: 
* PhotoRec
* Scalpel  

Ambas nos pueden ayudar en estos casos pero son un poco diferentes. **No intenten esto en casa, o sí.**    
Para sistemas Windows lo único que he usado es Recuva, el cual funciona bien. No ahondaremos en él, por que el objetivo es recuperar archivos en sistemas Linux.  

### Formateando una USB
Lo primero que hice fue formatear una USB que ya no utilizo, lo importante es sobreescribir los contenidos para ver el funcionamiento de las herramientas que vamos a usar.

![formateando una usb](./images/photorec-scalpel/steps/1format.png)
*Hay que especificar que deseamos que sobreescriba el almacenamiento con 0s y 1s*  


















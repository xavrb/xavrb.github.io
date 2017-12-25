---
layout: post
title: Desactivando el touchpad en Fedora con LXDE  
tags: [fedora, lxde]
---

Por alguna razón que sigo investigando, el touchpad de mi laptop no reconoce `Fn + tecla que desactiva el touchpad`, así que la manera más fácil de conseguirlo es la siguiente.

Requisitos:  
* Tener instalado xinput  

Son dos comandos simples:
1. `xinput list`: Nos mostrará una lista de todos los dispositivos de entrada, buscaremos `touchpad`, o podemos usar grep: `xinput list | grep TouchPad`  
2. Una vez identificado el `id = X` hacemos lo siguiente: `xinput --disable X`  

EZ PZ.  


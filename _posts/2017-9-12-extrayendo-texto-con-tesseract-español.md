---
layout: post
title: Extrayendo texto de un PDF en español con Tesseract y Fedora
---


Ayer estaba tratando de hacer precisamente lo que dice el título del post. Y sí, estaba udando Fedora.  

Toma 1: El PDF que recibí no se podía convertir a un documento de Word aunque era un documento de layout muy sencilla, sin embargo después me di cuenta que era básicamente un escaneo bastante bien hecho, es decir, si lo veías parecía texto crudo de word, aquí lo que intenté:

* Usar [cloudconvert](cloudconvert.com), es un servicio en línea que puede convertir entre 215 formatos de archivos. ¿El problema? Aunque cloudconvert es excelente, su procesamiento se limita a literalmente extraer el texto si ya hay un proceso de OCR sobre el archivo, en este caso no había ninguno.
* Usar LibreOffice y abiword. En teoría los *alter-ego* de MS Word puede convertir PDF en texto, sin embargo resultó en lo mismo por que no había OCR que extraer, lo que me temía.  
Según un artículo que encontré, se puede hacer la conversión entre PDF y word con un comando de abiword:  
```bash
abiword --to=doc whatever.pdf
```  
Lamentablemente no funcionó. Sad.



## La solución: Gscan2pdf con Tesseract e imagemagick

*¿Tesse-qué?* Tesseract es una maravilla hecha motor de reconocimiento de caracteres (OCR), el cual, combinado con gscan2pdf (una herramienta para escanear en Linux) crean un potente extractor de texto. Yay!

¿El problema? Por defecto los paquetes que tenía en mi distribución se limitaban al motor de tesseract pero en inglés (el texto que me mandaron estaba en español)  

¿La solución? Un simple comando en shell para instalar los paquetes del español:  
```bash
# dnf -y install tesseract-langpack-spa
```
Después hay que convertir el PDF en imágenes, ¿cómo hacemos esto?, EZPZ:  
```bash
convert -density 400 esepdfextraño.pdf imagen.png
```
Lo anterior, en mi caso, generó 2 imágenes, las cuales vamos a abrir en gscan2pdf, el cual tiene una GUI bastante intuitiva.

```
Archivo > Abrir > selecciona todas las imágenes que generó convert

Herramientas > OCR > Seleccionar (x)Todos > Elegir Spanish
```
Ahora, dependiendo de la calidad de el pdf querrás jugar con la opción de umbral (threshold before OCR), en mi caso no fue necesaria.
```
Iniciar OCR
```
Y deja que la magia ocurra.  Después de que tesseract termine, en la pestaña `Resultado del OCR` se encontrará el texto que logró extraer, lo exportaremos con:  

```
Archivo > Guardar > (Rango de página) (x)Todos > (Tipo de imagen) (x) texto
``` 
Y listo. Tal vez tengas que quitar uno que otro salto de línea extra, y en general leer el archivo, recordemos que incluso el aprendizaje de máquina a veces requiere supervisión.

Peace out.















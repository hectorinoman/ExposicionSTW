
# Tutorial Edicion de video
## Programa de edicion de video: Cinelerra 
### Instalacion
La instalacion se debe hacer en una maquina con sistema operativo ubuntu de 64 bits.

```sh
$ git clone https://github.com/hectorinoman/ExposicionSTW
$ cd ExposicionesSTW
$ ./cinelerra
```
Los recursos para trabajar la practica tutorizada se encuentran dentro de la carpeta recursos.

### Tutorial de edicion

#### Censurar Video:
* Cargar video
* Añadir pista extra e insertar el video de nuevo.
* Seleccionar la zona del video que queremos ocultar (in point, out point)
* Arrastramos el efecto de video DOWNSAMPLE 
* En la pantalla de Compositor pinchamos en ?, para abrir la ventana de máscara
* Seleccionamos el polígono para ocultar la zona deseada.
* Con esto conseguimos centrar un punto, pero si se moviera, debemos mover la mascara con la llave insertada

 [https://github.com/petterreinholdtsen/cinelerra-cv/blob/master/plugins/downsample/downsample.C]


#### Camara rapida y lenta (ReframeRT)

* Observaremos en propiedades los fp y la resolucion del video
* Archivo nuevo con las dimensiones del video 640x480 25fp
* Reframert añadimos el plugin.
* Ajustaremos el factor de escala, de tal forma que un 1 implica velocidad normal, mayor de 1 mayor velocidad y menor que 1 menor velocidad.
* Al el video ser una imagen estatica, no podemos alargar el video, pero siempre podremos alargar el efecto

[https://github.com/petterreinholdtsen/cinelerra-cv/blob/master/plugins/reframert/reframert.C]


#### Cromaa (chroma key HSV)
* Debemos añadir el video de fondo verde y en otra pista la imagen que queremos que quede detras
* Añadir el plugin chroma key
* Seleccionar el tono de verde para que el programa lo reconozca
* Ajustar los diferentes ajustes para poder dejar un buen efecto.

[https://github.com/petterreinholdtsen/cinelerra-cv/blob/master/plugins/chromakeyhsv/chromakey.C] 


## Programa de visualizacion de video: VLC 

#### VLC (Servidor)

* Abrir VLC
* Seleccionar Medio, Emitir
* Seleccionar el tipo de archivo que se desea transmitir
* Cambiamos el protocolo de destino a HTTP y le ponemos una ruta por ejemplo chuchu.
* El tipo de codificación la podemos dejar como está.
* Procedemos al Stream.

#### VLC (Cliente)

* Abrir VLC
* Seleccionar Medio, Abrir Ubicacion en red
* Escribimos http://ip_local:8080/chuchu
* Disfrutar de la emisión en directo.








Instrucciones de ejecuci�n del programa:

- Descargar el presente Laboratorio en cada computador donde quiera correrlo.
- Editar el archivo "config.ini" en la carpeta del proyecto, y establezca la configuraci�n que desee. Es obligatorio establecer las direcciones IP de cada servicio en cada computador de manera coherente, para ello debe conocer la direcci�n IP local de cada computador donde alojar� algun servicio.
- Ejecutar el servidor de MongoDB
- Ingresar a la aplicaci�n NetBeans.
- Ir al men� "File" y presionar sobre la opci�n "Open Proyect...".
- Dirigirse a la carpeta donde se encuentra el presente laboratorio, seleccionarlo y presionar el bot�n "Open Proyect".
- Realizar "Build" del proyecto, presionando el bot�n F11 o presionando click derecho sobre la raiz de navegaci�n del proyecto y seleccionando la opci�n "Build".
- Ejecutar el proyecto manualmente desplegando en el arbol de navegaci�n del proyecto, los archivos .java. Primero, presionar el click derecho del mouse y seleccionar la opci�n "Run" sobre "IndexService.java", luego repetir la misma operaci�n sobre "CacheService.java", "FrontService.java" y "Cliente.java", en el dicho orden.

* El programa solo funciona ejecutando los archivos en el orden antes estipulado (Index, Cache, Front, Cliente), debido a la dependencia de conexiones de los socket entre los programas.

Instrucciones para la configuraci�n del programa:

- Para cambiar los par�metros del programa se debe editar el archivo "config.ini". La sintaxis correcta es:

 "<tama�o del Cache> <tama�o Cache est�tico> <cantidad de hebras del programa> <cantidad de particiones del cache> <IP del servidor IndexService> <IP del servidor CacheService> <IP del servidor FrontService>\n".

Por ejemplo la configuracion que viene por defecto es "15 50 5 5 192.168.1.34 192.168.1.35 192.168.1.36\n", donde se establecen 15 slots totales en el cache (3 est�ticos (20%) y 12 din�micos (80%); luego se establecen 5 hebras para el programa, que se asignan de manera circular a las consultas del usuario, tanto en el frontService como en el cacheService; y finalmente se establecen 5 particiones del cache, en este caso con tama�os de 2, 2, 2, 2 y 4 slots por particion respectivamente (distribuidos por el autom�ticamente por el programa). Adem�s se establece 192.168.1.34 como IP local donde se alojar� el servidor de IndexService; 192.168.1.35 como IP local donde se alojar� el servidor de CacheService, y 192.168.1.36 como IP local donde se alojar� el servidor de FrontService.

*IMPORTANTE: el archivo de configuracion DEBE terminar con un salto de linea, sino el programa no lo reconocer� y se generar� un error.
*IMPORTANTE: Las direcciones IP del de los distintos servicios deben ser establecidas cada vez que se quiere ejecutar el programa en una red local distinta (o en un momento distinto), dado que es el router el que establece las IP locales para los computadores, seg�n el orden, la cantidad de dispositivos conectados y los puertos disponibles. Adem�s se debe cumplir ejecutar el servicio en el computador con la IP establecida o el programa no funcionar� correctamente.

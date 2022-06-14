# Conceptos básicos de capa fisica

## Tipos de redes

Las infraestructuras de red pueden variar en gran medida en términos de:
* El tamaño del área que abarcan.
* La cantidad de usuarios conectados.
* La cantidad y los tipos de servicios disponibles.
* El área de responsabilidad

A continuación se muestra una clasificación simple

* **Red de area personal**: Es una red que conecta diferentes dispositivos dentro de un area pequeña. Este tipo de red conecta tipicamente wearables. 
* **Red de área local (LAN)**: Es una infraestructura de la red que abarca un área geográfica pequeña. Las redes residenciales, SOHO y corporativas son casos tipicos de este tipo. 
* **Red de área amplia (WAN)**: Es una infraestructura de la red que abarca un área geográfica extensa. Permiten la conexión de varias redes LAN entre sí.

![lan_wan](imagenes_teoria/lan_wan.png)

La siguiente tabla muestra las tecnologias usadas en la implementación de los diferentes tipos de redes:

|Tipo|Tecnologias|
|---|---|
|PAN|Bluetooth radio, Bluetooth Low Energy, ZigBee, Z-Wave, Thread, 6LoWPAN, Wired|
|LAN| Wi-Fi, Ethernet|
|MAN| SigFox, LoRaWAN, NB-IOT (Narrow Band IOT) |

## Bandas ISM

Las bandas ISM (Industrial, Scientific and Medical) son bandas de radio frecuencia reservadas internacionalmente para el uso con propósitos industriales, científicos y médicos.

![ism-band](imagenes_teoria/ism-band.jpg)

La siguiente tabla resume las diferentes tecnologias de comunicación inalambrica resaltando las frecuencias de operación para cada caso:

|Caracteristica|Bluetooth Classic | Bluetooth Low Energy | Bluetooth Mesh | Zigbee | Wi-Fi | LTE-M |NB-IoT|Sigfox|LoRaWAN|
|---|---|---|---|---|---|---|---|---|---|
|Rango| Hasta 100 m| Hasta 200 m o 400 m con LR|Hasta 200 m|Hasta 200 m|Hasta 200 m|Hasta 10 km|Hasta 10 km|Hasta 50 km|Hasta 20 km|
|Frecuencia|2.4 GHz|2.4 GHz|2.4 GHz|2.4 GHz|2.4 GHz, 5 GHz|---|---|915 MHz (America)|902 MHz |
|Throughput|Hasta 3 Mbps|Hasta 2 Mbps|Hasta 1 Mbps|Hasta 250 Kbps|Hasta 100 Mbps|Hasta 1 Mbps|Hasta 200 Kbps|Hasta 100 bps|10 Kbps - 50 Kbps|
|Ongoing cost|Una vez|Una vez|Una vez|Una vez|Una vez|Recurrente|Recurrente|Recurrente|Una vez|
|Consumo de potencia|Bajo|Bajo|Bajo|Bajo|Medio|Medio|Bajo|Bajo|Bajo|
|Costo del módulo|Menores de $5|Menores de $5|Menores de $5|$8 - $15|Menores de $10|$8 - $20|Menores de $5|$8 - $15|
|Topologia|P2P, Star|P2P, Star, Broadcast|Mesh|Mesh|Star, Mesh|Star|Star|Star|Star|

Para mas información puede encontrar una comparación mas detallada en el siguiente [enlace de wikipedia](https://en.wikipedia.org/wiki/Comparison_of_wireless_data_standards).

Para ver como conectar una cosa (thing) a una red Wi-Fi, ver el siguiente [link](./wifi/)

## Enlaces

1. https://wokwi.com/
2. https://markmegarry.github.io/AVR8js-Falstad/
3. https://wokwi.com/
4. https://tawjaw.github.io/Arduino-Robot-Virtual-Lab/
5. https://tawjaw.github.io/Arduino-Robot-Virtual-Lab/index.html
6. https://forum.arduino.cc/t/virtual-online-arduino-and-esp32-simulator-wokwi-arduino-simulator-features/698481/5
7. http://iotfactory.eu/iot-knowledge-center/overview-of-iot-networks/
8. https://www.c-sharpcorner.com/UploadFile/f88748/internet-of-things-iot-an-introduction/
9. https://www.c-sharpcorner.com/UploadFile/f88748/internet-of-things-part-2/
10. https://www.c-sharpcorner.com/UploadFile/f88748/internet-of-things-iot-part-3/
11. https://www.c-sharpcorner.com/UploadFile/f88748/internet-of-thingsiot-part-4-network-protocols-and-arc/
12. https://www.ccontrols.net/cz-sk/applications/internet-of-things-iot/wireless-networks/
13. https://www.sam-solutions.com/blog/internet-of-things-iot-protocols-and-connectivity-options-an-overview/
14. https://www.lanner-america.com/es/iot/
15. https://en.wikipedia.org/wiki/Comparison_of_wireless_data_standards
16. https://www.digikey.com/en/articles/comparing-low-power-wireless-technologies
17. https://www.digikey.com/en/articles/comparing-low-power-wireless-technologies-part-2
18. https://bismark.net.co/como-avanzan-redes-lpwan/
19. http://www.ane.gov.co/Documentos%20compartidos/ArchivosDescargables/consultapublica/contenidos/ComentariosAnexoNormatividadUsoLibre/Respuesta_Comentarios_Anexo_Normatividad_Uso_Libre.pdf
20. https://www.aprendiendoarduino.com/tag/sigfox/
21. https://repositorio.uchile.cl/bitstream/handle/2250/171099/Evaluacion-del-protocolo-HTTP2-para-Internet-de-las-cosas.pdf?sequence=1&isAllowed=y
22. https://editores-srl.com.ar/sites/default/files/aa2_semle_protocolos_ilot.pdf
23. https://forum.huawei.com/enterprise/es/protocolo-http-en-iot-miuconhuawei/thread/624779-100275
24. https://cloud.google.com/blog/products/iot-devices/http-vs-mqtt-a-tale-of-two-iot-protocols
25. https://microsoft.github.io/IoT-For-Beginners/#/2-farm/lessons/2-detect-soil-moisture/README
26. https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-devguide-protocols
27. https://docs.oracle.com/en/cloud/paas/iot-cloud/iotrq/toc.htm
28. https://www.nabto.com/rest-api-iot-guide/
29. https://docs.microsoft.com/en-us/rest/api/iothub/
30. https://github.com/homieiot/homie-esp8266
31. https://openforce.com/de/blog/openhab-mqtt-homie/
32. https://www.instructables.com/Building-Homie-Devices-for-IoT-or-Home-Automation/
33. https://diyprojects.io/getting-start-homie-library-mqtt-connected-objects-esp8266/#.YbDMOL3MLIU
34. http://revistas.unisimon.edu.co/index.php/innovacioning/article/view/3771/4701
35. https://aprendiendoarduino.wordpress.com/2017/10/11/saber-mas-iniciacion-arduino-2017/
36. http://www.microhomie.com/en/master/
37. https://arest.io/
38. http://dweet.io/
39. https://create.arduino.cc/projecthub/frankzhao/iot4car-1b07f1
40. https://bossinsights.com/integrations/iot/adafruit/
41. https://learn.sparkfun.com/tutorials/esp8266-thing-hookup-guide?_ga=2.146596982.374019962.1638969666-812475524.1634861735
42. http://lucstechblog.blogspot.com/2019/07/esp-webserver-tutorial-part-1-textfields.html
43. https://www.esp8266.com/
44. https://learn.sparkfun.com/tutorials/internet-of-things-experiment-guide
45. https://learn.sparkfun.com/tutorials/photon-remote-water-level-sensor#setting-up-text-alerts
46. https://docs.arduino.cc/cloud/iot-cloud/tutorials/esp-32-cloud
47. https://docs.arduino.cc/built-in-examples/control-structures/WhileStatementConditional
48. https://docs.arduino.cc/tutorials/generic/basic-servo-control
49. https://docs.arduino.cc/tutorials/generic/introduction-to-the-serial-peripheral-interface
50. https://programarfacil.com/podcast/proyectos-iot-con-arduino/
51. https://www.instructables.com/Send-SMS-from-Arduino-over-the-Internet-using-ENC2/
52. https://www.networkworld.com/article/3133738/dweetio-a-simple-effective-messaging-service-for-the-internet-of-things.html
53. https://github.com/gamo256/dweet-esp
54. https://www.hackster.io/javier-munoz-saez/esp8266-sending-data-to-an-online-deskboard-3e7e91
55. https://www.fatalerrors.org/a/building-a-simple-internet-of-things-project-with-esp8266.html
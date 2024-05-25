# Laboratorio 1 - Fundamentos y simulaciones Kobuki y Lego EV3 

Integrantes: Daniel Felipe Cantor Santana, Giovanni Obregon, Thomas Hernandez Ochoa, Andres Felipe Zuleta Romero.

# 1. ¿Qué es un robot móvil? Definir qué es un robot y cuáles son sus principales características.

Un robot capaz de moverse bajo su propio control, y sus principales características son:
- Es capaz de reconocer su entorno por medio de sensores
- Ser capaz de desplazarse independientemente sin necesidad de algún tipo de cable de energía
- Adaptado al medio en el que se mueve (terrestre, aéreo o acuático)
- Posee cierto grado de autonomía, es capaz de operar sin un control humano constante.


# 2. Presentación de los Robots: Descripción detallada de los robots Kuboki y EV3, incluyendo sus características físicas y capacidades.
## Kobuki
El robot posee un chasis cilíndrico soportados en cuatro llantas, dos llantas que dan tracción para generar el movimiento del mismo, ambas poseen alturas variables, adicional podemos encontrar otras 2 llantas, las cuales no generan tracción, más bien son 2 apoyos extras. 

Posee sensores de:
- Giroscopio: 3-Ejes Digital, Fabricante STMicroelectronics.
- Bumper (frontal, derecha, izquierda): Este sensor se activa cuando el robot entra en contacto con un obstaculo y manda una señal.
- Cliff Sensor (izquierda, centro, derecha): Este es un sensor de proximidad que detecta la distancia del robot al suelo en diferentes zonas.
- Wheel Drop Sensor: Este sensor detecta si las ruedas se encuentran desplegadas o contraidas.

Posee las siguientes conexiones:
- Switch de encendido y apagado.
- Conector (jack) para carga.
- Power connectors (19V-2A,12V-5A, 12v-1.5A y 5v-1A)
- Puerto de extensión serial (entrada y salida digital/ entrada análoga).
- Puerto USB.
- Botones programables(B0,B1 y B2)
- Leds programables (LED, LED 2)
- Led de estado de carga(Status)
- Switch de descarga de firmware.
## Lego EV3
El robot EV3, desarrollado por LEGO como parte de su serie Mindstorms, es una plataforma educativa y de investigación que combina componentes de hardware y software para enseñar robótica y programación. A continuación, se presenta una descripción detallada de sus características físicas y capacidades.

Componentes Principales:

- Bloque Inteligente EV3: Es el cerebro del robot. Este bloque cuenta con un microprocesador ARM9, una pantalla monocromática, botones de navegación y control, un altavoz, y una ranura para tarjetas microSD que permite ampliar su memoria. Tiene puertos para conectar motores y sensores.
- Motores: Viene con tres motores, dos grandes y uno mediano. Los motores grandes proporcionan más torque, adecuados para movimientos principales como la locomoción del robot, mientras que el motor mediano es ideal para tareas que requieren mayor velocidad y precisión.

Sensores:
- Sensor de Ultrasonidos: Utiliza ondas sonoras para medir la distancia a objetos, permitiendo al robot detectar obstáculos y medir distancias.
- Sensor de Luz: Puede detectar colores y la intensidad de la luz, útil para seguir líneas en el suelo.
- Sensor de Toque: Detecta cuándo se presiona o se libera, útil para detectar colisiones o acciones de presión.
- Sensor Giroscópico: Mide la velocidad de rotación y cambios en la orientación del robot, ayudando en la estabilización y el control preciso del movimiento.
- Sensor de Color: Reconoce hasta siete colores distintos y también puede medir la intensidad de la luz reflejada.

Conectividad y Expansión:

- Puertos de Entrada y Salida: Cuatro puertos de entrada para sensores y cuatro puertos de salida para motores.
- Conectividad Inalámbrica: Compatible con Bluetooth y Wi-Fi (mediante un adaptador USB), permitiendo la comunicación y control remoto del robot.
- Conexión USB: Permite la transferencia de datos y programación desde una computadora.

# 3. Estado actual del robot y sistema de control.
## Kobuki
Características físicas: 
- Cuenta con 5 bandejas para posicionar distintos dispositivos 
- Las 4 ruedas se encuentran en buen estado
- Tiene un conector de puertos USB en la bandeja superior
- Los 4 conectores aparentemente están en buen estado
- No posee computadora principal
- Trae su cable de carga
- Trae su cable para USB

Sistemas de control
- No posee computadora principal.Debe implementarse una tarjeta de desarrollo (Jetson) o un PC 
- Puede controlarse con ROS o de manera serial
- Existe una API en C++ 

## Lego EV3
Características Físicas
- Las 2 ruedas se encuentran en buen estado
- Tiene un conector de puertos USB en la parte lateral
- Tiene un conector MicroSD en la parte lateral
- Posee computadora principal
- No trae su cable de carga

Sistemas de control
- Puede controlarse con ROS a travez de comunicacion MQTT
- Existe unprograma nativo MINDSTORMS EV3

# 4. APIs y lenguajes de programación: Identificar las APIs o librerías disponibles para programar los robots. Enumerar los lenguajes de programación compatibles con los robots.
## Kobuki
Los lenguajes compatibles con el robot kuboki son:
- C++
- Python
- Java u otros (Usando el protocolo de comunicación serial)

Las APIs y paquetes compatibles con el robot kuboki son:
- ROS: kobuki, TurtleBot2
- C++ API (Doxygen)
## Lego EV3
Las APIs y paquetes compatibles con el robot kuboki son:
-ROS:MQTT
-MINDSTORMS EV3
Los lenguajes compatibles con el robot kuboki son:
- Matlab
- Python
- EV3-G

# 5. Herramientas de desarrollo propias
## Kobuki
Existen 3 formas para generar una comunicación con el robot, mediante una aplicación de C + + para linux, usando la plataforma TurtleBot2 o mediante ROS, siendo esta última la manera mas sencillas de uso, ya que cuenta con repositorio propio incluyendo paquetes de simulación: https://wiki.ros.org/kobuki 
## Lego EV3
El LEGO MINDSTORMS EV3 ofrece varias herramientas de desarrollo propias que facilitan la programación y el control del robot, adaptándose a diferentes niveles de experiencia. Las principales herramientas incluyen EV3 Software (EV3-G), un entorno de programación gráfico basado en LabVIEW ideal para principiantes, y EV3 Classroom, una plataforma educativa basada en Scratch que es excelente para uso en aulas de educación primaria y secundaria

[![LEGO MINDSTORMS EV3 Videos](https://img.youtube.com/vi/o5jPKdwpMcg/0.jpg)](https://www.youtube.com/watch?v=o5jPKdwpMcg&list=PLUDkntwKJbAqtGePuVtnEDt91QTcGdjf3&index=1)

[Ver Lista de Reproducción en YouTube](https://www.youtube.com/watch?v=o5jPKdwpMcg&list=PLUDkntwKJbAqtGePuVtnEDt91QTcGdjf3&index=1)

# 6. Sensores del robot Identificar los sensores incorporados en los robots y explicar su funcionamiento.
#Kobuki
El robot posee los siguientes sensores:
Giroscopio: 3-Ejes Digital, Fabricante STMicroelectronics.
Bumper (frontal, derecha, izquierda): Este sensor se activa cuando el robot entra en contacto con un obstaculo y manda una señal.
Cliff Sensor (izquierda, centro, derecha): Este es un sensor de proximidad que detecta la distancia del robot al suelo en diferentes zonas.
Wheel Drop Sensor: Este sensor detecta si las ruedas se encuentran desplegadas o contraidas.

Tiene  compatibilidad con sensores:
- Ultrasónicos
- Cámaras RGBD
- LiDAR
#Lego Eve3
## Sensor de Ultrasonidos
Funcionamiento: Emite ondas sonoras de alta frecuencia que rebotan en los objetos y regresan al sensor. Mide el tiempo de retorno para calcular la distancia al objeto.
Rango: 3 cm a 250 cm.
Aplicaciones: Detección de obstáculos, medición de distancias y proximidad.
Modos: Distancia continua y detección de presencia.

## Sensor Infrarrojo
Funcionamiento: Emite una señal infrarroja y mide la intensidad de la señal reflejada para determinar la distancia a los objetos.
Rango: 0 a 70 cm.
Aplicaciones: Seguimiento de una baliza infrarroja, control remoto del robot y detección de proximidad.
Modos: Proximidad, señal de baliza y receptor de comandos

Tiene  compatibilidad con sensores:
- Sensor Infrarrojo
- Sensor de Color
- Sensor de Toque
- Sensor Giroscópico

# 7. Práctica de identificación y uso de los sensores integrados en los robots, explicando cómo interactúan con el entorno.
## Kobuki
Sensor anti choque: Estos sensores son esenciales para ayudar al robot a evitar obstáculos, evitar daños a sí mismo o a su entorno, y realizar movimientos más seguros. La interacción de un sensor anti choque con el entorno puede variar según el diseño específico del robot y el tipo de sensor utilizado, pero en términos generales cuando el robot se mueve, el sensor constantemente monitorea su entorno en busca de obstáculos. Si detecta un objeto cercano, interpreta esto como una posible colisión.

Sensor de profundidad o detección de bordes: Estos sensores están diseñados para identificar cambios en la superficie, como el borde de una mesa o una plataforma elevada, y alertar al robot para que tome medidas para evitar caerse.
En este caso no se tiene claridad de qué tipo de sensor es, ya que existen táctiles, infrarrojos y de ultra sonido, los sensores infrarrojos por ejemplo emiten luz infrarroja y miden la cantidad de luz reflejada. Cuando el sensor detecta un cambio abrupto en la cantidad de luz reflejada, interpreta que está cerca de un borde y activa medidas de precaución.

### Ultrasonido EV3
Para la toma de medidas del sensor de ultrasonido del EV3, se siguieron las instrucciones dadas en la guia del laboratorio con 2 particularidades, debido al guardaescobas de la habitación el sensor de ultrasonido del EV3 tomó como distancia inicial 4mm, sin embargo con el fin de reducir la incertidumbre, adicional a la cinta métrica se marcó con cinta los 100cm, como puede verse en las siguientes fotos:

<img src="https://github.com/FRM-2024-1S-Grupo-2/Laboratorio-Sensores/blob/main/Imagenes/Ultrasonido_EV3.jpg" alt="Ultrasonido_EV3" width="400"> <img src="https://github.com/FRM-2024-1S-Grupo-2/Laboratorio-Sensores/blob/main/Imagenes/Cinta_Ev3.jpg" alt="Cinta_Ev3" width="400">

![image](https://github.com/FRM-2024-1S-Grupo-2/Laboratorio-Sensores/blob/main/Imagenes/Distancia_4mm.jpg)

Dicho experimento se realizó con el siguiente código:

![image](https://github.com/FRM-2024-1S-Grupo-2/Laboratorio-Sensores/blob/main/Imagenes/Codigo_ultrasonido.png)

Se puede ver los demas sensores usados en [Laboratorio de sensores](https://github.com/FRM-2024-1S-Grupo-2/Laboratorio-Sensores/tree/main)
# 8. Modelado del robot real: Realizar el modelado del robot Kuboki y EV3, en coopeliasim.

El modelado puede apreciarse en la siguiente figura y su respectivo archivo se encuentra adjunto en este repositorio. 
![Imagen 1](https://github.com/FRM-2024-1S-Grupo-2/Taller-1/blob/main/imagenes/CoppeliaSim.png)


# 9. Programa simple de movimientos: Utilizando las herramientas propias del robot, crear un programa sencillo que indique movimientos básicos del robot, como desplazarse hacia adelante, girar a la derecha, etc.
La primera prueba realizada, fue implementando un programa pre definido que se encuentra instalado en el robot, acá puede verse su funcionamiento:

[![Alt text](https://img.youtube.com/vi/ZMaNHp1PxMU/0.jpg)](https://www.youtube.com/watch?v=ZMaNHp1PxMU)


Además,se encontró un código que describe una trayectoria cuadrada del kuboki, sin embargo, realizamos una ligera modificación para que se describiera una trayectoria lineal (El archivo completo se encuentra en este mismo repositorio). Como se ve a continuación:
![Imagen 2](https://github.com/FRM-2024-1S-Grupo-2/Taller-1/blob/main/imagenes/Función%20de%20trayectoria.png)

Se modificó el límite "eclp" del *if*  para generar un giro de 180 grados del robot (pi) y que el robot describa una trayectoria lineal.

# 10. Reflexión y Discusión: Sesión de reflexión donde los estudiantes comparten sus experiencias, aprendizajes y posibles mejoras en el uso del robot Kuboki en aplicaciones prácticas.

El robot Kuboki posee diversos usos, desde el educativo, hasta aplicaciones médicas y de asistencia. Posee una interfaz física intuitiva, con varias formas de conexión y programación.

Para el equipo de trabajo, resultó ser desafiante el hecho de crear una rutina para el robot sin usar ROS, dado que este programa se tuvo que realizar en lenguaje C++, tratandose de un lenguaje de alto nivel.

Tener un modelado mas complejo de la geometría del robot hace que coppelia sim se perciba un poco mas lento, hay ciertas pruebas que es mejor realizarlas con la geometría simplificada.

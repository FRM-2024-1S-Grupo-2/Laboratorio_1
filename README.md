# Taller-1

Integrantes: Daniel Felipe Cantor Santana, Giovanni Obregon, Thomas Hernandez Ochoa, Andres Felipe Zuleta Romero

# 1. ¿Qué es un robot móvil? Definir qué es un robot y cuáles son sus principales características.

Un robot capaz de moverse bajo su propio control, y sus principales características son:
- Es capaz de reconocer su entorno por medio de sensores
- Ser capaz de desplazarse independientemente sin necesidad de algún tipo de cable de energía
- Adaptado al medio en el que se mueve (terrestre, aéreo o acuático)
- Posee cierto grado de autonomía, es capaz de operar sin un control humano constante.


# 2. Presentación de los Robots: Descripción detallada de los robots Kuboki y EV3, incluyendo sus características físicas y capacidades.

El robot posee un chasis cilíndrico soportados en cuatro llantas, dos llantas que dan tracción para generar el movimiento del mismo, ambas poseen alturas variables, adicional podemos encontrar otras 2 llantas, las cuales no generan tracción, más bien son 2 apoyos extras. 

Posee sensores de:
- Sensor anti choque.
- Sensores de profundidad.
- Sensor de desnivel, con el objetivo de evitar caídas.

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


# 3. Estado actual del robot y sistema de control.
Características físicas: 
- Cuenta con 5 bandejas para posicionar distintos dispositivos 
- Las 4 ruedas se encuentran en buen estado
- Tiene un conector de puertos USB en la bandeja superior
- Los 4 conectores aparentemente están en buen estado
- No posee computadora principal
- Trae su cable de carga
- Trae su cable para USB

Sistema de control
- No posee computadora principal.Debe implementarse una tarjeta de desarrollo (Jetson) o un PC 
- Debe controlarse con ROS




# 4. APIs y lenguajes de programación: Identificar las APIs o librerías disponibles para programar los robots. Enumerar los lenguajes de programación compatibles con los robots.

Los lenguajes compatibles con el robot kuboki son:
- C++
- Python
- Java u otros (Usando el protocolo de comunicación serial)

Las APIs y paquetes compatibles con el robot kuboki son:
- ROS: kobuki, TurtleBot2
- C++ API (Doxygen)

# 5. Herramientas de desarrollo propias: Demostración de las herramientas de desarrollo propias de los robots, destacando su utilidad y funcionalidades. (Si es posible). Resumir las herramientas propias que disponen los robots para facilitar la programación y el control.

Existen 3 formas para generar una comunicación con el robot, mediante una aplicación de C + + para linux, usando la plataforma TurtleBot2 o mediante ROS, siendo esta última la manera mas sencillas de uso, ya que cuenta con repositorio propio incluyendo paquetes de simulación: https://wiki.ros.org/kobuki 


# 6. Sensores del robot Identificar los sensores incorporados en los robots y explicar su funcionamiento.
El robot posee los siguientes sensores:
Giroscopio: 3-Ejes Digital, Fabricante STMicroelectronics.
Bumper (frontal, derecha, izquierda): Este sensor se activa cuando el robot entra en contacto con un obstaculo y manda una señal.
Cliff Sensor (izquierda, centro, derecha): Este es un sensor de proximidad que detecta la distancia del robot al suelo en diferentes zonas.
Wheel Drop Sensor: Este sensor detecta si las ruedas se encuentran desplegadas o contraidas.

Tiene  compatibilidad con sensores:
- Ultrasónicos
- Cámaras RGBD
- LiDAR
# 7. Práctica de identificación y uso de los sensores integrados en los robots, explicando cómo interactúan con el entorno.

Sensor anti choque: Estos sensores son esenciales para ayudar al robot a evitar obstáculos, evitar daños a sí mismo o a su entorno, y realizar movimientos más seguros. La interacción de un sensor anti choque con el entorno puede variar según el diseño específico del robot y el tipo de sensor utilizado, pero en términos generales cuando el robot se mueve, el sensor constantemente monitorea su entorno en busca de obstáculos. Si detecta un objeto cercano, interpreta esto como una posible colisión.

Sensor de profundidad o detección de bordes: Estos sensores están diseñados para identificar cambios en la superficie, como el borde de una mesa o una plataforma elevada, y alertar al robot para que tome medidas para evitar caerse.
En este caso no se tiene claridad de qué tipo de sensor es, ya que existen táctiles, infrarrojos y de ultra sonido, los sensores infrarrojos por ejemplo emiten luz infrarroja y miden la cantidad de luz reflejada. Cuando el sensor detecta un cambio abrupto en la cantidad de luz reflejada, interpreta que está cerca de un borde y activa medidas de precaución.



# 8. Modelado del robot real: Realizar el modelado del robot Kuboki y EV3, en coopeliasim.

El modelado puede apreciarse en la siguiente figura y su respectivo archivo se encuentra adjunto en este repositorio. 
![Imagen 1](https://github.com/FRM-2024-1S-Grupo-2/Taller-1/blob/main/imagenes/CoppeliaSim.png)


# 9. Programa simple de movimientos: Utilizando las herramientas propias del robot, crear un programa sencillo que indique movimientos básicos del robot, como desplazarse hacia adelante, girar a la derecha, etc.
La primera prueba realizada, fue implementando un programa pre definido que se encuentra instalado en el robot, acá puede verse su funcionamiento:

[![Alt [![Alt text](https://img.youtube.com/vi/ZMaNHp1PxMU/0.jpg)](https://www.youtube.com/watch?v=ZMaNHp1PxMU)


Además,se encontró un código que describe una trayectoria cuadrada del kuboki, sin embargo, realizamos una ligera modificación para que se describiera una trayectoria lineal (El archivo completo se encuentra en este mismo repositorio). Como se ve a continuación:
![Imagen 2](https://github.com/FRM-2024-1S-Grupo-2/Taller-1/blob/main/imagenes/Función%20de%20trayectoria.png)

Se modificó el límite "eclp" del *if*  para generar un giro de 180 grados del robot (pi) y que el robot describa una trayectoria lineal.

# 10. Reflexión y Discusión: Sesión de reflexión donde los estudiantes comparten sus experiencias, aprendizajes y posibles mejoras en el uso del robot Kuboki en aplicaciones prácticas.

El robot Kuboki posee diversos usos, desde el educativo, hasta aplicaciones médicas y de asistencia. Posee una interfaz física intuitiva, con varias formas de conexión y programación.

Para el equipo de trabajo, resultó ser desafiante el hecho de crear una rutina para el robot sin usar ROS, dado que este programa se tuvo que realizar en lenguaje C++, tratandose de un lenguaje de alto nivel.

Tener un modelado mas complejo de la geometría del robot hace que coppelia sim se perciba un poco mas lento, hay ciertas pruebas que es mejor realizarlas con la geometría simplificada.

# Práctica 3
## Integrantes:
- Luis Fernando Duarte Reséndiz.
  
-  Mauricio Alberto Gómez Arroyo.

- Diego Brandon Guzmán Sierra.

- Bryan Hiadim Vera Hernández.

## Introducción
La automatización de tareas con robots industriales es clave para mejorar la eficiencia y productividad en entornos industriales, reduciendo riesgos asociados a la intervención humana. El objetivo de la práctica fue programar y grabar una secuencia de movimientos usando el software Epson RC+ 7.0, para que el robot los ejecute automáticamente. La grabación consistió en movimientos manuales precisos para intercambiar la posición de fusibles, reemplazando uno por otro.

## Instrucciones

### 1. Abrir el software Epson RC+ 7.0 y ajustar la conexion
La conexión sera por medio de USB, que es por donde se subiran las instrucciones de la computadora al robot (en nuestro caso en un robot Epson C4 de seis ejes).

![image](https://github.com/user-attachments/assets/f53d896d-24dd-4f9a-ae4d-27dc472d6d49)

### 2. Configurar "Home"
La coonfiguración de Home, es muy importante dado que sera la posición inicial o referencia del robot.
En el apartado de "Tools" abrimos la sección "Robot Manager" o F6.

![image](https://github.com/user-attachments/assets/585e909d-afd5-44ec-b4f8-08314f148fc2)

Prender motor.

![image](https://github.com/user-attachments/assets/6a2e023b-4fb1-481c-8db6-7b38baa8caf3)

Aceptar.

![image](https://github.com/user-attachments/assets/8e7a5a4d-1b9d-43f9-8170-1eb4cef97543)

Ahora los motores estan encendidos.

![image](https://github.com/user-attachments/assets/89c0fe3d-9592-4796-82b7-368883d4db83)

En la parte izquierda seleccionar "Jog and Teach". En mode seleccionamos "Joint" y en "Current Position tambien seleccionamos "Joint". Y ajustamos a -90 grados J5.

![image](https://github.com/user-attachments/assets/73901d3e-28ae-49ee-a17a-7aa374ddf8ec)

Con la flechitas moverse hasta la parte de inferior y seleccionamos "Home Config". Una vez ahi seleccionamos "Read Current Position" y esas seran las coordenadas de "Home" de nuestro robot.

![image](https://github.com/user-attachments/assets/584e51b8-842f-4afe-8b36-6bc8df34c799) ![image](https://github.com/user-attachments/assets/db26a1fa-4434-4978-866b-32fd8c103428)
> Configuración de Home y Home vista desde el simulador.


### 3. Configurar las memorias de las posiciones a usar
Para realizar la práctica, se requiere seleccionar dos fusibles e intercambiar sus posiciones. Es decir, el fusible 2 pasará a ocupar la posición del fusible 4, y el fusible 4 ocupará la posición del fusible 2. Para efectuar este intercambio, uno de los fusibles se colocará temporalmente en una posición intermedia, permitiendo completar el cambio de posiciones de manera ordenada.

En la sección "Jog and Teach" se enseñarán las posiciones necesarias para el intercambio exitoso de los fusibles. Este proceso implica mover el robot directamente y verificar visualmente que cada posición sea la correcta. Si alguna no es adecuada, se ajusta hasta lograr la precisión requerida para el éxito del procedimiento.

Una vez que se tiene la posición deseada, se selecciona "Teach" y se guarda con un nombre que facilite recordar la función de esa posición. En este caso, solo se usarán 5 posiciones. Las funciones de estas posiciones son:

- agarrar2: Sirve para que la garra llegue a una posición adecuada para agarrar el fusible número 2.
- arriba2: Sirve para moverse solo hacia arriba del fusible número 2.
- bajar2: Sirve para dejar el fusible número 2 en una posición intermedia para el cambio de fusibles.
- agarrar4: Sirve para que la garra llegue a una posición adecuada para agarrar el fusible número 4.
- arriba4: Sirve para moverse solo hacia arriba del fusible número 4.

![image](https://github.com/user-attachments/assets/5588dbe3-0f07-48d0-aa6e-c0da3f271a95)

En la sección "Points" se vizualizan las posiciones guardadas anteriormente.

![image](https://github.com/user-attachments/assets/4fcf5525-dea7-4351-8e31-b864ab991d86)

## 4. Ordenar los movimientos dentro del programa
Una vez que se tienen los movimientos en memoria, se procede a ordenar los movimiento dentro del programa. Esto se hace abriendo "File" seguido de "Open" o ctrl. O.

![image](https://github.com/user-attachments/assets/76b2f4f9-4fd6-41ac-a707-843e1994e08d)

Ahí abres el programa con el nombre guardado.

![image](https://github.com/user-attachments/assets/3986b667-85de-49bf-98ac-ee56e9ac1dc2)

Para realizar la tarea con éxito, se sigue la siguiente secuencia:

- Colocar el robot en la posición inicial (Home).
- Abrir la garra del robot (el comando "On" abre la garra, ubicada en la salida 2).
- Mover el robot a la posición arriba2.
- Mover el robot a la posición agarrar2.
- Cerrar la garra para sujetar el fusible 2.
- Regresar a la posición inicial (Home) con el fusible 2.
- Bajar la garra a una posición intermedia.
- Abrir la garra para soltar temporalmente el fusible 2 y proceder con el intercambio.
- Regresar a la posición inicial (Home).
- Mover el robot a la posición arriba4.
- Mover el robot a la posición agarrar4.
- Cerrar la garra para sujetar el fusible 4.
- Elevar ligeramente la garra por encima de la posición del fusible 4.
- Mover el robot a una posición ligeramente por encima del fusible 2.
- Mover el robot a la posición del fusible 2.
- Abrir la garra para soltar el fusible 4 en la posición del fusible 2.
- Elevar ligeramente la garra.
- Regresar a la posición inicial (Home).
- Bajar la garra hasta la posición donde se dejó el fusible 2.
- Cerrar la garra para sujetar el fusible 2.
- Mover el robot a la posición ligeramente por encima del fusible 4.
- Bajar la garra hasta dejar el fusible 2 en la posición del fusible 4.
- Abrir la garra para soltar el fusible 2.
- Elevar ligeramente la garra.
- Regresar a la posición final (Home).

Nota: las posiones arriba2, arriba4, agarrar2, agarrar4 fueron descritas anteriormente.

![image](https://github.com/user-attachments/assets/d80af8e1-5e1a-409b-ad82-84c43e55e82e)
> Secuencia del robot para realizar la tarea.

## Ejecución
A continuación se visualiza la ejecución en físico.



https://github.com/user-attachments/assets/4db95b0b-f126-46cd-9c07-362a2c458a74



## Conclusiones
- Luis Fernando Duarte Reséndiz.
  
La práctica demostró que la correcta programación de un robot es crucial para asegurar la precisión en tareas específicas, como el intercambio de fusibles. Al definir de manera exacta cada una de las posiciones del robot, se reduce considerablemente el margen de error y se asegura que las operaciones sean repetibles con mucha precisión. Este nivel de control permite que el robot ejecute movimientos complejos sin desviaciones, lo que es fundamental en entornos industriales donde incluso pequeños errores pueden generar retrasos o problemas de calidad en la producción.
  
-  Mauricio Alberto Gómez Arroyo.

El uso del robot en esta práctica resaltó cómo la automatización es una herramienta poderosa para optimizar la eficiencia en tareas repetitivas. A diferencia de la intervención manual, que puede ser propensa a errores y fatiga, el robot fue capaz de completar cada ciclo de intercambio de fusibles de manera consistente y sin variaciones en el tiempo de ejecución. Esto no solo mejora la productividad general, sino que también libera a los operarios humanos de tareas repetitivas, permitiéndoles enfocarse en actividades más estratégicas y de mayor valor agregado dentro del proceso industrial.

- Diego Brandon Guzmán Sierra.

La automatización de procesos industriales, en este caso el intercambio de fusibles, no solo incrementa la productividad, sino que también contribuye a mejorar la seguridad en el entorno laboral. Al eliminar la necesidad de que los operarios intervengan directamente en el manejo de componentes, se minimizan los riesgos de accidentes laborales, como lesiones por contacto con partes móviles o fallos mecánicos. Además de que la programación precisa del robot garantiza que las operaciones se realicen de manera segura y controlada, protegiendo tanto al personal como a los equipos involucrados en el proceso.

- Bryan Hiadim Vera Hernández.

Aunque la automatización, como la implementada en el intercambio de fusibles, mejora la precisión y la eficiencia, también tiene algunas desventajas que deben considerarse. Una de las principales es la falta de flexibilidad. Los robots, una vez programados para realizar tareas específicas, pueden tener dificultades para adaptarse rápidamente a cambios imprevistos o a nuevas configuraciones sin intervención humana o reprogramación. Además, los altos costos iniciales de implementación y mantenimiento de los sistemas automatizados pueden ser una barrera, especialmente para pequeñas empresas que no cuentan con los recursos necesarios para invertir en tecnología avanzada o en personal capacitado para operarla.

## Referencias

De proyectos, A. y. D. (s/f). Manual del usuario. Epson.com. Recuperado de https://files.support.epson.com/far/docs/epson_rc_pl_70_users_guide_spanish_(v73r2).pdf

Robot Epson C4 de 6 ejes compactos. (s. f.). Productos | Epson México. https://epson.com.mx/Para-el-trabajo/Rob%C3%B3tica/6-Ejes/Robot-Epson-C4-de-6-ejes-compactos/p/RC4-A601ST75

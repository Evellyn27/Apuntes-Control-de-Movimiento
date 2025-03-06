# SIMSCAPE MULTIBODY

En el ámbito de la simulación y modelado de sistemas mecánicos, Simscape Multibody se presenta como una poderosa herramienta dentro de MATLAB, este entorno permite la representación y análisis de sistemas mecánicos tridimensionales, como robots, maquinaria pesada y vehículos, utilizando cuerpos rígidos interconectados mediante articulaciones, restricciones y elementos de fuerza. Con Simscape Multibody, es posible formular y resolver ecuaciones de movimiento de manera eficiente, facilitando el diseño, validación y optimización de mecanismos complejos. Además, su capacidad de visualización 3D permite interpretar el comportamiento dinámico de los sistemas simulados en un entorno gráfico interactivo. Este software resulta fundamental para ingenieros y desarrolladores que buscan realizar pruebas virtuales antes de la implementación física, optimizando tiempos y recursos en el desarrollo de sistemas mecánicos avanzados.

## CARACTERISTICAS

Además de su capacidad para modelar y simular sistemas mecánicos 3D, Simscape Multibody ofrece una serie de características adicionales que lo convierten en una herramienta versátil para la ingeniería:

* Integración multidominio: Se puede combinar con otros sistemas físicos, como circuitos hidráulicos, eléctricos y neumáticos, permitiendo el desarrollo de modelos más realistas y complejos.

* Modelado basado en componentes: Utiliza bloques que representan elementos físicos, facilitando la creación, modificación y análisis de los sistemas sin necesidad de programación extensiva.

* Visualización avanzada: Permite la animación 3D de los modelos, lo que ayuda a interpretar mejor el comportamiento dinámico del sistema y validar su funcionamiento.
Automatización y análisis: Ofrece herramientas para la parametrización, optimización y análisis de sensibilidad, permitiendo ajustar los diseños de manera eficiente.

* Compatibilidad con Simulink: Se integra completamente con Simulink, lo que facilita la incorporación de controladores y la simulación de sistemas completos.

Gracias a estas características, Simscape Multibody se posiciona como una herramienta fundamental para ingenieros y diseñadores que buscan desarrollar y probar sistemas mecánicos de manera eficiente y precisa.

## Elementos Clave en Simscape Multibody

Los siguientes bloques son fundamentales para la construcción de modelos en Simscape Multibody dentro de MATLAB:

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/672abf7cffd30f356361f325c8f67f83f169805a/Imagenes/Sistema.png">
</p>
### Solver Configuration
Define los parámetros de resolución numérica del modelo, como la tolerancia y el método de integración.

* Solver en paso fijo

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/c705a0c17d2775a278025cd4e166906a85fdfb2f/Imagenes/Captura%20de%20pantalla%202025-03-06%20001531.png">
</p>
  
  El paso fijo mantiene un intervalo de tiempo constante entre cálculos, lo que es útil para sistemas de tiempo real y control embebido. MATLAB ofrece varias opciones, dependiendo de la precisión deseada:
  
  - **ode1 (Euler)**: Método simple y rápido, pero menos preciso.
  - **ode3, ode5 (Runge-Kutta)**: Métodos más precisos, pero requieren más cálculo.
  - **Auto**: MATLAB selecciona automáticamente el solver adecuado.

> 📌 **Nota:** En *Fixed-step size*, establece el intervalo de tiempo de cada cálculo. Por ejemplo, si se configura en `0.01`, la simulación calculará datos cada `0.01` segundos. Un paso más pequeño mejora la precisión, pero aumenta el tiempo de simulación.

* Solver en paso variable

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/e8037c9f73f57638e6e4eb322ec289ccc8571e90/Imagenes/Captura%20de%20pantalla%202025-03-06%20001947.png">
</p>

  El paso variable ajusta dinámicamente el tamaño del paso de tiempo según la complejidad del sistema en cada instante, lo que permite mayor precisión y eficiencia.

  MATLAB ofrece varios solvers para paso variable. Algunas opciones recomendadas son:
  - **ode45 (Dormand-Prince)**: Solver de uso general, bueno para modelos sin discontinuidades.
  - **ode23t (Trapezoidal)**: Recomendado para modelos con Simscape, ya que maneja bien sistemas rígidos.
  - **ode15s (Stiff/NDF)**: Útil para sistemas con ecuaciones diferenciales rígidas.

### World Frame
Establece el marco de referencia global para todos los objetos en la simulación.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/5f80afc4c24e07f42689474028f0449b7c739a39/Imagenes/Captura%20de%20pantalla%202025-03-06%20002101.png">
</p>

### Mechanism Configuration
Establece las propiedades generales del mecanismo, como la gravedad y la resolución numérica.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/672abf7cffd30f356361f325c8f67f83f169805a/Imagenes/Sistema.png">
</p>

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/f9216829f984d19bf71b95f49846216a98410b2d/Imagenes/Captura%20de%20pantalla%202025-03-06%20002347.png">
</p>

**Parámetros del Bloque**
* Uniform Gravity (Gravedad Uniforme)

  Se define una gravedad constante para todo el sistema mecánico.
  - El valor se establece en forma de vector `[x y z]`, donde cada componente indica la aceleración gravitacional en cada eje.
  - En la imagen, el valor de gravedad es `[0 0 -9.80665]`, lo que significa que la gravedad actúa en la dirección Z negativa (sentido convencional en la Tierra).
    
> 📌 **Nota:** Si la gravedad está definida como `[0 -9.80665 0]`, significa que ahora actúa en la dirección Y negativa.

* Linearization Delta
  
Este parámetro se usa para la linealización del modelo y se mantiene en `0.001`, lo que controla la precisión en los cálculos numéricos.

* Joint Mode Transition (Transición de Modo de Articulación)

  **Nonlinear Iterations**: Se establece en `2`, lo que indica cuántas iteraciones se permiten en los cálculos de transición no lineales en las articulaciones.

### Brick Solid
Representa un cuerpo rígido con forma de bloque en la simulación.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/672abf7cffd30f356361f325c8f67f83f169805a/Imagenes/Sistema.png">
</p>

**Configuración básica**
- **Dimensiones**: Se especifican en el formato `[largo ancho alto]` en metros.
- **Propiedades de inercia**: Pueden definirse automáticamente o personalizarse manualmente.
- **Gráfica y visualización**: Se pueden modificar aspectos visuales del sólido.
- **Puntos de referencia (Frames)**: Se añaden para definir ubicaciones clave para conexiones o movimientos en la simulación.

### Rigid Transform
Establece una transformación rígida entre dos elementos, permitiendo posicionarlos y orientarlos correctamente.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/672abf7cffd30f356361f325c8f67f83f169805a/Imagenes/Sistema.png">
</p>

El bloque *Rigid Transform* en Simscape Multibody permite establecer una relación fija de posición y orientación entre dos marcos de referencia sin deformación. A través de sus parámetros de **rotación** y **traslación**, se pueden definir transformaciones geométricas para conectar correctamente los componentes de un modelo mecánico.

En la configuración mostrada, ambos parámetros están en `None`, lo que indica que no se está aplicando ninguna transformación, dejando los marcos de referencia en la misma posición y orientación relativa.


## CONCLUSIONES

* Simscape Multibody es una herramienta poderosa y versátil dentro del entorno MATLAB, que permite modelar, analizar y optimizar sistemas mecánicos tridimensionales mediante cuerpos rígidos, articulaciones y fuerzas, facilitando el diseño de mecanismos complejos.

* La integración con otros dominios físicos (hidráulicos, eléctricos y neumáticos) permite la creación de modelos más realistas y completos, mejorando la precisión de las simulaciones.

* Su capacidad de visualización 3D y análisis avanzado facilita la interpretación del comportamiento dinámico de los sistemas, permitiendo una validación más intuitiva y detallada antes de la implementación física.

* La configuración automática del solver mediante la opción Auto (Automatic Solver Selection) optimiza la precisión y eficiencia de los cálculos numéricos, eliminando la necesidad de ajustes manuales complejos.

* El uso de bloques de configuración en Simscape Multibody permite establecer de manera estructurada los parámetros clave de la simulación, como el marco de referencia, las ecuaciones del sistema y las propiedades físicas del mecanismo.

* La compatibilidad con Simulink facilita la integración de sistemas de control en los modelos mecánicos, lo que permite realizar simulaciones más completas e interactivas.

* El comando smnew simplifica la creación de nuevos modelos al generar automáticamente un entorno de trabajo preconfigurado para la simulación de sistemas multicuerpo.

En general, Simscape Multibody es una herramienta fundamental para ingenieros y diseñadores que buscan realizar pruebas virtuales, optimizar el rendimiento de los mecanismos y reducir costos en el desarrollo de sistemas mecánicos avanzados.

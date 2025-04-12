
#  Modelado de Mecanismos en Simscape

El modelado de mecanismos en Simscape es una herramienta poderosa dentro del entorno Matlab/Simulink que permite representar sistemas mecánicos de manera detallada, utilizando bloques que simulan componentes reales como cuerpos rígidos, articulaciones y resortes. A diferencia de otros enfoques, Simscape facilita la creación de modelos físicos complejos sin necesidad de escribir ecuaciones, ya que las convierte automáticamente en representaciones listas para simular. Esta herramienta no solo permite integrar el modelado mecánico con otros dominios físicos como el eléctrico o térmico, sino que también favorece la simulación de sistemas multidisciplinarios, lo que hace posible diseñar, analizar y optimizar mecanismos en un entorno virtual antes de su implementación física.

## 1. Fundamentos del Modelado de Mecanismos

El diseño de eslabones en Simscape se realiza utilizando sólidos que representan los componentes de un mecanismo, como los eslabones de una cadena cinemática. Estos sólidos, que pueden ser cuerpos rígidos o estructuras más complejas, son modelados a través de bloques específicos que permiten definir sus propiedades físicas, como la masa, el momento de inercia y las fuerzas de contacto.

>🔑 *Eslabones:* son elementos rígidos que transmiten fuerzas o movimientos dentro de un mecanismo.

En el entorno de Simulink, los eslabones se modelan mediante el bloque Solid, el cual permite definir una amplia gama de propiedades que describen el comportamiento físico del cuerpo en el espacio tridimensional, como se muestra acontinuación: 

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/043e7227e44ce6cc18c1f69bec1b16df57b53888/Imagenes/Captura%20de%20pantalla%202025-04-11%20213930.jpg"  width="500">

Dentro del entorno de Simulink, el bloque de Solid permite especificar parámetros claves como:

- **Geometría:** Define la forma física del sólido. Puede seleccionarse entre geometrías básicas (cubo, cilindro, esfera, etc.) o importarse desde archivos CAD.

- **Inercia:** Determina cómo responde el sólido ante rotaciones. Incluye masa, centro de masa, y tensor de inercia.

- **Gráficos:** Permite personalizar la apariencia visual del sólido durante la simulación. Aunque no influye en el comportamiento dinámico, facilita el análisis visual del sistema.
  
- **Marcos de referencia:** Establecen los sistemas de coordenadas locales asociados al sólido. Son esenciales para posicionar el eslabón dentro del modelo y conectar correctamente.

## 2. Cinemática y Dinámica de Mecanismos

### 2.1 Cinemática de Mecanismos en Simscape

> 🔑 *Cinemática:* Es la rama de la mecánica que estudia el movimiento de los cuerpos sin tener en cuenta las fuerzas que lo producen

En el contexto de Simscape, la cinemática se implementa a través de la descripción del movimiento relativo entre los eslabones de un mecanismo conectado por juntas mecánicas (*joints*), que definen la relación espacial entre ellos y los grados de libertad del sistema.

Simscape ofrece una variedad de bloques de juntas que se pueden utilizar para modelar diferentes tipos de movimientos en mecanismos, entre las juntas más comunes incluyen:

- **Revolute Joint**: permite la rotación relativa entre dos sólidos alrededor de un eje fijo. Es comparable a una bisagra o a una articulación como el codo en un brazo robótico.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/e2754edb612f0685ad4610b16332c6dec5f3499c/Imagenes/Captura%20de%20pantalla%202025-04-11%20213147.jpg"  width="200">
</p>


- **Prismatic Joint**: restringe el movimiento a una sola dimensión lineal. Es similar al comportamiento de un pistón o actuador lineal.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/1222695aa5fdf1b41f498a92b106e4c39930765e/Imagenes/Captura%20de%20pantalla%202025-04-11%20230057.jpg"  width="200">
</p>


- **Spherical Joint:** permite que un cuerpo se mueva libremente en tres grados de libertad (traslación y rotación) dentro de un espacio tridimensional

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/1222695aa5fdf1b41f498a92b106e4c39930765e/Imagenes/Captura%20de%20pantalla%202025-04-11%20230125.jpg"  width="200">
</p>

- **Cylindrical Joint:** permite que un cuerpo se desplace a lo largo de un eje, pero también puede rotar alrededor de ese mismo eje.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/1222695aa5fdf1b41f498a92b106e4c39930765e/Imagenes/Captura%20de%20pantalla%202025-04-11%20230110.jpg"  width="200">
</p>

- **Pin-Slot Joint:** permite que un cuerpo se desplace a lo largo de una ranura (movimiento lineal) y, al mismo tiempo, pueda rotar alrededor de un eje dentro de esa trayectori

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/cff4f7c6455840c971953cc960d77861d5102050/Captura%20de%20pantalla%202025-04-11%20230138.jpg"  width="200">
</p>

### 2.2  Dinámica de los Mecanismos

> 🔑 *Dinámica:* estudia las fuerzas que actúan sobre los eslabones y cómo estas afectan el movimiento del sistema. 

En Simscape, se configuran propiedades dinámicas utilizando el bloque Solid y sus parámetros de masa, momento de inercia, y fuerzas de contacto.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/5535d42e88dd950cc25ddf5b4cedcef0e850fd85/Imagenes/Captura%20de%20pantalla%202025-04-11%20232425.jpg"  width="500">
</p>

### 2.3 Actuadores y Sensado en Simscape
Simscape permite controlar el comportamiento dinámico de un mecanismo mediante el uso de actuadores y obtener información clave del sistema a través de sensores integrados en cada articulación.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/ee9ada9d8955f5cb8642a4675e5c35bf33d01cb2/Imagenes/Captura%20de%20pantalla%202025-04-11%20233600.jpg"  width="500">
</p>

#### Actuation (Actuación)
El apartado Actuation define cómo se aplican las entradas al sistema. En el caso mostrado:

- **Torque:** Se puede configurar como None, Automatically Computed, Provided by Input, etc.

Cuando se selecciona None, no se aplica ningún par directamente. Sin embargo, si se elige Provided by Input, se habilita una entrada física por la cual se puede aplicar un torque externo al sistema, por ejemplo, desde un bloque Stair Generator conectado mediante un PS Converter.

- **Motion:** Determina si el movimiento es calculado por el modelo (como resultado de las fuerzas aplicadas), o si es prescrito manualmente.

En la opción Automatically Computed, el sistema resuelve el movimiento según las condiciones físicas, pero también se puede fijarse a un perfil definido por el usuario (e.g., velocidad o posición deseada).

#### Sensing (Sensado)
Este bloque permite seleccionar qué variables del sistema se desean monitorear. Las opciones incluyen:

- **Position**: Mide la posición angular o lineal relativa entre los dos cuerpos conectados por la junta.
- **Velocity**: Mide la velocidad de cambio de posición.
- **Acceleration**: Permite obtener la segunda derivada, útil para el análisis dinámico.
- **Actuator Torque**: Mide el par aplicado por un actuador.
- **Lower-Limit Torque / Upper-Limit Torque**: Detectan cuándo el sistema está alcanzando los límites de movimiento impuestos por la configuración de la junta.


### 2.4 Aplicación de Entradas 
<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/eac0de6430c7708504ab7a4f3e50abe2c154af45/Imagenes/Captura%20de%20pantalla%202025-04-11%20234004.jpg"  width="400">
</p>

En Simscape, aplicar entradas al sistema mecánico requiere transformar señales generadas desde el entorno de Simulink (como funciones escalón, senoidales o algoritmos de control) a señales físicas que puedan interactuar con el modelo. Para esto, se utiliza el bloque PS Converter.

El PS Converter es una herramienta clave que permite convertir señales no físicas en señales físicas, adecuadas para interactuar con el entorno Simscape. Este bloque es esencial para:

- Prescribir entradas dinámicas a las juntas (por ejemplo, ángulos deseados o posiciones lineales).
- Aplicar torques o fuerzas variables en función del tiempo o de un controlador.
- Controlar trayectorias mecánicas generadas por algoritmos de control.

<p align="center">
  <img src="https://github.com/user-attachments/assets/80382fda-dda3-4192-943d-244b9882a5ac"  width="100">
</p>

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/a310790f3533d968b1ec3d9987005e1361085a2a/Imagenes/Captura%20de%20pantalla%202025-04-11%20234623.jpg"  width="500">
</p>

Cuando se aplican **entradas manuales** (por ejemplo, con un bloque como `Stair Generator` o `Signal Builder`), la señal pasa por un proceso que involucra:

- **Conversión física** con `PS Converter`
- **Aplicación de un filtro derivativo interno**, que suaviza la señal para evitar discontinuidades no físicas
- **Cálculo de derivadas de segundo orden**, que son necesarias para la resolución de ecuaciones dinámicas del sistema (como velocidad y aceleración)

Este proceso permite que el sistema obtenga información completa de la evolución temporal del movimiento, asegurando coherencia física en los resultados.

## 3. Desarrollo Guiado de un Mecanismo en Simscape
A continuación, se describe el procedimiento básico para modelar un sistema mecánico utilizando la biblioteca de Simscape Multibody

### Paso 1: Creación de un nuevo modelo en Simulink
- Abre MATLAB y selecciona Simulink.
- Haz clic en "Blank Model" para iniciar un nuevo proyecto.
- Guarda el archivo con un nombre representativo (por ejemplo, `modelo_mecanismo.slx`).
- Asegúrate de tener disponible la biblioteca de **Simscape > Multibody**.

### Paso 2: Adición de elementos (cuerpos rígidos, juntas, actuadores)
- Inserta el bloque **World Frame** como referencia global.
- Agrega cuerpos rígidos mediante el bloque **Solid** para representar los eslabones o componentes del sistema.
- Conecta los sólidos utilizando juntas mecánicas (por ejemplo, **Revolute Joint**, **Prismatic Joint**, **Pin Slot Joint**, etc.), según el tipo de movimiento que desees permitir.
- Incorpora **actuadores** (**Joint Actuator**) si deseas aplicar movimiento, y **sensores** (**Joint Sensor**) para observar variables del sistema.
- Usa **Rigid Transform** si necesitas ajustar las posiciones relativas entre los componentes.

### Paso 3: Configuración de parámetros físicos
- Define la geometría de cada cuerpo rígido (dimensiones, forma, orientación).
- Establece propiedades de masa e inercia en cada **Solid**.
- Ajusta los límites y condiciones iniciales en las juntas (por ejemplo, posición, velocidad).
- Si se emplean señales de entrada, utiliza **PS Converter** para traducir señales de control a variables físicas.
- Aplica filtros y derivadas si se trabaja con señales manuales como **Stair Generator**.

### Paso 4: Simulación
- Conecta todo al **Solver Configuration** y **Mechanical Reference** para cerrar el sistema físico.
- Agrega **Scope** o **Simscape Results Explorer** para visualizar las variables de salida.
- Ejecuta la simulación ajustando el tiempo en los **Simulation Settings**.
- Verifica el comportamiento mecánico en el visor 3D (**Simscape Multibody Explorer**).

### Ejemplos Prácticos 
💡**Ejemplo: Movimiento oscilatorio vertical del cubo**
A continuación, se simula un movimiento oscilatorio vertical del cubo, restringido a un desplazamiento alternante a lo largo de un único eje mediante una Prismatic Joint, que limita el movimiento a un solo grado de libertad lineal. Este movimiento es generado por una señal senoidal, convertida en el entorno de Simulink mediante un bloque PS Converter, lo que da lugar a un desplazamiento de ida y vuelta con frecuencia y amplitud definidas.

A partir del esquema presentado, se procede a realizar una descripción concisa del sistema, destacando sus componentes principales y su funcionamiento dentro del entorno de simulación.


<p align="center">
  <img src="https://github.com/user-attachments/assets/0c2f4eae-404a-4449-b724-8683042abba2"  width="500">
</p>


**Configuración del Sistema**

**1. Configuración del Bloque Mechanism Configuration**
Este bloque se utiliza para establecer los parámetros globales del entorno de simulación mecánica. Para este caso, se habilita la gravedad, configurada para actuar a lo largo del eje Y.

<p align="center">
  <img src="https://github.com/user-attachments/assets/14da1f3e-f8b1-4237-8312-4ab7c63b3b5f"  width="400">
</p>

**2. Configuración del Bloque Sine Wave**
Generar una señal senoidal que actuará como entrada dinámica para el movimiento del cubo.

Configuración:

- Amplitude: 0.5 (Desplazamiento máximo del cubo)
- Bias: 0 (Sin desplazamiento constante)
- Samples per period: 10 (Discretización de la señal)
- Sine type: Sample based (Se utiliza una onda senoidal basada en muestras)

En ese sentido, la señal senoidal generada tiene una amplitud de 0.5, y el cubo oscila con esa amplitud sobre el eje Y, con una resolución adecuada.

<p align="center">
  <img src="https://github.com/user-attachments/assets/1f4c2434-c4f9-4774-b41b-acf0590ff6ce"  width="400">
</p>

**3. Configuración del Bloque Prismatic Joint**
Restringir el movimiento relativo entre los cuerpos rígidos a lo largo de un eje lineal.

Parámetros configurados:

- Actuation:
  - Force:`Automatically Computed`  
    El bloque calcula automáticamente la fuerza requerida para que el cuerpo se mueva según la señal de entrada prescrita, considerando las fuerzas externas, como la gravedad.
  
  - Motion:`Provided by Input`  
    El desplazamiento del cuerpo móvil no se determina por las leyes físicas del sistema, sino que es impuesto directamente desde una entrada externa. Esta entrada proviene de una señal física (por ejemplo, una onda senoidal convertida desde Simulink mediante un **Simulink-PS Converter**).

- Sensing:
  - Position: Activada  
    Esta opción permite medir en tiempo real la posición del cuerpo a lo largo del eje Z. La activación de esta opción es útil para monitoreo, análisis posterior o para la implementación de lazos de control en tiempo real.
  
  - Las demás opciones (Velocity, Acceleration, Actuator Force, etc.) no están activadas en esta configuración, pero podrían habilitarse si se requiere una observación más detallada del comportamiento dinámico del sistema.

Esta configuración, junto con una entrada senoidal, genera un **movimiento oscilatorio vertical prescrito** del cuerpo (cubo) en el eje Z. Gracias al sensor de posición activado, es posible visualizar y registrar la trayectoria del cubo a lo largo del tiempo, lo que resulta útil para validar el comportamiento deseado o comparar contra otras estrategias de control.

<p align="center">
  <img src="https://github.com/user-attachments/assets/530f6d3e-e831-4a27-9c1a-34991b193078"  width="400">
</p>

**4. Configuración del Bloque Brick Solid**
Definir un cubo con ciertas dimensiones en el espacio simulado.

Configuración:

- Dimensiones: [1 1 1] (El cubo tiene 1 metro de ancho, alto y profundidad).

- Unidad: Metro (m), que es una unidad estándar en simulaciones físicas.

Se define un cubo perfecto de 1 metro cúbico en el entorno de simulación, lo que proporciona un cuerpo rígido sobre el cual se aplicarán las fuerzas.

<p align="center">
  <img src="https://github.com/user-attachments/assets/15d44cf6-9d75-4eac-bdeb-5ad4b7a29ddd"  width="400">
</p>


#### Simulación del Cubo

Durante la ejecución de la simulación, se puede observar el comportamiento dinámico del cubo creado mediante el bloque **Solid**. Este cubo está acoplado a una **junta prismática (Prismatic Joint)**, la cual permite desplazamientos exclusivamente a lo largo de un eje lineal, en este caso, el eje vertical (eje Y).

Gracias a la señal senoidal aplicada como entrada de movimiento al **Prismatic Joint**, el cubo ejecuta un **movimiento oscilatorio de traslación vertical**, subiendo y bajando de forma periódica a lo largo del tiempo.

En la animación de la simulación se aprecia claramente cómo el cubo:

- Asciende y desciende suavemente en función de la amplitud y frecuencia de la onda senoidal configurada.
- Mantiene una trayectoria rectilínea sobre el eje **Y**, gracias a las restricciones impuestas por el **Prismatic Joint**.
- Responde con fluidez al perfil de entrada definido, evidenciando un correcto acoplamiento entre el mundo físico (Simscape) y el entorno de señales matemáticas (Simulink).

Este resultado valida el modelo construido, confirmando que la interacción entre los bloques ha sido correctamente configurada para simular un comportamiento físico realista.

<p align="center">
  <img src="https://github.com/user-attachments/assets/ca005403-439f-4eb2-86da-5df6b42d9c85"  width="400">
</p>


<p align="center">
  <img src="https://github.com/user-attachments/assets/60dd17f3-9c65-4ed6-9a59-77b6c9839e58"  width="400">
</p>

### 📚 Ejercicio 1: Sistema biela-manivela-corredera

Este mecanismo clásico puede modelarse con tres cuerpos rígidos: manivela, biela y pistón. 

<p align="center">
  <img src="https://github.com/user-attachments/assets/570e2076-b81d-430f-9586-223987135b0b"  width="400">
</p>

Este tipo de sistema es ampliamente utilizado en aplicaciones como motores de combustión interna y compresores, debido a su capacidad de convertir un **movimiento rotacional** en **movimiento lineal**.

#### Descripción del Modelo

El modelo se estructura a partir de varios bloques fundamentales de Simscape Multibody:

- **Solver Configuration**: Configura el solucionador para realizar la simulación física.
- **World Frame**: Define el sistema de referencia inercial global.
- **Mechanism Configuration**: Permite ajustar condiciones globales del sistema, como la gravedad.
- **Simulink-PS Converter**: Convierte una señal senoidal de entrada de Simulink en una señal física (PS) utilizable por los bloques de Simscape.
- **PS-Simulink Converter**: Convierte señales físicas de salida nuevamente al dominio de Simulink para su visualización (por ejemplo, en el Scope).

#### Componentes del Mecanismo

1. **Manivela**: 
   - Bloque sólido que gira continuamente alrededor de un eje fijo mediante una **Revolute Joint** (articulación rotacional).
   - El movimiento rotacional se genera mediante la señal senoidal conectada a la junta rotacional, simulando un eje impulsor.

2. **Biela**: 
   - Conectada entre la manivela y la corredera mediante dos juntas **Revolute Joint**.
   - Transmite el movimiento rotacional de la manivela a la corredera en forma de desplazamiento lineal.

3. **Corredera**: 
   - Representada como un sólido que se mueve linealmente gracias a una **Prismatic Joint**.
   - Esta junta limita el movimiento a lo largo de un solo eje (en este caso, lineal horizontal o vertical, según la configuración del modelo).
   - El desplazamiento de la corredera se visualiza mediante un bloque **Scope**.

4. **Rigid Transform**:
   - Se utiliza para establecer posiciones relativas entre los distintos componentes sólidos y ajustar alineaciones físicas.

#### Funcionalidad

El sistema convierte el **movimiento oscilatorio rotacional de la manivela**, provocado por la onda senoidal, en un **movimiento alternativo rectilíneo de la corredera**. La biela actúa como el eslabón intermedio que transmite y adapta el movimiento entre las otras dos partes.

Este modelo permite observar en tiempo real cómo se comporta un sistema mecánico real bajo condiciones de entrada dinámicas y es útil tanto en simulaciones de diseño como en estudios de control y dinámica de mecanismos.

#### Simulación

En las figuras se muestran capturas de la simulación en Simscape Multibody del sistema biela-manivela-corredera. En esta vista, se pueden observar claramente los tres elementos principales del mecanismo:

- **Manivela** (bloque azul a la izquierda),
- **Biela** (elemento en color magenta),
- **Corredera** (bloque marrón a la derecha).

<p align="center">
  <img src="https://github.com/user-attachments/assets/3d3dbf0d-e8b4-4666-889d-926d9f08844f"  width="400">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/a766ed80-13c7-47f0-99fa-4f7484e5b91f"  width="400">
</p>


En la animación se puede notar que:

- El conjunto de cuerpos rígidos reacciona de manera continua a la entrada de onda senoidal.
- La **biela** actúa como eslabón intermediario dinámico, cambiando de orientación para acompañar tanto el giro de la manivela como el desplazamiento de la corredera.
- El sistema completo funciona de manera armónica, simulando fielmente un **ciclo mecánico completo**, como el que ocurre en el pistón de un motor de combustión interna.

### 📚 Ejercicio 2: Modelodo de un mecanismo de tres eslabones

El modelo de un mecanismo compuesto por **tres eslabones** conectados mediante **juntas rotacionales (Revolute Joints)** permite representar con fidelidad el comportamiento de sistemas articulados como brazos robóticos, extremidades mecánicas o manipuladores articulados.

<p align="center">
  <img src="https://github.com/user-attachments/assets/0a2a3750-5ff9-4512-9b81-6f2b4f8d5496"  width="400">
</p>

### Componentes del Modelo

- **Solver Configuration**: Define los parámetros de resolución del modelo físico.
- **World Frame**: Establece el marco de referencia global para la simulación.
- **Mechanism Configuration**: Permite especificar condiciones físicas del entorno como la gravedad.
- **Rigid Transform**: Posiciona el primer eslabón respecto al marco global.


### Estructura de los Eslabones

1. **Eslabón 1**
   - Conectado al **World Frame** mediante una **Revolute Joint**.
   - Permite la rotación inicial del sistema.
   - Simula una base giratoria.

2. **Eslabón 2**
   - Unido al extremo del eslabón 1 mediante una segunda **Revolute Joint**.
   - Esta articulación permite el movimiento relativo entre el primer y segundo segmento.
   - El bloque de sólido representa su geometría y masa.

3. **Eslabón 3**
   - Conectado al final del segundo eslabón a través de una tercera **Revolute Joint**.
   - Funciona como el extremo libre o efector del sistema.

### Funcionalidad del Sistema

- **Actuación rotacional**: A través de las juntas rotacionales, se puede aplicar movimiento controlado a cada eslabón.
- **Medición angular**: Mediante sensores en las juntas se puede obtener la posición angular de cada articulación.
- **Salida a Scope**: El ángulo de alguna de las juntas es enviado a un bloque `Scope` mediante un `PS-Simulink Converter`, permitiendo visualizar la respuesta dinámica del sistema.

### Simulación.

Las siguientes figuras corresponden a diferentes momentos capturados durante la simulación del mecanismo de **tres eslabones** articulados mediante juntas rotacionales (`Revolute Joint`). Este sistema puede asociarse conceptualmente con un brazo robótico en movimiento, en el cual cada eslabón se mueve como resultado de las señales de entrada que provocan rotaciones en las articulaciones.

<p align="center">
  <img src="https://github.com/user-attachments/assets/7fbfee20-4f56-4bc3-953c-7f3de4c63acc"  width="400">
</p>


<p align="center">
  <img src="https://github.com/user-attachments/assets/657b20b4-5b67-417d-82ad-c2e449923a1d"  width="400">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/1091a68a-ea4d-439d-9b28-08f911012cfa"  width="400">
</p>


### 📚 Ejercicio 3: Suspensión automotriz

En un sistema de suspensión:

- Las ruedas están conectadas al chasis por eslabones.
- Se usan juntas rotacionales y traslacionales para simular los grados de libertad del sistema.
- Se pueden incluir resortes y amortiguadores para representar las fuerzas de suspensión.

<p align="center">
  <img src="https://github.com/user-attachments/assets/d63b7486-699b-4263-ab57-e3f2b3c9dfc2"  width="400">
</p>

### Componentes del Modelo

- **Solver Configuration**: Establece los parámetros numéricos necesarios para la resolución del modelo físico.
- **World Frame**: Define el marco de referencia absoluto para todo el sistema mecánico.
- **Mechanism Configuration**: Permite configurar propiedades globales del entorno como la gravedad.
- **Simulink-PS Converter**: Convierte señales de Simulink a señales físicas para interactuar con bloques de Simscape.
- **Rigid Transform**: Ajusta la posición y orientación del sólido respecto al marco global.
- **Brick Solid**: Representa un cubo con propiedades físicas como masa, volumen y geometría.

### Estructura del Sistema

1. **Sistema de Entrada**
   - Una señal de entrada tipo onda (por ejemplo, sinusoidal) es transformada en una señal física mediante el bloque `Simulink-PS Converter`.
   - Esta señal puede representar una fuerza aplicada al sistema.

2. **Transformación Rígida**
   - El bloque `Rigid Transform` define la posición inicial del cubo en el espacio tridimensional.
   - Sirve para conectar correctamente el sólido al marco de referencia global.

3. **Cubo (Brick Solid)**
   - Actúa como el objeto físico que responde a la entrada de fuerza o movimiento.
   - Puede desplazarse linealmente, simulando el comportamiento de una masa móvil.

### Funcionalidad del Sistema

- **Simulación de movimiento lineal**: El sistema está diseñado para analizar el desplazamiento de un sólido (cubo) en una dimensión, producto de una entrada definida.
- **Base para aplicaciones prácticas**: Esta estructura básica puede servir como base para simular fenómenos más complejos, como un sistema de **suspensión automotriz**, en el que el cubo representa la masa suspendida (por ejemplo, el chasis del vehículo).
- **Interacción mecánica**: Permite estudiar la respuesta dinámica del sólido ante una fuerza externa o entrada controlada.

### Simulación
<p align="center">
  <img src="https://github.com/user-attachments/assets/9e6a6e8f-29c5-4c88-a9dd-a17c4098fe81"  width="400">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/e6d408b4-2446-4b64-be84-d1272e698e41"  width="400">
</p>

## Conclusiones
Dentro de la temática, se pudo llegar a las siguientes conclusiones:

El uso de herramientas como Solid, Prismatic Joint y Simulink-PS Converter permitió representar con precisión los sistemas físicos y establecer una conexión clara entre las señales matemáticas y los comportamientos mecánicos reales. Al configurar correctamente parámetros como la masa, la geometría del cuerpo y las fuerzas actuadoras, se logró simular un movimiento oscilatorio vertical mediante una señal senoidal, demostrando que incluso dinámicas simples pueden ser modeladas con gran fidelidad y utilizadas como base para sistemas más complejos.

Gracias a la activación de sensores y a la integración visual entre Simulink y Simscape Multibody, fue posible monitorear en tiempo real el comportamiento del sistema, lo que facilitó el análisis cinemático y dinámico. Esta representación gráfica ayudó a identificar comportamientos inesperados y a ajustar los valores del modelo con rapidez. Modificar variables como dimensiones, frecuencias o condiciones iniciales dentro del entorno simulado hizo que el proceso de prueba fuera más eficiente, reduciendo significativamente los recursos necesarios en etapas tempranas de diseño.

Además, la experiencia fortaleció la capacidad de análisis del estudiante al combinar modelado físico con teoría mecánica. Se sentaron así las bases para futuras implementaciones de control automático en sistemas reales, ya que los principios aplicados pueden ser adaptados fácilmente a entornos que incluyan sensores, actuadores y controladores. Esta simulación no solo consolidó conocimientos técnicos, sino que también ofreció una visión más integral del diseño de mecanismos y su validación dentro de entornos virtuales.

## Referencias

- MathWorks. (2024). *Simscape Multibody User’s Guide*. The MathWorks, Inc. https://www.mathworks.com/help/physmod/sm/  
Guía oficial de MathWorks que explica el uso de bloques como Solid, Revolute Joint, Prismatic Joint y Simulink-PS Converter.

- MathWorks. (2024). *Simulink Documentation*. The MathWorks, Inc. https://www.mathworks.com/help/simulink/  
Referencia general del entorno Simulink para la creación y control de modelos mediante señales y algoritmos.

- The MathWorks, Inc. (2020, abril 9). *Physical Modeling Tutorial, Part 6: Introduction to Multibody Simulation* [Video]. YouTube. https://www.youtube.com/watch?v=lItmRlH4iBw  
Tutorial visual sobre modelado físico y simulación multibody con herramientas de MathWorks.


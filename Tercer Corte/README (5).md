# COMO HACER USO DE LOS GEMELOS DIGITALES (QUANSER)

![image](https://github.com/user-attachments/assets/01916511-5fb9-4e7f-bc56-84fca18238f4)

🔹 *Figura 1: Quanser.* 

Los gemelos digitales son representaciones virtuales de sistemas físicos que permiten simular y analizar su comportamiento en un entorno controlado.  

# 1) Definiciones

> 🔑 Gemelo Digital (Digital Twin: Réplica virtual de un sistema físico que emula su comportamiento en tiempo real mediante modelos computacionales y flujo bidireccional de datos, permitiendo simulación, monitoreo y predicción.

> 🔑 QUARC (Quanser Real-time Control: Plataforma de desarrollo para sistemas de control en tiempo real que se integra con MATLAB/Simulink, proporcionando bloques especializados para adquisición de datos y control de hardware Quanser.

> 🔑 Qube-Servo 2: Dispositivo didáctico para control de posición angular que consta de un motor DC con encoder de alta resolución (4096 CPR), disco de inercia y circuitos de protección, utilizado en laboratorios de control automático.

> 🔑 Stall Detection: Mecanismo de protección que detecta cuando un motor eléctrico recibe voltaje pero no gira (bloqueo), activando el apagado automático para prevenir daños por sobrecalentamiento.

> 🔑 CPR (Counts Per Revolution): Unidad de medida que indica el número de pulsos que genera un encoder óptico por cada revolución completa (360°) del eje del motor.

> 🔑 HIL (Hardware-In-the-Loop): Metodología de prueba que combina componentes físicos reales con modelos simulados, permitiendo validar algoritmos de control en condiciones seguras antes de su implementación final.

> 🔑 Pulse Generator: Bloque de Simulink que genera señales cuadradas periódicas con parámetros configurables (amplitud, frecuencia y ciclo de trabajo), usado para excitar sistemas de control.

# 2) Requisitos Previos  

A continuación se detallan los requisitos mínimos necesarios para poder utilizar el software Quanser en conjunto con MATLAB. Es importante cumplir con estas especificaciones para garantizar el correcto funcionamiento de las herramientas.  

- **MATLAB** (versión R2021a+)  
  *Se requiere una versión reciente de MATLAB debido a las dependencias de librerías y funciones utilizadas por QUARC.*  
- **Cuenta Quanser**: [Registro aquí](https://portal.quanser.com/)   
  *Es necesario registrarse en el portal de Quanser para acceder a descargas de software, licencias y documentación técnica.*  
- **Complemento QUARC**  
  *QUARC es un middleware esencial para la comunicación en tiempo real entre MATLAB/Simulink y los dispositivos Quanser.*  

# 3) Paso a paso

En este apartado se detalla el proceso de configuración inicial para integrar Quanser Interactive Labs con MATLAB, incluyendo capturas ilustrativas.  

## 3.1 Instalación del Complemento Quanser Interactive Labs  

*Este procedimiento instala las bibliotecas necesarias para la creación y operación de gemelos digitales en entornos Quanser:*  

- **Abrir MATLAB**  
  *Inicie MATLAB con privilegios de administrador para evitar conflictos durante la instalación.*  

- **Descargar el complemento Quanser Interactive Labs desde el portal**  
  *El paquete de instalación está disponible en la sección "Downloads" de su cuenta Quanser después del login.*  

- **Instalar el paquete siguiendo las instrucciones del asistente**  
  *Acepte los términos de licencia y seleccione la opción "Typical Install" a menos que necesite componentes personalizados.*  

![image](https://github.com/user-attachments/assets/5ba8c5e4-a6d4-4e25-ae59-f07311455623)  
🔹 *Figura 2: Interfaz del complemento Quanser Interactive Labs para gemelos digitales, mostrando el panel de control de dispositivos virtuales.*  



## 3.2 Inicio del Software

Antes de iniciar cualquier trabajo práctico con los modelos virtuales desarrollados por Quanser, es fundamental preparar adecuadamente el entorno de simulación proporcionado por la plataforma QLabs. Este entorno simula plantas físicas tridimensionales de manera realista, permitiendo la interacción y experimentación sin la necesidad de contar con el hardware físico real. Este enfoque resulta especialmente útil en etapas iniciales de diseño, pruebas de controladores o cuando se desea realizar simulaciones remotas o en entornos educativos.

El primer paso consiste en ejecutar el comando **qlabs_setup**, el cual tiene la función de configurar las rutas de acceso, inicializar los parámetros del entorno virtual y establecer la comunicación con los módulos necesarios. Esta configuración automatiza la integración del entorno QLabs con herramientas como MATLAB y Simulink, asegurando que las bibliotecas y funciones específicas estén disponibles para su correcto funcionamiento.

Una vez configurado el entorno, se procede con el comando **qlabs_launch**, que inicia la interfaz gráfica de usuario del software QLabs. Desde esta interfaz, el usuario puede seleccionar el modelo de planta virtual deseado entre una variedad de experimentos predefinidos, como sistemas de control de posición, péndulos invertidos, módulos de servomecanismos, entre otros. Esta selección es crucial, ya que determina la planta sobre la cual se diseñarán, implementarán y validarán los algoritmos de control.

Este proceso de inicialización no solo permite establecer una conexión eficiente entre los bloques de Simulink y la planta simulada, sino que también garantiza que las simulaciones se desarrollen en tiempo real, facilitando la observación del comportamiento dinámico del sistema y la evaluación del desempeño del controlador diseñado. En resumen, la correcta configuración y ejecución del entorno QLabs constituye un paso indispensable para llevar a cabo prácticas de control avanzadas y garantizar resultados representativos antes de pasar a una implementación física.

![image](https://github.com/user-attachments/assets/50827ea6-b57d-451d-a835-9497ec405088)

🔹 *Figura 3: Codigo de inicio.*  


Al ejecutar el comando correspondiente para iniciar QLabs, se despliega una ventana emergente en la cual el usuario, en este caso el estudiante, debe autenticarse utilizando su cuenta institucional proporcionada por la universidad. Este proceso de autenticación es un requisito indispensable, ya que permite verificar la identidad del usuario y garantizar el acceso a los recursos licenciados específicamente para la institución educativa.

Una vez completado satisfactoriamente el proceso de inicio de sesión, se habilita la interacción total con la interfaz de QLabs, permitiendo al usuario acceder a los modelos tridimensionales virtuales. En este punto, ya es posible cargar los escenarios de simulación, conectar los bloques de control desarrollados en Simulink con las plantas virtuales, y comenzar con las tareas de diseño, validación y ajuste de los controladores en tiempo real.

## Ventana 
Luego de completar el proceso de autenticación con éxito, el entorno QLabs despliega una interfaz que permite seleccionar entre diversas plantas virtuales habilitadas de acuerdo con la licencia académica institucional. En el contexto de nuestra universidad, actualmente se dispone del acceso a tres modelos de sistemas físicos simulados, cada uno diseñado para abordar diferentes conceptos clave en el área del control automático:

### 1. Modelo "Ball and Beam":
Este sistema representa una aplicación clásica de control, en la cual una esfera se desplaza sobre una viga cuya inclinación es regulada por un actuador rotacional. La complejidad radica en la naturaleza inestable del sistema, lo que lo convierte en una herramienta didáctica para el análisis de estabilidad, diseño de sistemas de retroalimentación y ajuste de controladores que gestionen trayectorias o puntos de equilibrio. Su comportamiento dinámico requiere la implementación de estrategias de control robusto y sintonización precisa.

### 2. Sistema "Aero":
Este modelo simula una estructura aeroespacial en configuración de doble hélice, donde las fuerzas de empuje inducidas generan movimientos acoplados sobre varios ejes. La dinámica no lineal y el fuerte acoplamiento entre variables convierten este sistema en una plataforma avanzada para el estudio de control multivariable, linealización alrededor de puntos de operación y diseño de compensadores. Es particularmente útil en cursos intermedios y avanzados de sistemas dinámicos.

### 3. Planta "Qube 2 – DC Motor":
Corresponde a la simulación de un servomecanismo de corriente continua montado en una estructura compacta. Esta planta es ideal para introducirse en el diseño de controladores clásicos como PID, así como para comprender el comportamiento temporal de sistemas de primer y segundo orden. Además, permite implementar controladores de velocidad y posición, facilitando el estudio de conceptos como sobregiro, tiempo de establecimiento y errores en estado estacionario.


![image](https://github.com/user-attachments/assets/530805c1-6c4f-4acd-a966-fbb71663236d)

🔹 *Figura 4: Ventana de inicio (gemelos digitales).*  

## 3.3 Interaccion motor DC Qube 2

En el ámbito académico de la ingeniería de control el **QUBE-Servo 2** es una plataforma experimental avanzada creada por **Quanser**, orientada al aprendizaje práctico en control de sistemas dinámicos. Esta planta didáctica ha sido diseñada para facilitar el estudio de principios fundamentales y avanzados del control automático en sistemas electromecánicos, permitiendo a los estudiantes implementar algoritmos en tiempo real, analizar el comportamiento dinámico y validar modelos directamente en hardware físico a través de entornos como **Simulink y QUARC**. Su diseño modular y su integración directa con herramientas de simulación la convierten en un recurso clave para los laboratorios universitarios de mecatrónica, robótica e ingeniería de control.

### Interfaz USB :
Actúa como el enlace de comunicación entre el sistema físico y la estación de trabajo del usuario. A través de esta conexión, es posible ejecutar controladores en tiempo real desde el computador, enviar señales de mando y recibir datos de medición, lo que permite una interacción eficiente y una sincronización precisa entre el software de control y el hardware experimental.

### Sensores de medición (encoders):
El sistema está equipado con encoders ópticos de alta resolución que capturan continuamente las variables del sistema, como la posición angular y la velocidad. Estos datos se utilizan como entrada para los algoritmos de retroalimentación, permitiendo ajustar el comportamiento del sistema en función del estado actual y mejorar la precisión del control implementado.

### Motor de corriente continua (DC):
Este componente cumple la función de actuador principal, generando el movimiento rotacional necesario para las pruebas experimentales. Su respuesta controlable lo hace adecuado para desarrollar ejercicios de regulación y seguimiento, analizar la respuesta transitoria del sistema, e implementar técnicas como control proporcional, integral y derivativo (PID).

### Módulos mecánicos intercambiables:
El QUBE-Servo 2 permite conectar distintos elementos mecánicos al eje del motor para simular diferentes tipos de sistemas. Entre los más utilizados se encuentran:

- **El brazo rotatorio**, que posibilita el análisis de control de posición, estabilidad y seguimiento de referencias angulares.

- **El péndulo invertido**, que representa un sistema altamente inestable y no lineal, ideal para probar técnicas de control robusto, estabilización por retroalimentación y observadores de estado.

![image](https://github.com/user-attachments/assets/849df92a-bc55-404f-b65d-0e1ba3cdb764)

🔹 *Figura 5: QUBE-Servo 2*


## 3.3 Fases de la Simulación en Simulink con Bloques QUARC

En el presente laboratorio se desarrollará un modelo básico en Simulink utilizando bloques pertenecientes al entorno QUARC, con el objetivo principal de controlar un motor de corriente continua (DC) y medir en tiempo real el ángulo de rotación de su eje. Esta práctica forma parte fundamental del proceso de aprendizaje en sistemas de control en tiempo real, permitiendo al estudiante integrar conocimientos teóricos con su aplicación práctica en entornos de simulación interactiva.

El sistema se construirá mediante la lectura de datos de un encoder conectado al eje del motor, cuya señal será procesada para obtener el desplazamiento angular. A través de un bloque de ganancia, estos pulsos se transformarán a unidades físicas como grados o radianes. Posteriormente, la señal será utilizada como retroalimentación dentro de un lazo de control, el cual puede configurarse manualmente o mediante un controlador automático (como un PID), permitiendo generar una salida analógica que gobierna el comportamiento del motor.

Asimismo, se implementarán mecanismos de visualización que permiten monitorear las variables clave del sistema, así como herramientas de conmutación y detección de fallos, como la detección de estancamiento del motor (stall detection). Esta última funcionalidad es esencial para garantizar la seguridad del sistema, ya que puede alertar si el motor deja de moverse pese a recibir una señal de control.

En conjunto, esta experiencia permitirá a los participantes familiarizarse con el flujo de trabajo en un entorno de programación en tiempo real, comprender la importancia de la adquisición de datos y el control digital, y establecer una comunicación efectiva entre el modelo computacional y la planta física o simulada, mediante el uso de sensores y actuadores virtuales conectados a través de hardware-in-the-loop (HIL). El conocimiento adquirido en esta práctica es directamente aplicable en áreas como automatización industrial, robótica y control de procesos.

![image](https://github.com/user-attachments/assets/f03cef2c-a4de-45d3-8382-6801fae8b6b2)

🔹 *Figura 6: Simulación de prueba.*  

A continuación, se describen las principales fases de la simulación realizada para el control de un motor de corriente continua utilizando bloques QUARC en Simulink:

### 1. HIL Read Encoder (Lectura del encoder)
- **Función:** Lee la posición angular del eje del motor en tiempo real a través de un encoder. Este dispositivo emite pulsos en función del desplazamiento del eje.

### 2. Gain (Ganancia)
- **Función:** Convierte los pulsos del encoder en unidades físicas como grados o radianes. Esto facilita la interpretación y el procesamiento de la señal en el sistema de control.

### 3. Display / Scope (Visualización)
- **Función:** Muestra la señal de posición angular del motor para facilitar el monitoreo durante la simulación.

### 4. Controlador (PID u otro)
- **Función:** Genera una señal de control a partir del error entre la posición deseada y la posición real. Su objetivo es minimizar ese error para lograr un comportamiento deseado del motor.

### 5. Manual Switch (Conmutador manual)
- **Función:** Permite seleccionar entre una entrada de control manual (por ejemplo, un valor constante) o la salida del controlador automático.

### 6. HIL Write Analog (Salida analógica)
- **Función:** Envía la señal analógica al motor. Esta señal controla el comportamiento del motor, como la velocidad o el torque.

### 7. Stall Detection (Detección de estancamiento)
- **Función:** Monitorea si el motor se encuentra detenido cuando debería estar en movimiento. Si se detecta una condición de estancamiento, puede generar una alarma o interrumpir la operación.

### 8 💡 Ejemplo: Configuracion pulse generator

**Datos a utilizar:**

#### Configuración de Simulink
- **Bloque HIL Write Analog**: Envía señal al canal analógico #0 del dispositivo de adquisición, conectado al amplificador PWM que controla el motor DC.  
- **Bloque Constant**: Conectado al bloque HIL Write Analog .  
  - Valor configurado en `0.5` para aplicar 0.5 V al motor.  

#### Verificación
1. Ejecute `Monitor & Tune` para compilar y ejecutar el modelo.  
2. Confirme que:  
   - Una señal positiva genera una medición positiva (critical en sistemas de control).  
   - Dirección del disco: **horario** con entrada positiva.  
3. Modifique el bloque a `-0.5` y verifique giro **antihorario**.  
4. Detenga la simulación.  

#### 8.1 Medición y Estimación de Velocidad Angular

##### Temas
- Filtros pasa bajos/altos.  
- Estimación de velocidad mediante encoder.  
- Medición directa con tacómetro.  

#### 8.2 Filtros Analógicos

##### Filtro Pasa Bajos (LPF)
- **Función de transferencia**:

  $$H_{LP}(s) = \frac{\omega_f}{s + \omega_f}$$  
  - $\omega_f$: Frecuencia de corte (rad/s).  
  - Atenúa frecuencias altas ($\geq \omega_f$) en $-3$ dB (~70% amplitud).  

##### Filtro Pasa Altos (HPF)

- **Función de transferencia**:

  $$ H_{HP}(s) = \frac{\omega_f s}{s + \omega_f} $$  
  - Equivalente a una derivada ($s$) seguida de un LPF.  
  - Usado para estimar velocidad angular ($\hat{\omega}_f(t)$) desde posición angular ($\theta(t)$).  


##### 8.3 Estimación de Velocidad con Encoder + HPF

### Configuración en Simulink
1. **Modificaciones previas**:  
   - Cambiar ganancia del encoder a **radianes**.  
   - Reemplazar `HIL Read Encoder` por `HIL Read Encoder Timebase`.  

2. **Modelo propuesto** :  
   - Añadir bloque `Switched derivative for linearization` (derivada de la posición para estimar velocidad en rad/s).  
   - Conectar a `Scope`
   - 
3. **Filtrado**:  
   - Inicialmente omitir el LPF (`50/(s + 50)`).  
   - Posteriormente, implementar HPF combinado: `50s/(s + 50)`.  

### Análisis de Resultados
- **Señal de posición**: Discreta (pasos pequeños) → Derivada amplifica componentes de alta frecuencia.  
- **Filtro HPF**: Mejora la estimación de velocidad al atenuar ruido.  
- **Frecuencia de corte**:  
  - Valor nominal: $\omega_f = 50$ rad/s (~7.96 Hz).  
  - Variar $\omega_f$ entre **10-200 rad/s** (1.6-32 Hz) y evaluar:  
    - **Beneficio de $\omega_f$ bajo**: Mayor suavizado.  
    - **Compensación**: Retardo en la respuesta.  

.
## 3.4 Configuraciones motor DC Qube 2

Para comenzar con el desarrollo de sistemas de control utilizando **Simulink**, es fundamental establecer una conexión entre el entorno de modelado y la planta virtual o física. En este caso, se utilizará el modelo del **Qube-Servo 2 – DC Motor**. Esta integración permite que MATLAB/Simulink transmita comandos de control hacia la planta y reciba datos de retroalimentación en tiempo real, facilitando la implementación de controladores y el análisis del comportamiento dinámico del sistema.

### Procedimiento general para conectar el modelo:

#### A. Lanzar el entorno de Simulink:

En la consola de MATLAB, ingresa el comando simulink y presiona Enter. Esto abrirá la interfaz gráfica desde la cual se puede iniciar la construcción del modelo.

#### B. Crear un modelo nuevo:

En la ventana inicial de Simulink, selecciona la opción “Blank Model” para generar un nuevo espacio de trabajo donde se insertarán los bloques necesarios para el control del sistema.

#### C. Agregar bloques desde la biblioteca QUARC:

Accede al navegador de bibliotecas y busca la categoría “QUARC Targets”. Esta contiene todos los bloques necesarios para interactuar con el hardware o con la planta virtual.
Dentro de esta biblioteca, localiza el bloque específico correspondiente al Qube-Servo 2 - DC Motor. El nombre del bloque puede presentar variaciones menores según la versión del software instalada.

![image](https://github.com/user-attachments/assets/c291d22e-5827-4146-893d-c63f3c13e8b8)

🔹 *Figura 7: QUARC Targets*

Una vez añadido el bloque al modelo, se deben ajustar ciertos parámetros para que la comunicación entre Simulink y la planta sea exitosa, ya sea para trabajar con simulación (gemelo digital) o con el dispositivo físico conectado por USB.

### Configuración del bloque del motor:

![image](https://github.com/user-attachments/assets/dfa4ca0e-17bf-4c0b-925f-0953888985ff)

🔹 *Figura 8: hil-1*

#### A. Abrir las propiedades del bloque:

Haz doble clic sobre el bloque del motor insertado en el modelo. Esto abrirá la ventana de configuración donde se deben definir varios parámetros de conexión.

#### B. Definir el nombre del dispositivo:

En el campo destinado al identificador del hardware, escribe **HL_1**. Este nombre será utilizado por los demás bloques del modelo para referenciar correctamente la conexión con el actuador.

#### C. Seleccionar el tipo de dispositivo y su identificador:

La configuración específica depende del entorno de trabajo:

- Para el entorno virtual (gemelo digital):

- Para el dispositivo físico conectado por USB:


Esta selección informa al sistema de simulación si debe establecer conexión con la planta digital simulada localmente o con el hardware físico conectado al computador. Es un paso crítico que garantiza el correcto funcionamiento de los controladores implementados y la recolección de datos experimentales para análisis posterior.

![image](https://github.com/user-attachments/assets/a14fdf1e-1ab0-4b85-8e5e-02cd79f1cbbb)

🔹 *Figura 9: Confirguracion hil-1*


#### Procedimiento de Ejecución de Simulación en Entorno de Control en Tiempo Real

Tras la implementación y parametrización inicial del modelo de control en el entorno Simulink, se inicia la fase de ejecución computacional. En esta etapa crítica, el sistema realiza las siguientes operaciones secuenciales:

- **Inicialización del Protocolo de Comunicación:** El software establece un enlace de datos bidireccional con la interfaz del hardware Quanser mediante protocolos de tiempo real, implementando mecanismos de handshaking para garantizar la sincronización temporal.

- **Verificación de Estado Operativo:** El indicador lumínico ubicado en la barra superior del IDE de Simulink adquiere una tonalidad verde espectral, lo que constituye una confirmación visual de:

-- Establecimiento exitoso del canal de comunicación hardware-software

-- Correcta sincronización del reloj en tiempo real (RT Clock)

-- Disponibilidad del sistema para interacción con la planta física

- **Monitorización del Proceso:** Durante la ejecución, el subsistema de diagnóstico verifica continuamente:

--La latencia del bucle de control

-- La integridad de las señales I/O

-- La estabilidad temporal del proceso


![image](https://github.com/user-attachments/assets/681462fd-9f42-41b2-96dc-4e1979462fda)

🔹 *Figura 9: En funcionamiento*

# 4) CONCLUSIONES  

- Los gemelos digitales en Quanser permiten una simulación precisa de sistemas físicos, facilitando el diseño, prueba y optimización de algoritmos de control antes de su implementación en hardware real. Esto reduce costos y riesgos en entornos educativos e industriales.

- La integración con MATLAB/Simulink y QUARC proporciona un entorno robusto para el desarrollo de controladores en tiempo real, aprovechando herramientas como HIL (Hardware-In-the-Loop) para validar modelos con alta fidelidad.

- El Qube-Servo 2 es una plataforma versátil para el aprendizaje de control automático, gracias a sus sensores de alta resolución (encoder de 4096 CPR), modularidad mecánica y capacidad de simular sistemas complejos como péndulos invertidos y servomotores.

- La metodología HIL combinada con gemelos digitales permite realizar pruebas seguras y eficientes, detectando fallos como el stall condition antes de afectar al sistema físico.

- La configuración paso a paso (instalación de QUARC, autenticación en QLabs y conexión con Simulink) demuestra la importancia de un flujo de trabajo estructurado para garantizar resultados confiables en simulaciones y control en tiempo real.

- Eficiencia en el Aprendizaje:Los gemelos digitales de Quanser, como el *Qube-Servo 2*, optimizan el proceso de enseñanza en ingeniería de control al permitir experimentación virtual interactiva, reduciendo la dependencia de hardware físico y facilitando la comprensión de conceptos teóricos mediante simulaciones realistas.

- Escalabilidad y Flexibilidad: La plataforma QUARC permite adaptar los modelos de simulación a diferentes niveles de complejidad, desde sistemas básicos (como control PID en motores DC) hasta problemas avanzados (control multivariable o no lineal), lo que la hace útil tanto en educación como en investigación.

- Seguridad y Protección de Equipos: Mecanismos como stall detection y monitoreo en tiempo real protegen los dispositivos físicos durante pruebas, evitando daños por sobrecargas o mal funcionamiento, lo que es crucial en entornos de laboratorio con equipos costosos.

- Preparación para Industria 4.0: El uso de gemelos digitales y metodologías HIL alinea la formación académica con las demandas de la industria moderna, donde la simulación y el control digital son pilares en automatización, robótica y sistemas ciberfísicos.

- Interoperabilidad con Herramientas Estándar: La compatibilidad nativa de Quanser con MATLAB/Simulink asegura que los estudiantes y profesionales trabajen con herramientas ampliamente utilizadas en la industria, facilitando la transición entre entornos académicos y aplicaciones reales.


# 5) REFERENCIAS  

- Quanser. (2023). Quanser Interactive Labs Documentation. Disponible en: https://www.quanser.com

- MathWorks. (2023). Simulink Real-Time and QUARC Integration. Disponible en: https://www.mathworks.com

- Quanser. (2022). *Qube-Servo 2 User Manual*.

- Tao, F., et al. (2019). Digital Twins and Cyber–Physical Systems toward Smart Manufacturing and Industry 4.0: Correlation and Comparison. Engineering, 5(4), 653-661.

- MathWorks. (2021). Hardware-in-the-Loop (HIL) Testing with Simulink.

# Perfiles de Movimiento Avanzados: Curvas en S y Movimiento Multieje
Los perfiles de movimiento juegan un papel clave en aplicaciones donde la precisión y el control son determinantes, ya que permiten optimizar el desempeño y reducir esfuerzos mecánicos innecesarios, por esta razón, el uso de curvas en S se ha convertido en una estrategia fundamental, dado que suaviza las transiciones al regular la aceleración y desaceleración de forma progresiva, minimizando vibraciones y mejorando la estabilidad del sistema. Además, en entornos con múltiples actuadores, el movimiento multieje cobra importancia, pues asegura que cada eje siga su trayectoria de manera sincronizada para evitar desajustes, lo que garantiza desplazamientos precisos y eficientes, contribuyendo no solo a un mejor rendimiento, sino también a una mayor vida útil de los componentes mecánicos y electrónicos involucrados.

## Perfil de Movimiento con Curva en S
>🔑 *Perfiles de movimiento con curvas en S :* Es una estrategia de control que utiliza transiciones progresivas para suavizar la aceleración y desaceleración, lo que reduce el jerk (cambios bruscos de aceleración) y optimiza el tiempo de transferencia punto a punto al ajustar el perfil según la carga. 

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/c9215149709dcd64306668f00d3be01c708b97c7/Imagenes/Betterimage.ai_1743362496537.jpeg"  width="500">
</p>

Estos suelen implementar dentro de su comportamiento una dinámica de 7 fases, ya que además de acelerar, deslizar y desacelerar, incorporan segmentos de transición que permiten una distribución progresiva y continua de la aceleración, eliminando picos abruptos y reduciendo el jerk, generando así un desplazamiento más fluido, preciso y estable.

### Características
Para entender la importancia de las curvas en S, es clave conocer sus principales características:

- **Reducción de Vibraciones:** Inyecta mucho menos energía vibratoria en los mecanismos y la carga, tanto con servomotores como con motores paso a paso.
- **Ajuste de Oscilaciones:** Permite cancelar oscilaciones ajustando la relación entre las fases de transición y los tramos de aceleración constante.  
- **Optimización del Tiempo de Transferencia Efectivo:** Reduce en un 25–33 % el tiempo desde que la carga inicia su movimiento hasta que se asienta, ideal para movimientos punto a punto de alta velocidad.  
- **Gestión Uniforme del Jerk:** Mantiene un valor constante de cambio en la aceleración (jerk), distribuyendo el cambio a lo largo del tiempo.
  
### Comparación entre Sistemas de Transmisión y Control de Movimiento
A continuación, se muestran dos gráficos que ilustran el comportamiento en velocidad y aceleración, seguidos de una tabla comparativa con las diferencias clave entre la curva en S y el perfil trapezoidal.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/fde05a7c2dfa995b4eae15b8751aca7331d24520/Imagenes/Betterimage.ai_1743358409497.jpeg"  width="800">
</p>

La gráfica de velocidad muestra cómo la curva en S facilita transiciones continuas y suaves entre aceleración y desaceleración, mientras que el perfil trapezoidal presenta cambios bruscos en los tramos de aceleración y desaceleración, afectando la continuidad del movimiento.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/038fe408fa20b9dacd648f2c5dc1beb0887a01ea/Imagenes/Betterimage.ai_1743361954557.jpeg"  width="800">
</p>

De igual forma, la gráfica de aceleración evidencia cómo la curva en S mantiene un cambio uniforme (jerk constante) a lo largo del tiempo, evitando picos que generan vibraciones y desgaste, en contraste con los picos abruptos observados en el perfil trapezoidal.

A continuación, se muestra una tabla comparativa que resume estas diferencias:

| Característica               | Curva en S                                                                 | Perfil Trapezoidal                                                     |
|------------------------------|----------------------------------------------------------------------------|------------------------------------------------------------------------|
| Complejidad del Perfil       | Estructura de 7 fases con transiciones progresivas y continuas             | Estructura de 3 fases con cambios abruptos                             |
| Rendimiento en Transferencia | Optimiza el tiempo efectivo, permitiendo movimientos punto a punto ágiles    | Mayor tiempo de estabilización en cada movimiento                      |
| Impacto Mecánico             | Minimiza impactos y reduce el desgaste al distribuir uniformemente el jerk   | Picos de aceleración que generan vibraciones y aceleran el desgaste      |
| Adaptabilidad a Cargas       | Ajuste preciso de las transiciones según la carga, cancelando oscilaciones   | Menor flexibilidad para adaptarse a variaciones en la carga             |
| Precisión y Estabilidad      | Control refinado que mejora la precisión y estabilidad del sistema           | Transiciones bruscas        |


💡**Ejemplo: Análisis Experimental según Performance Motion Devices**

El experimento realizado por Performance Motion Devices evaluó cómo los perfiles de movimiento afectan la estabilidad de la carga utilizando un motor lineal conectado a una carga con elasticidad controlada, replicando un sistema mecánico real

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/42fc1956ed591aaf5ca52f6940bae6cc19962ba4/Imagenes/Betterimage.ai_1743363106678.jpeg"  width="600">
</p>

Las gráficas muestran que el perfil trapezoidal genera oscilaciones debido a cambios bruscos en la aceleración, lo que prolonga el tiempo de estabilización, mientras que el perfil con curva S distribuye mejor la aceleración, reduciendo vibraciones y demostrando que es más eficiente para movimientos precisos y controlados.

### Tipos de curvas en S

- **Curva en S Estandar:** 
- **Curva en S Estandar:**



## Modelo Matemático del Perfil de Movimiento en S

El modelo matemático de la curva en S se basa en un polinomio de segundo orden que define el perfil de velocidad, permitiendo una transición suave en la aceleración y evitando cambios bruscos en el movimiento.

 La ecuación general se expresa como:

$$
v(t) = C_1 t^2 + C_2 t + C_3
$$  

Donde $C_1$, $C_2$ y $C_3$ son coeficientes determinados por las condiciones de frontera, logrando un desplazamiento más controlado y eficiente al reducir vibraciones e impactos en sistemas mecánicos.  


En este contexto, para obtener cada coeficiente, se analiza cada segmento de la curva en S, en ese sntido como se muestra en la figura, hay dos secciones, A y B, y en este caso se realizará el análisis de la sección A.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/13949018ee22e88b273505ede4aab3b705e53d19/Imagenes/Captura%20de%20pantalla%202025-03-30%20165645.jpg"  width="600">
</p>

Se imponen las siguientes condiciones de frontera:
**Condición inicial (t = 0):**  
   La velocidad inicial es cero:

<p align="center">
   $$v(0) = C_1 (0)^2 + C_2 (0) + C_3 = 0 \quad\Longrightarrow\quad C_3 = 0$$
</p>

**Condición de aceleración inicial:**  
   La aceleración se obtiene derivando la velocidad:

<p align="center">
   $$a(t) = \frac{dv}{dt} = 2C_1 t + C_2$$
   </p>
   
Si se requiere que la aceleración inicial sea cero, se impone:

   <p align="center">
   $$a(0) = C_2 = 0$$
  </p>

**Condición intermedia (t = $$\frac{t_a}{2}$$):**  
Se establece que la velocidad a la mitad del tiempo de aceleración es la mitad de la velocidad máxima:

<p align="center">
   $$v\left(\frac{t_a}{2}\right) = \frac{v_m}{2}$$
   </p>
   
Con $C_2 = 0$ y $C_3 = 0$ , se tiene:

   <p align="center">
   $$C_1 \left(\frac{t_a}{2}\right)^2 = \frac{v_m}{2}$$
   </p>
   
   De donde se despeja:

   <p align="center">
   $$C_1 = \frac{2v_m}{t_a^2}$$
  </p>
  
Así, los coeficientes quedan definidos como:

- $C_1 = \dfrac{2v_m}{t_a^2}$
- $C_2 = 0$
- $C_3 = 0$

💡**Ejemplo: Análisis Curva S de 3 segmentos**

## Métodos de Coordinación de Movimiento Multieje

La coordinación de múltiples ejes es esencial en sistemas como la robótica o el mecanizado CNC, ya que permite que varios ejes trabajen en conjunto para seguir trayectorias complejas con alta precisión. Una adecuada sincronización reduce errores, vibraciones y el desgaste de los componentes, lo que se traduce en un mejor rendimiento global.


<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/abb1830c4c6117f7044992fb0538960a493df8a7/Imagenes/Captura%20de%20pantalla%202025-03-30%20194525.png"  width="600">
</p>

Existen tres formas principales de coordinar el movimiento de dos o más ejes:

- Mover un eje a la vez (Movimiento Secuencial)
- Slew Motion (Movimiento Independiente de los Ejes)
- Interpolated Motion (Sincronización de Movimiento)

### Mover un eje a la vez (Movimiento Secuencial)

Este método consiste en ejecutar el movimiento de cada eje de forma secuencial, es decir, se mueve un eje X, una vez que completa su recorrido, se activa el siguiente, de este modo se tiene un control individualizado en cada eje y se puede apreciar que la trayectoria global presenta transiciones abruptas, ya que cada eje opera de manera independiente sin superposición temporal en sus movimientos

### Slew Motion (Movimiento Independiente de los Ejes)
En este enfoque, ambos ejes se ponen en marcha al mismo tiempo pero cada uno sigue su propio perfil de velocidad y aceleración, lo que permite que cada eje se adapte a sus propias condiciones de trabajo y se mueva de forma simultánea sin exigir que inicien ni finalicen exactamente al mismo instante, de esta forma se obtiene una mayor flexibilidad en el control, aunque la sincronización global puede no ser perfecta.

### 💡Ejemplo de Clase:

Si ambos ejes de una máquina se mueven a 4 cm/s con un perfil de velocidad trapezoidal y un tiempo de aceleración \( t_a = 0.2 \) s, ¿cuánto tiempo tomará a cada eje completar su movimiento si las distancias a recorrer son $L_x = 16$ cm y $L_y = 12$ cm?  

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/c914b68fad3de24a936b4002df265bbc90df05ef/Imagenes/Captura%20de%20pantalla%202025-03-30%20195648.png"  width="300">
</p>

**Cálculo:**  

- Para el eje **X**:


  <p align="center">
  $$t_{m_x} = \frac{L_x}{v_m} - t_a = \frac{16}{4} - 0.2 = 3.8 \text{ s}$$  
</p>


<p align="center">
  $$ t_{total_x} = t_{m_x} + 2t_a = 3.8 + 2(0.2) = 4.2 \text{ s} $$  
</p>

- Para el eje **Y**:

  <p align="center">
$$ t_{m_y} = \frac{L_y}{v_m} - t_a = \frac{12}{4} - 0.2 = 2.8 \text{ s} $$
</p>

<p align="center">
$$ t_{total_y} = t_{m_y} + 2t_a = 2.8 + 2(0.2) = 3.2 \text{ s} $$  
</p>

El eje **X** tardará **4.2 s** en completar su movimiento, mientras que el eje **Y** lo hará en **3.2 s**.


### 📚 Ejercicio 1:

Un sistema cartesiano con dos ejes, $x$ y $y$, debe mover cada eje de forma independiente sin sincronización estricta. El eje $x$ debe recorrer $L_x = 18$ cm y el eje $y$ debe recorrer $L_y = 12$ cm. Ambos se mueven a una velocidad de 6 cm/s con un perfil de velocidad trapezoidal y un tiempo de aceleración de $t_a = 0.2$ s. ¿Cuánto tiempo tomará a cada eje completar su movimiento?  

**Cálculo:**

Para cada eje, el tiempo de movimiento se calcula como:  

- **Para el eje $x$ :**

<p align="center">
  $$ t_m = \frac{L_x}{v_x} - t_a = \frac{18}{6} - 0.2 = 2.8 \text{ s} $$  
</p>

<p align="center">
  $$ t_{\text{total}, x} = t_m + 2t_a = 2.8 + 2(0.2) = 3.2 \text{ s} $$  
</p>

- **Para el eje $y$ :**

<p align="center">
  $$ t_m = \frac{L_y}{v_y} - t_a = \frac{12}{6} - 0.2 = 1.8 \text{ s} $$  
</p>

<p align="center">
  $$ t_{\text{total}, y} = t_m + 2t_a = 1.8 + 2(0.2) = 2.2 \text{ s} $$  
</p>



### Interpolated Motion (Sincronización de Movimiento)

Este método se basa en planificar una trayectoria global en la que se calculan puntos de referencia comunes para todos los ejes, de modo que cada uno inicie y termine su movimiento de forma sincronizada, utilizando algoritmos de interpolación se logra que la velocidad y la aceleración de cada eje se ajusten de manera coordinada, lo que da como resultado una trayectoria suave y precisa, ideal para aplicaciones que requieren alta sincronización.

### 💡Ejemplo de Clase:

Dado el ejemplo anterior, al calcular por interpolación se encuentra que la velocidad del eje \( y \) debe ajustarse para que ambos ejes terminen al mismo tiempo.  

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/c914b68fad3de24a936b4002df265bbc90df05ef/Imagenes/Captura%20de%20pantalla%202025-03-30%20195648.png"  width="300">
</p>

**Cálculo:**  

<p align="center">
$$ v_y = \frac{L_y}{t_m + t_a} = \frac{12}{3.8 + 0.2} $$  
</p>

<p align="center">
$$ v_y = \frac{12}{4} = 3 \text{ cm/s} $$  
</p> 

### 📚 Ejercicio 2:

Para mejorar la sincronización del sistema, se busca que ambos ejes terminen su movimiento al mismo tiempo. La velocidad del eje $x$ se mantiene en $v_x = 5$ cm/s y su tiempo total de movimiento es $t_{\text{total}} = 4.3$ s. ¿Cuál debe ser la nueva velocidad $v_y$ para que el eje $y$ termine simultáneamente con el eje $x$?  

**Cálculo:**  

Se despeja $v_y$ de la ecuación del tiempo de movimiento:  

<p align="center">
  $$ v_y = \frac{L_y}{t_m + t_a} $$  
</p>  

<p align="center">
  $$ v_y = \frac{15}{(4.3 - 2(0.3))} = \frac{15}{3.7} \approx 4.05 \text{ cm/s} $$  
</p>  

## Conclusiones
Dentro de la temática, se pudo llegar a las siguientes conclusiones:

En primer lugar, las curvas en S son fundamentales para optimizar el tiempo de transferencia de una carga de máquina, ya que permiten reducir impactos mecánicos y mejorar la estabilidad del movimiento, esto es especialmente útil cuando el motor está acoplado a la carga mediante un mecanismo, pues minimiza vibraciones y esfuerzos innecesarios en los componentes, además, su aplicación abarca una gran variedad de sistemas de control de movimiento en la industria, garantizando un desempeño más eficiente y seguro en procesos automatizados.

Por otro lado, el número de segmentos en una curva S influye directamente en la suavidad y precisión del movimiento, mientras más segmentos se añadan, mayor será el control sobre la aceleración y desaceleración, lo que permite reducir el tiempo de asentamiento de la carga y mejorar la respuesta del sistema, sin embargo, un exceso de segmentación puede aumentar el tiempo total de movimiento, por lo que es necesario encontrar un equilibrio adecuado mediante la experimentación y el ajuste de parámetros en la configuración del perfil de movimiento.

Finalmente, en aplicaciones que requieren el control de múltiples ejes, la correcta sincronización de los movimientos es crucial para garantizar una operación eficiente y libre de errores, en estos casos, las estrategias de interpolación y la optimización de los perfiles de velocidad juegan un papel clave en la reducción de tiempos de ciclo y en la mejora del rendimiento global del sistema, además, la integración de sistemas avanzados de captura de movimiento facilita la evaluación y ajuste de los parámetros para lograr la máxima precisión en procesos industriales y robóticos.

## Referencias
[1] PMD Corp., "S-Curve Profiles Deep Dive Article," Performance Motion Devices, 2023. [En línea]. Disponible en: https://www.pmdcorp.com/resources/type/articles/get/s-curve-profiles-deep-dive-article. [Accedido: 25-mar-2025].

[2] Infoplc, "Motion Control Tip: Perfil de Velocidad Trapezoidal," InfoPLC, 2024. [En línea]. Disponible en: https://www.infoplc.net/blogs-automatizacion/item/113225-motion-control-tip-perfil-velocidad-trapezoidal. [Accedido: 27-mar-2025].

[3] LibreServo, "Curvas de Movimiento," LibreServo, 2024. [En línea]. Disponible en: https://www.libreservo.com/es/articulo/curvas-movimiento. [Accedido: 30-mar-2025].

[4] J. E. Cote B., Perfiles de Movimiento, diapositivas de clase, 9° semestre, Universidad ECCI, 2025.






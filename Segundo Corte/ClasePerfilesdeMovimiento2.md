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


💡**Ejemplo 1: Análisis Experimental según Performance Motion Devices**

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


## Métodos de Coordinación de Movimiento Multieje
### Slew Motion (Movimiento Independiente de los Ejes)
### Interpolated Motion (Sincronización de Movimiento)

## Conclusiones
Dentro de la temática, se pudo llegar a las siguientes conclusiones:


## Referencias
[1]CHAPMAN (2005). "Máquinas eléctricas". McGraw-Hill.
[2]SERRANO IRIBARNEGARAY (1989). "Fundamentos de máquinas eléctricas rotativas". Marcombo.
[3]“AulasVirtualesECCI: Entrar al sitio”, Edu.co. [En línea]. Disponible: https://aulas.ecci.edu.co/course/view.php?id=9304 .












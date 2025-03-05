# Fundamentos de Control de Movimiento
Actualmente, los sistemas de control de movimiento son fundamentales en el área de la automatización industrial, ya que permiten gestionar y coordinar el desplazamiento de cargas a través de actuadores y controladores, mejorando la precisión y la eficiencia en los procesos. Sin embargo, esto no siempre fue así, ya que antes de su implementación se dependía de sistemas de transmisión mecánica complejas que aunque eran funcionales, presentaban limitaciones en términos de flexibilidad y mantenimiento. En ese sentido, con el avance de la tecnología, estos sistemas fueron reemplazados por soluciones digitales más avanzadas, que integraban estrategias de retroalimentación donde se optimizaban el rendimiento y la adaptabilidad. 

---
## Evolución del Control de Movimiento
Desde sus inicios, la industria ha depositado su confianza  en los sistemas de transmisión mecánica para transferir energía y movimiento a través de mecanismos como engranajes, correas y cadenas, que permiten configurarse en innumerables aplicaciones, sin embargo, el diseño y mantenimiento del mismo plantea retos que con el tiempo han llevado a la búsqueda de opciones más sofisticadas, incorporando sensores y algoritmos avanzados, el control de movimiento ha evolucionado hacia sistemas digitales más eficientes y adaptables.

<p align="center">
  <img src="https://github.com/Evellyn27/Apuntes-Control-de-Movimiento/blob/e5c78494079f45b4aca660a2ef2e218f0795a500/Imagenes/Evolucion.png">
</p>

>🔑 *Sistema de transmisión mecánica:* Es un conjunto de elementos diseñados para transferir potencia y movimiento desde un componente motriz (como un motor) hasta un elemento receptor (como una rueda o una herramienta). 

>🔑 *Variable Controlada:* se refiere a la cantidad o condición es midible y  se pretende controlar.

>🔑 *Variable Manipulada:* esta variable permite condicionar a la variable controlada mediante una modificacion de la misma.

#### Comparación entre Sistemas de Transmisión y Control de Movimiento
| Característica              | Sistemas de Transmisión Mecánica | Sistemas de Control de Movimiento |
|----------------------------|--------------------------------|--------------------------------|
| **Precisión**              | Baja a media                  | Alta                          |
| **Flexibilidad**           | Limitada                      | Adaptable                      |
| **Eficiencia Energética**  | Dependiente de fricción y desgaste | Optimizada mediante algoritmos |
| **Mantenimiento**          | Frecuente debido al desgaste mecánico | Menor, basado en software y sensores |
| **Costo Inicial**          | Bajo a medio                   | Medio a alto                   |
| **Aplicaciones**           | Transportadores, maquinaria pesada | Robótica, automatización avanzada |

💡**Ejemplo 1:** En este caso se tienen dos figuras. 

<p align="center">
  <img src="https://motorkote.com.co/wp-content/uploads/2022/06/Sistema-de-transmisio%CC%81n-2.gif">
</p>

## Ejes de Movimiento y Componentes Clave

Los sistemas de control de movimiento operan a través de distintos **ejes de movimiento**, los cuales determinan los grados de libertad de un mecanismo. Dependiendo de la aplicación, estos pueden clasificarse en:

- **Ejes Lineales:** Permiten el desplazamiento en una sola dirección, como en sistemas de automatización y ensamblaje.
- **Ejes Rotacionales:** Utilizados en brazos robóticos y maquinaria CNC, donde se requiere giro y precisión angular.
- **Ejes Combinados:** Sistemas con múltiples grados de libertad que permiten movimientos complejos en diferentes planos.


> 🔑 *Ejemplo:* En un robot cartesiano, los ejes de movimiento son X, Y y Z, permitiendo un control preciso en un espacio tridimensional.

### 3. Componentes Clave de un Sistema de Control de Movimiento

Para lograr un **control de movimiento eficiente**, es necesario contar con los siguientes elementos:

- **Controlador de Movimiento:** Coordina las señales y define la trayectoria del movimiento.
- **Accionamiento o Amplificador:** Convierte las señales de control en potencia para accionar los motores.
- **Actuadores (Motores):** Convierten la energía eléctrica en movimiento mecánico.
- **Sensores y Retroalimentación:** Dispositivos como encoders y resolvers que permiten ajustar el comportamiento del sistema en tiempo real.
- **Mecanismos de Transmisión:** Engranajes, husillos de bolas o correas que conectan los actuadores con la carga en movimiento.


### 4. Ventajas del Control de Movimiento Moderno

La implementación de sistemas de control de movimiento avanzados ofrece múltiples ventajas:

- Mayor precisión y repetibilidad en los procesos.
- Optimización del consumo energético.
- Mejor respuesta ante perturbaciones y variaciones de carga.
- Menor desgaste mecánico y costos de mantenimiento.
- Mayor flexibilidad y adaptabilidad en la industria.

## 5. Esquemas de Control y Aplicaciones Industriales Avanzadas

>🔑 *Perturbaciones:* se le conoce a todo aquello que afecta de manera adversa el desarrollo de un proceso.
## 6. Conclusiones

## Referencias
[1] “Comunicaciones”. Tipos y Modos de Comunicaciones. Accedido el 28 de agosto de 2024. [En línea]. Disponible: http://xkiller-damndx.mex.tl/frameset.php?url=/1488142_Caracteristicas-de-las-senales-y-Conceptos-de-Ondas.html

[2] F. Miyara, CONVERSORES D/A Y A/D, 2a ed. 2004.

[3] Wilaeba electronica. “Conversor digital analogico R-2R”. Índice de contenido. Accedido el 1 de septiembre de 2024. [En línea]. Disponible: https://wilaebaelectronica.blogspot.com/2017/01/conversor-digital-analogico-r-2r.html

[4] Wilaeba electronica. “Conversor digital analogico por suma ponderada”. Índice de contenido. Accedido el 1 de septiembre de 2024. [En línea]. Disponible: https://wilaebaelectronica.blogspot.com/2017/01/conversor-digital-analogico-por-suma-ponderada.html












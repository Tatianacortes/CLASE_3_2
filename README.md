# CLASE 3 II CORTE
# 📘 Perfil de Velocidad en Curva S — Resumen Detallado

##  Tipos de Perfiles de Velocidad

- **Trapezoidal:** Perfil tradicional con aceleración constante, velocidad constante y desaceleración.
- **Curva S (Suavizada):** Cambios suaves en la aceleración, reduciendo vibraciones y desgaste mecánico.
- **Curva S Pura:** Perfil más avanzado, con aceleración suavemente variable desde 0 hasta la velocidad máxima, y luego desaceleración suave.



## Modelo Matemático de la Curva S

Cada segmento del perfil se modela con un polinomio de segundo orden:

$v(t) = C_1 t^2 + C_2 t + C_3$

Donde:
- $C_1, C_2, C_3$ son coeficientes determinados por condiciones de frontera.
- El modelo permite una aceleración variable y controlada.


## Obtención del Modelo – Curva A

### Condiciones Iniciales:
- $v(0) = 0$
- $a(0) = \frac{dv}{dt} = 0$
- Aceleración máxima se alcanza a $t = \frac{t_a}{2}$

### Sustituyendo:
$v(0) = C_1 (0)^2 + C_2 (0) + C_3 = 0 \Rightarrow C_3 = 0$

A partir de $v\left( \frac{t_a}{2} \right) = \frac{v_m}{2}$:

$\frac{2v_m}{t_a^2} \left( \frac{t_a}{2} \right)^2 = \frac{v_m}{2} \Rightarrow C_1 = \frac{2v_m}{t_a^2}$

Entonces:

$v(t) = \frac{2v_m}{t_a^2} t^2$


## Cálculo de la Posición

### Perfil en dos fases:

1. Aceleración: $v_A(t) = \frac{2v_m}{t_a^2} t^2$
2. Desaceleración: $v_B(t) = v_m - \frac{2v_m}{t_a^2} (t_a - t)^2$

### Integración para posición:

$s(t) = \int_0^{\frac{t_a}{2}} v_A(t)\,dt + \int_{\frac{t_a}{2}}^{t_a} v_B(t)\,dt$

#### Ejemplo 

$v_m = 32\ \text{cts/s} $, $ t_a = 30\ \text{ms}$:

$s(t) = \int_0^{15} \frac{64}{900} t^2\,dt + \int_{15}^{30} 32 - \frac{64}{900}(30 - t)^2\,dt$

Resultado:

$s_{0B}(t) = 0.023t^3 \bigg|_0^{15} + 32t + 0.071(900t - 60t^2 + \frac{t^3}{3}) \bigg|_{15}^{30}$

$s_{0B}(t) = 77.62 + 480 - 64.12 = 493.49\ \text{cts}$

$s_{0C}(t) = 493.49 + 32 \cdot 70 = 2733.49\ \text{cts}$


**Graficación del Perfil en MATLAB**

Con:
- $ v_{max} = 10\ \text{in/s} $
- $ t_a = 4\ \text{s} $
 ![Figura de prueba](IMAGES/curvas.png)


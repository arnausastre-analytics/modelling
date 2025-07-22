Contexto
Este proyecto aplica modelos de teoría de colas y simulación discreta para dimensionar recursos en servicios de atención al cliente. Los métodos permiten analizar la capacidad necesaria para garantizar tiempos de espera reducidos y minimizar bloqueos.

Objetivo
Evaluar el rendimiento de un centro de atención con tráfico conocido y proponer configuraciones óptimas.
Se calculan métricas clave utilizando fórmulas analíticas y simulación.

Datos y supuestos
Tasa de llegada: 30 llamadas/hora.

Tiempo medio de servicio: 5 minutos.

Tráfico: 2.5 Erlangs.

Se considera un sistema multi-servidor sin abandonos.

Metodología
Modelos analíticos
Se implementan:

Fórmula Erlang-C:

Probabilidad de espera (Pw).

Tiempo medio de espera (Wq).

Fórmula Erlang-B:

Probabilidad de bloqueo.

El análisis se realiza sobre un rango de 4 a 10 agentes.

Simulación discreta
Se desarrolla un simulador basado en eventos:

Llegadas: proceso Poisson.

Servicios: tiempos exponenciales.

Métricas obtenidas:

Tiempo medio de espera.

Porcentaje de llamadas con espera > 2 min.

Utilización media de los agentes.

La simulación cubre un periodo de 4 horas.

Resultados
Resultados analíticos
Con 4 agentes:

Tiempo medio de espera: 1.07 min.

Bloqueo: 14.99%.

Con 6 agentes:

Tiempo medio de espera: 0.07 min.

Bloqueo: 2.82%.

Con 7 agentes:

Tiempo medio de espera: 0.02 min.

Bloqueo: 1%.

Resultados de simulación
Para 6 agentes durante 4 horas:

Llamadas atendidas: 127.

Tiempo medio de espera: 0.02 min.

% de llamadas con espera > 2 min: 0.8%.

Utilización media: 100%.

Conclusiones
El análisis muestra que con 6 agentes se logra un servicio eficiente:

Tiempo medio de espera casi nulo.

Bloqueo inferior al 3%.

Con 7 agentes se minimiza prácticamente cualquier tiempo de espera y bloqueo.

La simulación discreta confirma los resultados analíticos y permite observar la variabilidad.

Uso
El código incluye:

Cálculo de métricas para diferentes niveles de recursos.

Simulación empírica del comportamiento real.

El proyecto es reproducible en Google Colab y puede adaptarse a otros contextos:
call centers, logística, atención presencial o virtual.

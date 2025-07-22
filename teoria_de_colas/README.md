# Modelos de Teoría de Colas y Simulación Discreta

## Contexto
Este proyecto aplica modelos de teoría de colas y simulación discreta para dimensionar recursos en servicios de atención al cliente. Permite analizar la capacidad necesaria para garantizar tiempos de espera reducidos, minimizar bloqueos y modelar abandonos.

## Objetivo
Evaluar el rendimiento de un centro de atención con tráfico conocido y proponer configuraciones óptimas.  
Se calculan métricas clave utilizando fórmulas analíticas y simulación.

## Datos y supuestos
- Tasa de llegada: 30 llamadas/hora
- Tiempo medio de servicio: 5 minutos
- Tráfico: 2.5 Erlangs
- Sistema multi-servidor con y sin abandonos

## Metodología

### Modelos analíticos
Se implementan:
- **Fórmula Erlang-C**
  - Probabilidad de espera (Pw)
  - Tiempo medio de espera (Wq)
- **Fórmula Erlang-B**
  - Probabilidad de bloqueo
- **Fórmula Erlang-A**
  - Modelo que incluye tasa de abandono
  - Permite estimar el impacto de clientes que abandonan la cola tras cierto tiempo

El análisis se realiza sobre un rango de 4 a 10 agentes.

### Simulación discreta
Se desarrolla un simulador basado en eventos:
- Llegadas: proceso Poisson
- Servicios: tiempos exponenciales
- Abandonos: tiempo máximo de espera antes de abandonar

Métricas obtenidas:
- Tiempo medio de espera
- Porcentaje de llamadas con espera > 2 min
- Porcentaje de abandonos
- Utilización media de los agentes

La simulación cubre un periodo de 4 horas.

## Resultados

### Resultados analíticos
Con 4 agentes:
- Tiempo medio de espera: 1.07 min
- Bloqueo: 14.99%

Con 6 agentes:
- Tiempo medio de espera: 0.07 min
- Bloqueo: 2.82%

Con 7 agentes:
- Tiempo medio de espera: 0.02 min
- Bloqueo: 1%

Modelo Erlang-A:
- Se analiza el impacto de una tasa de abandono sobre estos resultados
- Mejora la precisión en escenarios donde los clientes abandonan si esperan demasiado

### Resultados de simulación
Para 6 agentes durante 4 horas:
- Llamadas atendidas: 127
- Tiempo medio de espera: 0.02 min
- % de llamadas con espera > 2 min: 0.8%
- Utilización media: 100%

## Conclusiones
- Con 6 agentes se logra un servicio eficiente:
  - Tiempo medio de espera casi nulo
  - Bloqueo inferior al 3%

- Con 7 agentes se minimiza prácticamente cualquier tiempo de espera y bloqueo.

- El modelo Erlang-A permite analizar escenarios más realistas con abandonos.

- La simulación discreta confirma los resultados analíticos y permite observar la variabilidad.

## Uso
El código incluye:
- Cálculo de métricas para diferentes niveles de recursos
- Simulación empírica del comportamiento real

Proyecto reproducible en Google Colab.  
Aplicable a call centers, logística, atención presencial o virtual.

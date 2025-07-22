# Modelo avanzado de cadenas de Markov para ciclo de vida de cliente

## Contexto
Este proyecto modela las dinámicas de estados en el ciclo de vida de un cliente en un servicio de suscripción.  
Se utiliza un enfoque basado en cadenas de Markov para analizar la evolución de clientes a través de distintos estados, estimar tiempos de retención y evaluar impacto de intervenciones comerciales.

## Objetivo
- Estimar la distribución estacionaria en estados transitorios
- Calcular probabilidades de terminación (churn) desde cualquier estado inicial
- Calcular el tiempo esperado de vida del cliente
- Simular impacto de una campaña de retención

## Datos y supuestos

### Estados considerados
1. Activo  
2. Activo alto valor  
3. Inactivo  
4. Recuperado  
5. Perdido (estado absorbente)

### Matriz de transición inicial (mensual)
| Desde / Hacia | Activo | Activo alto valor | Inactivo | Recuperado | Perdido |
| ------------- | ------ | ----------------- | -------- | ---------- | ------- |
| Activo        | 0.70   | 0.10              | 0.10     | 0.00       | 0.10    |
| Activo alto   | 0.05   | 0.85              | 0.05     | 0.00       | 0.05    |
| Inactivo      | 0.10   | 0.05              | 0.65     | 0.10       | 0.10    |
| Recuperado    | 0.50   | 0.10              | 0.10     | 0.20       | 0.10    |
| Perdido       | 0.00   | 0.00              | 0.00     | 0.00       | 1.00    |

## Metodología
Se utiliza la teoría de cadenas de Markov absorbentes:
- Cálculo de distribución estacionaria sobre estados transitorios
- Cálculo de probabilidades de absorción en el estado "Perdido"
- Estimación del tiempo esperado hasta absorción desde cada estado inicial

## Resultados

### Caso base
**Distribución estacionaria (transitorios):**
- Activo: 0.290  
- Activo alto valor: 0.446  
- Inactivo: 0.213  
- Recuperado: 0.050

**Probabilidad de terminar en "Perdido":**  
1.00 desde todos los estados transitorios

**Tiempo esperado hasta pérdida:**  
- Desde Activo: 12.22 meses  
- Desde Activo alto valor: 14.72 meses  
- Desde Inactivo: 11.94 meses  
- Desde Recuperado: 12.22 meses

### Escenario avanzado: campaña de retención
Se introduce una intervención comercial enfocada en clientes "Inactivo" y "Recuperado":
- Aumenta probabilidad de retorno a "Activo" y "Activo alto valor"
- Reduce probabilidad de churn desde estos estados

**Distribución estacionaria tras campaña:**
- Activo: 0.306  
- Activo alto valor: 0.483  
- Inactivo: 0.186  
- Recuperado: 0.025

**Probabilidad de terminar en "Perdido":**  
1.00 desde todos los estados transitorios

**Tiempo esperado hasta pérdida tras campaña:**  
- Desde Activo: 13.92 meses  
- Desde Activo alto valor: 16.42 meses  
- Desde Inactivo: 15.33 meses  
- Desde Recuperado: 14.17 meses

## Conclusiones
- El modelo baseline muestra una vida media de cliente de 12-14 meses dependiendo del estado inicial.
- La campaña de retención aumenta la vida media entre 1 y 3 meses según el segmento.
- El análisis permite identificar impactos potenciales de iniciativas comerciales sobre retención y churn.

## Uso
El código incluye:
- Modelado de cadenas de Markov con matriz de transición configurable
- Cálculo de métricas clave de ciclo de vida
- Simulación de escenarios con modificaciones en probabilidades de transición

Proyecto reproducible en Google Colab.  
Aplicable a análisis de retención de clientes, mantenimiento predictivo y evaluación de ciclos de vida en contratos, activos o usuarios.

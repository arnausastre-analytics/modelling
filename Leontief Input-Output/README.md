# Modelo Input-Output sectorial (Leontief) – Simulación y análisis de impacto económico

## Descripción
Este proyecto implementa un **modelo Input-Output sectorial basado en la matriz de Leontief**, utilizando datos simulados pero realistas para representar relaciones intersectoriales en una economía simplificada.  
El objetivo es analizar **cómo un shock de demanda final en un sector específico impacta en la producción total de toda la economía, capturando efectos directos e indirectos.**

## Objetivos principales
- Construir la matriz de coeficientes técnicos \( A \) que describe las interdependencias entre sectores económicos.
- Calcular la inversa de Leontief \( (I - A)^{-1} \), que mide los efectos totales (directos e indirectos).
- Simular la producción total requerida para satisfacer una demanda final dada.
- Implementar un **escenario de shock sectorial (+10% en la demanda de `Construction`) y cuantificar el impacto propagado**.
- Calcular y visualizar **multiplicadores sectoriales**, clave para consultoría económica y análisis estratégico.

## Tecnologías utilizadas
- Python 3
- numpy
- pandas
- matplotlib

## Estructura del repositorio

## Resultados clave
-  **Matriz técnica A** simulada, realista, con coeficientes entre sectores.
-  **Inversa de Leontief calculada para capturar efectos totales.**
-  **Multiplicadores sectoriales ordenados**, permitiendo identificar sectores con mayor efecto arrastre.
-  **Análisis de escenario: impacto total de un shock del +10% en el sector `Construction`.**
-  **Visualización clara y profesional** de resultados.

## Valor para negocio
Este proyecto demuestra cómo aplicar un modelo Input-Output para:
- Evaluar el efecto de **políticas industriales o planes de estímulo sectorial.**
- Identificar **sectores estratégicos con mayor impacto indirecto en la economía ("sectores arrastre").**
- Simular escenarios que ayuden a **la toma de decisiones de gobiernos, consultoras o grandes corporaciones interesadas en planificación económica y análisis de cadenas de valor.**

Además, la estructura modular permite reemplazar los datos simulados por datos reales de fuentes como **Eurostat o BEA (Bureau of Economic Analysis, EEUU)** para convertirlo en una herramienta práctica para proyectos reales.

## Cómo ejecutar
Clonar el repositorio:
```bash
git clone https://github.com/tuusuario/leontief-input-output.git
cd leontief-input-output

# Optimización de mezclas industriales con restricciones técnicas

## Contexto
Este proyecto aborda la optimización de formulaciones en un contexto industrial (alimentación, química, materiales).  
El objetivo es minimizar el coste de producción garantizando especificaciones técnicas y operativas del producto final.

## Objetivo
Minimizar el coste de una mezcla compuesta por varios ingredientes, cumpliendo propiedades de calidad, restricciones físicas y restricciones comerciales.  
Se utiliza programación lineal clásica como herramienta principal.

## Datos y supuestos

### Ingredientes
| Ingrediente | Coste (€/kg) | Pureza (%) | Densidad (g/cm3) | Toxicidad (%) |
| ----------- | ------------- | ---------- | ---------------- | ------------- |
| A           | 2.0           | 80         | 1.2              | 1.0           |
| B           | 3.0           | 60         | 1.0              | 3.0           |
| C           | 4.0           | 90         | 0.8              | 0.5           |
| D           | 1.5           | 50         | 1.5              | 4.0           |

### Requisitos del producto final
- Pureza ≥ 70 %
- Densidad entre 1.0 y 1.3 g/cm3
- Toxicidad ≤ 2 %
- Total mezcla = 100 %

## Metodología

### Caso base
Optimización para minimizar coste cumpliendo requisitos de pureza, densidad, toxicidad y proporciones totales.  
Sin restricciones adicionales sobre mínimos o máximos por ingrediente.

### Escenario avanzado
Restricciones industriales realistas añadidas:
- Ingrediente A ≤ 60 %
- Ingrediente B ≤ 60 %
- Ingrediente C ≤ 60 %
- Ingrediente D ≤ 60 %
- Ingrediente B ≥ 10 %
- Ingrediente C ≥ 10 %

Estas condiciones simulan requisitos de homogeneidad, estabilidad y límites operativos.

## Resultados

### Caso base
- Proporción A: 0.75
- Proporción B: 0.00
- Proporción C: 0.00
- Proporción D: 0.25
- Coste mínimo: 1.88 €/kg
- Pureza final: 72.50 %
- Densidad final: 1.27 g/cm3
- Toxicidad final: 1.75 %

### Escenario avanzado
- Proporción A: 0.55
- Proporción B: 0.10
- Proporción C: 0.10
- Proporción D: 0.25
- Coste mínimo: 2.18 €/kg
- Pureza final: 71.50 %
- Densidad final: 1.22 g/cm3
- Toxicidad final: 1.90 %

## Conclusiones
- En el caso base, la solución óptima concentra la mezcla en los ingredientes más baratos.  
- En el escenario avanzado, las restricciones adicionales obligan a soluciones más equilibradas con mayor coste unitario pero factibles en entornos industriales reales.

El análisis permite simular escenarios técnicos relevantes para industrias donde se requiera control de propiedades fisicoquímicas y costes.

## Uso
El código resuelve el problema mediante `scipy.optimize.linprog`.  
Proyecto reproducible en Google Colab.  
Fácilmente adaptable a otros sectores como alimentación, materiales, química o cosmética.

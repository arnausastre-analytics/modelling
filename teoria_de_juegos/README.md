# Modelo de teoría de juegos aplicado a competencia en precios

## Contexto
Este proyecto analiza situaciones competitivas entre dos empresas que definen estrategias de precios en mercados con interacción estratégica.  
Se aplica teoría de juegos para identificar equilibrios de Nash y analizar resultados bajo distintos supuestos.

## Objetivo
- Modelar interacciones estratégicas en pricing competitivo
- Calcular equilibrios de Nash en escenarios con diferentes niveles de complejidad
- Interpretar pagos esperados en equilibrio mixto
- Simular asimetrías competitivas entre empresas

## Metodología

### Caso base: juego 2x2 simétrico
Dos empresas con estrategias: Precio Bajo / Precio Alto.

|                  | B bajo | B alto |
| ---------------- | ------ | ------ |
| **A bajo**       | (3,3)  | (5,1)  |
| **A alto**       | (1,5)  | (4,4)  |

**Equilibrio encontrado:**  
- Estrategia pura (Bajo, Bajo) para ambos jugadores.

### Caso avanzado: juego 3x3 con 3 niveles de precio
Se introducen tres estrategias: Bajo, Medio, Alto precio.

|                  | B bajo | B medio | B alto |
| ---------------- | ------ | ------- | ------ |
| **A bajo**       | (2,2)  | (4,1)   | (5,0)  |
| **A medio**      | (1,4)  | (3,3)   | (4,2)  |
| **A alto**       | (0,5)  | (2,4)   | (3,3)  |

**Equilibrio encontrado:**  
- Estrategia pura (Bajo, Bajo).

### Extensión técnica 1: juego clásico puramente mixto
Matching Pennies.

|                  | B cara | B cruz |
| ---------------- | ------ | ------ |
| **A cara**       | (1,1)  | (-1,-1) |
| **A cruz**       | (-1,-1) | (1,1)  |

**Equilibrios encontrados:**
- Dos equilibrios puros triviales y  
- Un equilibrio mixto: 50% Cara / 50% Cruz para ambos.

**Pago esperado en equilibrio mixto:**  
- Empresa A: 0  
- Empresa B: 0

### Extensión técnica 2: juego asimétrico realista
Escenario donde Empresa A (low-cost) tiene ventajas en precios bajos.

|                  | B bajo | B medio | B alto |
| ---------------- | ------ | ------- | ------ |
| **A bajo**       | (3,2)  | (4,1)   | (5,0)  |
| **A medio**      | (2,3)  | (3,3)   | (4,2)  |
| **A alto**       | (1,4)  | (2,4)   | (3,3)  |

**Equilibrio encontrado:**  
- Estrategia pura (Bajo, Bajo).

## Conclusiones
- Los modelos permiten analizar interacciones estratégicas en escenarios realistas.
- Se muestran situaciones donde el equilibrio es puro y donde solo existe equilibrio mixto.
- El análisis incluye interpretación económica a partir de pagos esperados en equilibrio.

## Uso
El código implementa:
- Definición de juegos bimatriz simétricos y asimétricos
- Cálculo de equilibrios de Nash (puros y mixtos)
- Cálculo de pagos esperados bajo estrategias mixtas

Proyecto reproducible en Google Colab.  
Aplicable a pricing competitivo, diseño de estrategias en mercados oligopolísticos, licitaciones y simulación de reacción de competidores.

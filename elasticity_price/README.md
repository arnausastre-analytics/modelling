# 📈 Elasticidad precio-demanda con datos reales (Online Retail UCI)

## 📝 Contexto del proyecto

Entender cómo responde la demanda al precio es fundamental para cualquier negocio que fije precios de productos o servicios.  
Este proyecto aplica un enfoque clásico de econometría —**elasticidad precio‑demanda**— utilizando datos reales del dataset *Online Retail*, proveniente de un retailer online del Reino Unido :contentReference[oaicite:1]{index=1}. Computamos el grado de sensibilidad de la demanda al precio a partir de información histórica de ventas y precios.

---

## 🎯 Objetivos

✅ Estimar una regresión lineal que modele la relación:  
- El coeficiente β₁ representa la elasticidad precio-demanda.
- Interpretar los resultados según su signo y magnitud.
- Analizar gráficamente esta relación.

---

## 🔧 Herramientas y técnicas

- `pandas` para carga, procesado y agregación del dataset.
- `numpy` para cálculos numéricos.
- `statsmodels` para regresión lineal y análisis estadístico.
- `matplotlib` / `seaborn` para visualización y análisis gráfico.

---

## 📂 Estructura del repositorio

elasticidad_precio_real/
├── README.md <-- Este documento
├── data/
│ └── online_retail.xlsx <-- Dataset original (UCI, 2010–2011)
├── notebook/
│ └── elasticidad_real.ipynb <-- Notebook paso a paso
└── requirements.txt <-- Dependencias del proyecto

yaml
Copiar
Editar

---

## 📥 Origen del dataset

- **Online Retail (UCI ML Repository)**: contiene todas las transacciones entre diciembre 2010 y diciembre 2011 de una tienda online del RU :contentReference[oaicite:2]{index=2}.
- Incluye columnas: InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country.

---

## 🧩 Procesamiento inicial

1. Filtrado legendario de datos:  
   - Quitar transacciones canceladas (InvoiceNo con ‘C’).
   - Filtrar solo país Reino Unido (UK).
   - Quitar valores negativos o erróneos (quantity, unitprice > 0).
2. Agrupar por producto y/o periodo (ej. mensual) para obtener:
   - Precio promedio por unidad  
   - Cantidad vendida total

---

## 📊 Modelado y resultados

- Ajuste de regresión log-log para estimar elasticidad.
- Evaluación con métricas: R², p-values, intervalos de confianza.
- Visualización:
  - Scatter de log(precio) vs log(cantidad) con línea de regresión.  
  - Interpretación del coeficiente β₁:
    - Elasticidad < -1 → demanda elástica
    - Elasticidad entre -1 y 0 → demanda inelástica

---

## 📥 Uso del proyecto

1. Descargar `online_retail.xlsx` y colocarlo en `data/`.
2. Instalar dependencias:
pip install -r requirements.txt

yaml
Copiar
Editar
3. Abrir `elasticidad_real.ipynb` en Jupyter o Colab.
4. Ejecutar sección por sección para reproducir el análisis completo.

---

## 💡 Extensiones posibles

- Estimar elasticidades por categoría de producto o segmento.
- Incluir variables de control: promociones, periodo (meses/estacionalidad).
- Elasticidad cruzada: analizar demanda entre productos relacionados.

---

## 👤 Autor

[Tu nombre]  
*Data Analyst & Business Consultant*  
🔗 [LinkedIn](https://www.linkedin.com) | [GitHub](https://github.com)

---


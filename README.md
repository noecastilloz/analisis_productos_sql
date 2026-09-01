# 🛒 Análisis Exploratorio de Datos e Inventario de Productos (SQL)

![SQL](https://img.shields.io/badge/SQL-SQLite-003B57?logo=sqlite)
![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![JupySQL](https://img.shields.io/badge/JupySQL-Data%20Analysis-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## 📌 Descripción del Proyecto
Este proyecto realiza una evaluación analítica e inspección de inventario sobre un conjunto de datos de **10,000 productos** de comercio electrónico utilizando **SQL (SQLite)** en un entorno interactivo de Google Colab. El objetivo fue transformar datos no estructurados en métricas clave de negocio (KPIs), analizar la distribución de precios por categoría e identificar oportunidades de optimización en el inventario.

---

## 🎯 Preguntas de Negocio Resueltas
- **Estructura del Catálogo:** ¿Cómo se distribuye la variedad de productos entre marcas y categorías principales?
- **Segmentación de Precios:** ¿Cuál es el rango de precios en el catálogo y cómo se agrupan los productos por nivel socioeconómico de compra?
- **Valoración de Inventario:** ¿Cuáles son las categorías con mayor capital inmovilizado ($Stock \times Price$)?
- **Identificación de Anomalías:** ¿Existe algún problema en la disponibilidad reportada del inventario respecto al stock físico en sistema?

---

## 🛠️ Tecnologías Utilizadas
- **Base de Datos & Lenguaje:** SQLite, SQL Standard (`CTEs`, `Window Functions`, `Aggregations`, `CASE WHEN`)
- **Entorno de Ejecución:** Google Colab / Jupyter Notebooks
- **Extensión SQL:** `JupySQL` (`ipython-sql`)
- **Librerías de Apoyo (Python):** `Pandas`, `sqlite3`

---

## 💡 Técnicas SQL Destacadas

### 1. Funciones de Ventana (`DENSE_RANK`)
Para determinar el podio de los productos más costosos por categoría sin reducir el detalle del conjunto de datos, se utilizó `DENSE_RANK()` dividiendo por departamento (`PARTITION BY Category`).

### 2. Expresiones Comunes de Tabla (`CTEs`)
Se empleó la cláusula `WITH` para comparar de forma dinámica el precio individual de cada artículo contra el promedio de su respectiva categoría.

### 3. Agregación y Segmentación por Reglas de Negocio
Uso de `CASE WHEN` para clasificar productos en rangos (*Económico*, *Gama Media*, *Gama Alta*) y cálculo acumulado del valor monetario total en inventario.

---

## 📊 Hallazgos Principales

| Métrica / Consulta | Valor / Resultado | Insight de Negocio |
| :--- | :--- | :--- |
| **Total Catálogo** | 10,000 productos / 9,241 marcas | Amplia variedad de proveedores distribuidos en 34 categorías. |
| **Categoría Líder (Stock)** | *Clothing & Apparel* (174,236 unidades) | Representa el mayor volumen físico de inventario acumulado. |
| **Rango de Precios** | $1.00 USD (Mín) / $999.00 USD (Máx) | Precio promedio global de **$503.37 USD**. |
| **Segmentación** | 5,049 productos en *Gama Alta (> $500)* | Más del 50% de la oferta se concentra en productos de costo elevado. |
| **Valoración Top Inventario** | *Clothing & Apparel* ($87.4M USD) | Concentra la mayor inversión financiera inmovilizada. |
| **Auditoría de Disponibilidad** | ~3,400 productos en `discontinued`/`out_of_stock` | Se detectaron **>1.6 millones de unidades en stock** asociadas a productos descontinuados o sin disponibilidad activa. |

---

## 📂 Estructura del Repositorio

```text
├── Análisis_Productos_SQL.ipynb   # Notebook principal con las consultas SQL
├── products-10000.csv             # Dataset original de productos
└── README.md                      # Documentación del proyecto
```
---

🚀 Visualización y Ejecución
Revisión estática: Explora las consultas SQL y los resultados navegando directamente en el archivo Análisis_Productos_SQL.ipynb.

Ejecución interactiva: Para ejecutar y probar las consultas SQL en la nube sin instalar SQLite localmente, haz clic en el siguiente botón:
https://colab.research.google.com/drive/1w8TNBsAox2ZbT_LKtSmHw74Pk_66gN_a?usp=sharing


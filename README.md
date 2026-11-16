[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rociojuarez/analisis-de-datos-telco-churn/blob/main/notebooks/TPI_Analisis_de_Datos.ipynb)

# 📊 Predicción y Análisis de Cancelación de Clientes (Telco Customer Churn)                                                               
### Trabajo Práctico Integrador (TPI) — Introducción al Análisis de Datos | División: 343 | 
Docente: Enzo Martín Zotti

---
## 👥 Integrantes del Equipo

* **Rocío Juárez**
* **Ezequiel Rodríguez**
* **Germán Roa**
* **Lucas Martín More**

---

## 📋 Descripción del Caso de Negocio

En el sector de las telecomunicaciones, el costo de adquirir un nuevo cliente supera ampliamente al de retener uno existente. Este proyecto aborda el problema del **Churn (tasa de abandono)** sobre una base histórica de **7.043 clientes**, con el objetivo de:

1. **Auditar y depurar** la calidad de los datos crudos (`data/raw`) para eliminar inconsistencias de tipo y valores faltantes ocultos.
2. **Identificar los factores críticos** que impulsan la baja del servicio (tipo de contrato, antigüedad, cargos mensuales, modalidad de pago y servicios adicionales).
3. **Entrenar y evaluar modelos predictivos** (Regresión Lineal y Regresión Logística) capaces de estimar el gasto acumulado y anticipar qué clientes presentan mayor probabilidad de abandono para diseñar campañas de retención focalizadas.

---
## 🛠️ **Stack Tecnológico**
- **Lenguaje:** Python 3
- **Manipulación y Análisis:** Pandas, NumPy
- **Visualización:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-Learn (`LinearRegression`, `LogisticRegression`, `DecisionTreeClassifier`, `ColumnTransformer`, `OneHotEncoder`, `OrdinalEncoder`, `StandardScaler`, `train_test_split`)
- **Entorno:** Google Colaboratory / Jupyter Notebook

## 📊 **Principales Hallazgos y Resultados**

- **Tasa Global de Abandono:** El **26,54%** de los clientes abandonó la compañía (1.869 bajas frente a 5.174 clientes activos).
- **Impacto del Contrato:** Los clientes con contrato **mes a mes (*Month-to-month*)** concentran la inmensa mayoría de las bajas, mientras que los contratos a 1 y 2 años presentan tasas de retención superiores al 88%.
- **Antigüedad (*Tenure*):** El riesgo de fuga es crítico durante los **primeros 12 meses** de relación comercial; pasada esa barrera, la fidelidad aumenta sostenidamente.
- **Desempeño de Modelos:**
  - **Regresión Lineal (`TotalCharges`):** $R^2 = 0.6701$ | $\text{MAE} = \$892.38$.
  - **Regresión Logística (`Churn`):** Exactitud (*Accuracy*) del **80,70%** sobre el conjunto de prueba, superando ampliamente la línea base de clase mayoritaria (73,46%).


## 🗂️ Estructura del Repositorio

```
analisis-de-datos-telco-churn/
├── data/
│   ├── raw/                  # Dataset original de Kaggle, sin modificar
│   └── processed/            # Dataset depurado (telco_churn_limpio.csv), generado por el notebook
├── notebooks/
│   └── TPI_Analisis_de_Datos.ipynb   # Análisis completo (limpieza, EDA y modelado)
├── docs/
│   └── INFORME_EJECUTIVO.pdf # Informe técnico-ejecutivo con carátula
├── requirements.txt          # Dependencias para ejecución local
└── README.md
```

**Cómo explorar el proyecto:** abrir el notebook y recorrerlo en orden. La *Parte 1* cubre fundamentos, ingesta y limpieza; la *Parte 2*, manipulación con Pandas y la exportación a `data/processed`; la *Parte 2B*, el análisis exploratorio y los gráficos; la *Parte 3*, el preprocesamiento y los modelos. El informe resume la metodología y las conclusiones de negocio.

## 🚀 Guía Rápida de Ejecución
Ejecución inmediata en la nube (Recomendado): Hacer clic en el botón Open in Colab al inicio de este documento. El notebook descarga automáticamente los datasets desde la rama main de este repositorio sin requerir configuración manual.

### **Ejecución local**:
git clone [https://github.com/rociojuarez/analisis-de-datos-telco-churn.git](https://github.com/rociojuarez/analisis-de-datos-telco-churn.git)
cd analisis-de-datos-telco-churn
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook notebooks/TPI_Analisis_de_Datos.ipynb

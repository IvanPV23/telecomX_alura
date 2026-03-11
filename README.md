# 📡 TelecomX — Análisis de Churn de Clientes

## 📋 Descripción del Proyecto

Este proyecto forma parte del **TelecomX Challenge** y tiene como objetivo aplicar un proceso completo de **ETL (Extract, Transform, Load)** sobre datos de clientes de una empresa de telecomunicaciones, con el fin de analizar los patrones de **churn** (abandono de clientes) y generar insights accionables.

---

## 🎯 Objetivo

Identificar los factores que influyen en la cancelación del servicio por parte de los clientes, a través del análisis de variables demográficas, de comportamiento y de contratación, apoyándonos en visualizaciones y estadísticas descriptivas.

---

## 🗂️ Estructura del Repositorio

```
TelecomX_Challenge/
│
├── TelecomX_book.ipynb          # Notebook principal con el proceso ETL completo
├── TelecomX_diccionario.md      # Diccionario de datos del proyecto
├── TelecomX_data.json           # Dataset fuente en formato JSON (obtenido de la API)
└── README.md                    # Este archivo
```

---

## 🔄 Proceso ETL

### 📌 1. Extracción
- Carga del dataset desde la API oficial de TelecomX (formato JSON anidado).
- Exploración inicial de la estructura del JSON y sus campos anidados (`customer`, `phone`, `internet`, `account`).

### 🔧 2. Transformación
- **Normalización**: aplanamiento del JSON anidado a un DataFrame tabular con `pd.json_normalize`.
- **Limpieza de datos**:
  - Conversión de `Charges.Total` de string a float.
  - Tratamiento de valores nulos y vacíos.
  - Estandarización de valores categóricos.
  - Creación de columna `Churn_bin` (0/1) para análisis numérico.
- **Feature Engineering**: cálculo de métricas derivadas (cargos diarios, segmentación por tenure).

### 📊 3. Carga y Análisis
- Exportación del DataFrame limpio a CSV.
- Análisis exploratorio de datos (EDA):
  - Distribución de churn general.
  - Análisis por variables demográficas (género, edad, dependientes).
  - Análisis por tipo de contrato y método de pago.
  - Análisis de cargos mensuales y totales.
  - Correlaciones entre variables y churn.
- Visualizaciones con `matplotlib` y `seaborn`.

### 📄 4. Informe Final
- Conclusiones y hallazgos principales.
- Perfil del cliente con mayor riesgo de churn.
- Recomendaciones estratégicas para reducir la tasa de abandono.

---

## 🛠️ Tecnologías Utilizadas

| Herramienta | Uso |
|-------------|-----|
| `Python 3.x` | Lenguaje principal |
| `pandas` | Manipulación y transformación de datos |
| `matplotlib` | Visualización de datos |
| `seaborn` | Visualización estadística |
| `requests` | Extracción de datos desde la API |
| `json` | Parsing del formato JSON |
| `Jupyter Notebook` | Entorno de desarrollo interactivo |

---

## 📊 Principales Hallazgos

- Los clientes con contrato **mensual (Month-to-month)** tienen la mayor tasa de churn.
- El servicio de **Fiber Optic** presenta mayor abandono que DSL.
- Clientes con menos de **12 meses de tenure** son los más propensos a cancelar.
- El pago mediante **Electronic check** está asociado a mayor churn.
- Clientes sin **pareja ni dependientes** presentan mayor tasa de abandono.

---

## 🚀 Cómo Ejecutar

1. Clona este repositorio:
   ```bash
   git clone https://github.com/tuusuario/telecomx-challenge.git
   cd telecomx-challenge
   ```

2. Instala las dependencias:
   ```bash
   pip install pandas matplotlib seaborn requests jupyter
   ```

3. Abre el notebook:
   ```bash
   jupyter notebook TelecomX_book.ipynb
   ```

4. Ejecuta las celdas en orden desde la sección de **Extracción** hasta el **Informe Final**.

---

## 📌 Fuente de Datos

Los datos son obtenidos desde la API oficial del desafío:


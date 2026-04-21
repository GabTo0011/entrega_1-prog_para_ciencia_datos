# entrega_1-prog_para_ciencia_datos
# 📊 Proyecto: Limpieza y Preprocesamiento de Datos de Urgencias Respiratorias en Chile

## 🧾 Descripción del Proyecto

Este proyecto tiene como objetivo analizar, limpiar y transformar un dataset real de **urgencias respiratorias en Chile (2023–2025)**, con el fin de mejorar la calidad de los datos y prepararlos para análisis exploratorio y modelamiento.

El dataset contiene información relevante a nivel:
- Geográfico (región, comuna)
- Institucional (servicio de salud, establecimiento)
- Clínico (causa, prioridad de triage)
- Demográfico (edad, sexo)
- Económico (costo de atención)

Dado que los datos originales presentan **valores faltantes, duplicados, inconsistencias y outliers**, se desarrolló un proceso completo de **preprocesamiento de datos**, aplicando buenas prácticas de ciencia de datos.

---

## 🎯 Objetivos

### Objetivo General
Preparar un dataset limpio, consistente y estructurado para su análisis y posible uso en modelos predictivos.

### Objetivos Específicos
- Identificar problemas de calidad de datos (nulos, duplicados, ruido, outliers).
- Aplicar técnicas de limpieza y transformación.
- Implementar un pipeline reproducible de preprocesamiento.
- Generar visualizaciones para el análisis de datos.

---

## 🧱 Estructura del Proyecto
```text
📁 proyecto-urgencias
│
├── 📁 data
│   ├── raw/
│   │   └── urgencias_noprocesados_grupo02.csv
│   └── processed/
│       └── datos_limpios.csv
│
├── 📁 notebooks
│   ├── entrega/
│   │   ├── graficos.ipynb
│   │   ├── segundo.trimestre.ipynb
│   │   └── notebook_integrado_urgencias_grupo02.ipynb
│   └── borradorres_trabajo/
│       └── (contiene documentos de desarrollo en progreso)
│
├── 📁 scripts
│   └── (Para funciones reutilizables)
│
├── 📁 docs
│   ├── EV PARCIAL 1 SCY1101_ESTUDIANTE.pdf
│   ├── EP-1_ SCY1101_G2_002V.docx
│   └── Formato presentacion evaluacion parcial 1.pptx
│
├── 📁 outputs
│   └── (gráficos generados)
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

## ⚙️ Tecnologías utilizadas

- Python 3.x
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## 🚀 Instrucciones de ejecución

### 1. Clonar el repositorio

```bash
git clone https://github.com/GabTo0011/entrega_1-prog_para_ciencia_datos.git

cd entrega_1-prog_para_ciencia_datos
```
### 2. Crear entorno virtual (recomendado)

python -m venv venv

#### Activar entorno:

Windows:

```bash
venv\Scripts\activate
```

Mac/Linux:

```bash
source venv/bin/activate
```

### 3. Instalar dependencias
usamos requirements.txt
```bash
pip install -r requirements.txt
```

### 4. Ejecutar el proyecto

Abrir Jupyter Notebook:

```bash
jupyter notebook
```

Luego abrir:

```bash
notebooks/notebook_integrado_urgencias_grupo02_pre-listo.ipynb
```

Ejecutar todas las celdas en orden:
```python
Kernel → Restart & Run All
```

## 🔍 Flujo del proyecto

El proyecto sigue el siguiente pipeline:
```mermaid
Datos crudos
   ↓
Diagnóstico (EDA)
   ↓
Limpieza de datos
   ↓
Transformación
   ↓
Feature Engineering
   ↓
Dataset limpio
   ↓
Análisis y visualización
```

## 🧹 Procesos realizados

### 🔹 Diagnóstico inicial
* `df.info()`   : para conocer la estructura del dataset, tipos de datos y valores nulos.
* `df.head()`   : para visualizar las primeras filas del dataset.
* `df.tail()`   : para visualizar las últimas filas del dataset.
* `df.describe()`   : para obtener estadísticas descriptivas de las variables numéricas.
* `df.isna().sum()` : para contar los valores nulos en cada columna.
* `df.dtypes`   : para conocer los tipos de datos de cada columna.
* `df.duplicated().sum()`   : para contar los valores duplicados en el dataset.
### 🔹 Limpieza de datos
* Eliminación de duplicados
* Tratamiento de valores faltantes  
 &ensp;`df.dropna()`   : para eliminar filas con valores nulos.  
 &ensp;`df.fillna()`   : para rellenar valores nulos con un valor específico.  
* Corrección de errores de formato
* Normalización de texto
### 🔹 Transformaciones
* Conversión de tipos de datos
* Normalización de fechas
* Codificación de variables categóricas
* Escalado de variables numéricas
### 🔹 Feature Engineering
* Creación de nuevas columnas
* Transformación de variables existentes
* Agregaciones por región
* Agregaciones por grupo etario
* Agregaciones por sexo
* Interacciones entre variables
* Variables derivadas
### 🔹 Análisis y visualización
* Histograma de la variable NumTotal  
&nbsp;→ Distribución de la cantidad de atenciones de urgencia.  
* Boxplot de la variable CostoAtencionCLP  
&nbsp;→ Detección de outliers y dispersión de los costos.  
* Gráfico de barras de las principales causas respiratorias (Causa)  
&nbsp;→ Identificación de las patologías más frecuentes.  
* Gráfico de barras de la distribución por grupo etario  
&nbsp;→ Comparación de atenciones entre rangos de edad.  
* Gráfico de barras del promedio de atenciones de adultos mayores (Num65oMas) por región (RegionGlosa)  
&nbsp;→ Análisis territorial de la demanda en población envejecida.  
### 🔹 Pipeline

Se implementó un pipeline con:
```Python
Pipeline + ColumnTransformer
```

Esto permite:

* Reproducibilidad  
* Modularidad  
* Evitar data leakage  

## 📊 Resultados obtenidos
* Eliminación de duplicados → mejora de consistencia
* Reducción de valores nulos
* Normalización de variables categóricas
* Identificación de outliers relevantes
* Dataset listo para análisis y modelado

## 📈 Visualizaciones

El proyecto incluye gráficos como:

* Distribución de atenciones (histograma)
* Boxplot de costos
* Top causas respiratorias
* Distribución por grupo etario
* Comparación por región

## 🔁 Reproducibilidad

El proyecto garantiza reproducibilidad mediante:

* Notebook documentado (Markdown + código)
* Uso de pipeline
* Estructura de carpetas clara
* Posibilidad de versionamiento con Git

## 🧠 Aprendizajes clave
* La limpieza de datos es crítica antes de cualquier análisis.
* Los outliers pueden representar información valiosa.
* La estandarización evita errores analíticos.
* Un pipeline asegura consistencia en el procesamiento.

## 📌 Posibles mejoras futuras
* Implementar modelos predictivos (clasificación/regresión)
* Aplicar técnicas de reducción de dimensionalidad (PCA)
* Automatizar el pipeline en scripts
* Integrar dashboard (Power BI / Streamlit)

## 👨‍💻 Autor(es)
* Daniela Zarate
* Gabriel Toledo

## 🤝👨‍💻👩‍💻 Conclusión como equipo

El proyecto lo desarrollamos de manera colaborativa, coincidiendo horarios de 
trabajo, complementando experiencias, organizar una división de tareas y 
intentar optimizar tiempos de desarrollo. La comunicación constante nos 
facilitó la toma de decisiones y validación de resultados, logrando un 
análisis más completo y robusto. El trabajo en equipo fue clave para asegurar 
la calidad y coherencia del proceso de limpieza y preprocesamiento de datos.
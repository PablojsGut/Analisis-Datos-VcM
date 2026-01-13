# Proyecto de Análisis de Datos y Modelamiento VcM (Vinculación con el Medio)

Este repositorio contiene el flujo de trabajo completo para el análisis de iniciativas y participaciones externas. El proyecto abarca desde la extracción y limpieza de datos (ETL) hasta la implementación de modelos de Machine Learning (Regresión Logística, Lineal y Clustering).

## 🚀 Estructura del Proyecto

El análisis se divide en cuatro cuadernos de Jupyter que deben ejecutarse en orden según el flujo de datos:

### 1. ETL: Participaciones Externas (`1.- etl.ipynb`)
**Propósito:** Limpieza y normalización de los datos crudos obtenidos del formulario de participaciones externas.
- Lectura de archivos Excel.
- Normalización de nombres de columnas y tipos de datos.
- Exportación del dataset limpio a la carpeta `db/` para su uso en modelos posteriores.

### 2. Predicción de Actividades: Regresión Logística (`2.- regresion_logistica.ipynb`)
**Propósito:** Clasificar si una actividad será "Larga" o "Corta" basada en los datos procesados en el paso 1.
- Uso de `MinMaxScaler` para normalizar variables cuantitativas.
- Entrenamiento de un modelo de **Regresión Logística**.
- Evaluación mediante Matriz de Confusión y reporte de clasificación (Accuracy, Precision, Recall).

### 3. Análisis de Iniciativas VcM: Regresión Dual (`3.- regresion_lineal-logistica.ipynb`)
**Propósito:** Modelar el rendimiento (notas) y el estado de las iniciativas generales.
- **Regresión Lineal:** Para predecir el puntaje/nota final de las iniciativas.
- **Regresión Logística:** Para predecir el estado de la iniciativa (ej. Enviada vs. En creación).
- Visualización de curvas ROC y análisis de residuos.

### 4. Segmentación de Iniciativas: Clustering (`4.- clustering.ipynb`)
**Propósito:** Agrupar iniciativas automáticamente según comportamientos similares.
- Implementación de **K-Means**.
- Determinación automática de grupos mediante **Método del Codo** y **Puntaje de Silueta**.
- Perfilamiento de clusters identificando variables diferenciadoras únicas por grupo.

---

## 🛠️ Requisitos e Instalación

Este proyecto utiliza un entorno virtual de Python (`.venv`) para gestionar las dependencias.

### Instalación para usuarios
1. **Clonar el repositorio:**
   ```powershell
   git clone <url-del-repositorio>
   cd <nombre-del-repositorio>

2. **Crear y activar el entorno virtual:**
    ```powershell
    python -m venv .venv
    .venv\Scripts\Activate

3. **Instalar dependencias:**
    ```powershell
    pip install -r requirements.txt

---

## 📂 Organización de Carpetas
- `/`: Archivos `.ipynb` principales.
- `db/`: Carpeta (ignorada en Git) donde se almacenan los datasets crudos y los resultados de los procesos ETL.
- `.venv/`: Entorno virtual de Python (ignorado en Git).

---

## 📊 Tecnologías Utilizadas
- **Pandas & Numpy**: Manipulación de datos.
- **Scikit-Learn**: Modelos de Machine Learning y preprocesamiento.
- **Matplotlib & Seaborn**: Visualización de datos.
- **Openpyxl**: Lectura y escritura de archivos Excel.

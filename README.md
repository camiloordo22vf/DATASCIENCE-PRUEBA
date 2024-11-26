# 🍷 Proyecto 1: **Wine Classification Project**

Este proyecto clasifica variedades de uva utilizando el **Wine Dataset** de la UCI Machine Learning Repository. Se analizaron características químicas y visuales de vinos, y se evaluaron varios modelos de clasificación para determinar el mejor clasificador.

## 📋 Descripción del Proyecto

El objetivo fue identificar la variedad de uva de los vinos utilizando técnicas de Machine Learning. Se probaron y compararon tres modelos:

- **Random Forest**
- **K-Nearest Neighbors (KNN)**
- **Support Vector Machine (SVM)**

El mejor modelo se seleccionó con base en métricas de evaluación registradas en MLflow.

## 📂 Estructura del Proyecto

- **data/**: Contiene el dataset del proyecto en formato CSV.
- **notebooks/**: Notebook principal con el análisis, preprocesamiento y entrenamiento de los modelos.
- **mlflow/**: Experimentos registrados en MLflow.
- **plots/**: Gráficas generadas durante el análisis y la comparación de modelos.

## 🛠 Pasos Realizados

### 1. **Carga del Dataset**
- Descarga del dataset desde el repositorio UCI.
- Carga en un DataFrame utilizando pandas.

### 2. **Análisis Exploratorio de Datos (EDA)**
- Verificación de datos nulos o faltantes.
- Análisis de correlación entre las características del dataset.
- Generación de gráficas para explorar relaciones entre variables.

### 3. **Preprocesamiento**
- Normalización de los datos para mejorar el rendimiento de los modelos.
- División en conjuntos de entrenamiento y prueba (80%-20%).

### 4. **Creación de Experimento en MLflow**
- Configuración de un experimento para registrar métricas y modelos.
- Registro de los resultados de cada algoritmo evaluado.

### 5. **Entrenamiento de Modelos**
Se implementaron y evaluaron los siguientes algoritmos:
- **Random Forest**: Modelo robusto para datos no lineales.
- **KNN**: Basado en la distancia entre puntos.
- **SVM**: Modelo que busca maximizar la separación entre clases.

### 6. **Evaluación y Comparación**
- Métricas calculadas: Accuracy, Precision, Recall y F1-score.
- Registro de resultados en MLflow.
- Gráficas comparativas para facilitar la selección del mejor modelo.

### 7. **Predicción en Nuevas Muestras**
Se probaron los modelos en dos muestras nuevas de vino para verificar su efectividad.

## 📊 Resultados

| Modelo       | Accuracy | Precision | Recall | F1-score |
|--------------|----------|-----------|--------|----------|
| **Random Forest** | 0.981 | 0.983     | 0.981  | 0.982    |
| **KNN**          | 0.963 | 0.966     | 0.963  | 0.964    |
| **SVM**          | 0.985 | 0.988     | 0.985  | 0.986    |

### 🔑 **Mejor Modelo: SVM**
**Razón**: Mayor rendimiento en todas las métricas evaluadas.

## 📈 Visualización

Se generaron gráficos comparativos de métricas para identificar el modelo óptimo.

## 🔧 Requisitos Previos

- **Python 3.9** o superior.
- Librerías necesarias:
  - `pandas`
  - `numpy`
  - `seaborn`
  - `matplotlib`
  - `sklearn`
  - `mlflow`

- **MLflow** configurado para registrar experimentos.

## 🚀 Instrucciones de Uso

1. **Clonar el repositorio:**

   ```bash
   git clone https://github.com/camiloordo22vf/wine-classification.git
   cd wine-classification
✍️ **Conclusión**

El modelo SVM fue identificado como el mejor clasificador para este problema, gracias a su rendimiento superior en precisión, recall y F1-score. Este proyecto demuestra cómo utilizar técnicas de Machine Learning para resolver problemas de clasificación y cómo registrar experimentos para garantizar la trazabilidad y reproducibilidad.

**Artefactos:**

[Modelo SVM](dbfs:/databricks/mlflow-tracking/2551573669228961/2584c9e481824fdb86e456d584417159/artifacts/svm_model)

---

## Proyecto 2: Automatización de la Revisión de Perfiles de Hojas de Vida (CVs)

Este proyecto implementa un modelo de inteligencia artificial basado en técnicas de procesamiento del lenguaje natural (NLP) y modelos de lenguaje grandes (LLMs) para automatizar la revisión de hojas de vida (CVs). El sistema extrae información clave de los CVs y genera un conjunto de datos en formato JSON con los resultados y la precisión de la extracción.

### **Características Principales**

#### Extracción de Información Clave:
- Nombre completo del candidato.
- Email o teléfono de contacto.
- Número total de años de experiencia profesional.
- Indicación de formación en inteligencia artificial (S/N).

#### Generación de Resultados:
- Resultados organizados en formato JSON.
- Incluye un puntaje de precisión para cada campo extraído.
- Valores nulos y puntaje cero (0) en caso de datos faltantes.

#### Uso de Técnicas NLP:
- Extracción basada en patrones y modelos de lenguaje.
- Evaluación de precisión para cada campo extraído.

---

### **Requisitos**

#### Entorno:
- Python 3.8+

#### Librerías:
- `re` (expresiones regulares para extracción de patrones).
- `json` (para manejo y generación de datos JSON).

#### Instalación de Dependencias:
Ejecutar el siguiente comando para instalar dependencias si se utilizan librerías adicionales:


pip install -r requirements.txt
## 📑 Pasos Realizados

### 📝 **Procesamiento de Hojas de Vida:**
Se procesan las hojas de vida utilizando la función `process_cv`, que extrae la información requerida y organiza los resultados en un diccionario.

### 🕵️‍♂️ **Extracción de Información:**
Para cada hoja de vida:
- **Nombre Completo:** Extraído mediante patrones de texto comunes.
- **Email y Teléfono:** Identificados con expresiones regulares.
- **Experiencia Profesional:** Detectada en años.
- **Formación en IA:** Determinada con base en palabras clave.

### 🗂️ **Generación de Resultados:**
Los resultados de cada hoja de vida se estructuran en un diccionario y se guardan en un archivo `output.json`.

#### Ejemplo del formato:


{
    "cv_id": "CV_1",
    "name": "John Doe",
    "email": "johndoe@example.com",
    "phone": "+123456789",
    "years_of_experience": 5,
    "ai_training": "Yes",
    "scores": {
        "name": 1.0,
        "email": 1.0,
        "phone": 1.0,
        "years_of_experience": 1.0,
        "ai_training": 1.0
    }
}

## ⚠️ **Manejo de Errores:**
En caso de no poder extraer un valor, se asigna `null` y un puntaje de `0.0`.

---

## 🚀 **Ejecución del Proyecto**

1. **📥 Agregar las hojas de vida:** Colocar los textos de los CVs en una lista.
2. **💻 Ejecutar el Script:** Correr el archivo Python principal:

   
   python process_cvs.py
## ✅ **Resultados:**
Verificar el archivo `output.json` generado.

---

## 📸 **Capturas de Pantalla:**
- **Resultado JSON Generado:**
- **Procesamiento en Consola:**

---

## 📊 **Conclusiones**

### ✅ **Precisión del Modelo:**
El sistema logra extraer correctamente la mayoría de los datos clave de los CVs. Los resultados incluyen un puntaje que indica la precisión en cada campo.

### 🧠 **Lecciones Aprendidas:**
- La preparación de datos es crítica para mejorar la precisión.
- Documentar errores ayuda a reducir la deuda técnica.

---

## 📧 **Contacto**
- **Email:** [ccoq2013@gmail.com](mailto:ccoq2013@gmail.com)
- **GitHub:** [Cristian Ordoñez]

---

## 🚀 **Ejecución del Proyecto**

1. **📥 Agregar las hojas de vida:** Colocar los textos de los CVs en una lista.
2. **💻 Ejecutar el Script:** Correr el archivo Python principal:

   
   python process_cvs.py


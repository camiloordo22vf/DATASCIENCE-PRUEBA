🍷 Wine Classification Project

Este proyecto clasifica variedades de uva utilizando el Wine Dataset de la UCI Machine Learning Repository. Se analizaron características químicas y visuales de vinos, y se evaluaron varios modelos de clasificación para determinar el mejor clasificador.

📋 Descripción del Proyecto

El objetivo fue identificar la variedad de uva de los vinos utilizando técnicas de Machine Learning. Se probaron y compararon tres modelos:

Random Forest
K-Nearest Neighbors (KNN)
Support Vector Machine (SVM)

El mejor modelo se seleccionó con base en métricas de evaluación registradas en MLflow.

📂 Estructura del Proyecto

data/: Contiene el dataset del proyecto en formato CSV.
notebooks/: Notebook principal con el análisis, preprocesamiento y entrenamiento de los modelos.
mlflow/: Experimentos registrados en MLflow.
plots/: Gráficas generadas durante el análisis y la comparación de modelos.

🛠 Pasos Realizados

1. Carga del Dataset
Descarga del dataset desde el repositorio UCI.
Carga en un DataFrame utilizando pandas.
2. Análisis Exploratorio de Datos (EDA)
Verificación de datos nulos o faltantes.
Análisis de correlación entre las características del dataset.
Generación de gráficas para explorar relaciones entre variables.
3. Preprocesamiento
Normalización de los datos para mejorar el rendimiento de los modelos.
División en conjuntos de entrenamiento y prueba (80%-20%).
4. Creación de Experimento en MLflow
Configuración de un experimento para registrar métricas y modelos.
Registro de los resultados de cada algoritmo evaluado.
5. Entrenamiento de Modelos
Se implementaron y evaluaron los siguientes algoritmos:

Random Forest: Modelo robusto para datos no lineales.
KNN: Basado en la distancia entre puntos.
SVM: Modelo que busca maximizar la separación entre clases.
6. Evaluación y Comparación
Métricas calculadas: Accuracy, Precision, Recall y F1-score.
Registro de resultados en MLflow.
Gráficas comparativas para facilitar la selección del mejor modelo.
7. Predicción en Nuevas Muestras
Se probaron los modelos en dos muestras nuevas de vino para verificar su efectividad.

📊 Resultados

Modelo	Accuracy	Precision	Recall	F1-score

Random Forest
0.981	0.983	0.981	0.982

KNN
0.963	0.966	0.963	0.964

SVM	
0.985	0.988	0.985	0.986

🔑 Mejor Modelo: SVM

Razón: Mayor rendimiento en todas las métricas evaluadas.

📈 Visualización

Se generaron gráficos comparativos de métricas para identificar el modelo óptimo.

🔧 Requisitos Previos

Python 3.9 o superior.
Librerías necesarias: pandas, numpy, seaborn, matplotlib, sklearn, mlflow.
MLflow configurado para registrar experimentos.

🚀 Instrucciones de Uso

Clonar el repositorio:

bash
Copiar código
git clone https://github.com/camiloordo22vf/wine-classification.git
cd wine-classification
Instalar dependencias:

bash
Copiar código
pip install -r requirements.txt
Ejecutar el Notebook:
Abra el archivo notebooks/Wine_Classification.ipynb y ejecute las celdas paso a paso.

Revisar experimentos en MLflow:
Ejecute el siguiente comando para iniciar la interfaz de MLflow:

bash
Copiar código
mlflow ui
✍️ Conclusión

El modelo SVM fue identificado como el mejor clasificador para este problema, gracias a su rendimiento superior en precisión, recall y F1-score. Este proyecto demuestra cómo utilizar técnicas de Machine Learning para resolver problemas de clasificación y cómo registrar experimentos para garantizar la trazabilidad y reproducibilidad.

📧 Contacto
Si tienes preguntas o sugerencias, no dudes en contactarme:
Email: ccoq2013@gmail.com
GitHub: Cristian Ordoñez

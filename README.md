# AG News Text Classifier

## 1. Descripción del proyecto

Este proyecto implementa un sistema de clasificación automática de noticias utilizando técnicas de **Machine Learning** y **Procesamiento de Lenguaje Natural (NLP)**.

El objetivo es desarrollar, entrenar y evaluar modelos capaces de asignar noticias a diferentes categorías temáticas a partir de su contenido textual.

El proyecto utiliza el conjunto de datos **AG News** y aborda un problema de clasificación multiclase.

## 2. Categorías de clasificación

El problema contempla cuatro categorías:

- `Business`: negocios y economía.
- `Sci_Tech`: ciencia y tecnología.
- `Sports`: deportes.
- `World`: noticias internacionales.

## 3. Dataset

Se utilizan dos archivos CSV:

- `ag_news_train.csv`: conjunto de entrenamiento.
- `ag_news_test.csv`: conjunto de prueba.

Distribución del conjunto de datos:

| Conjunto | Registros | Distribución |
|---|---:|---|
| Entrenamiento | 8.000 | 2.000 por categoría |
| Prueba | 2.000 | 500 por categoría |

El conjunto de prueba se reserva para la evaluación final de los modelos, evitando utilizarlo durante el entrenamiento.

## 4. Tecnologías utilizadas

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- SpaCy
- PyTorch
- Jupyter Notebook
- Google Colab
- PyCharm
- Git y GitHub

## 5. Estructura del repositorio

```text
ag-news-text-classifier/
│
├── data/
│   ├── raw/
│   │   ├── ag_news_train.csv
│   │   └── ag_news_test.csv
│   │
│   └── processed/
│
├── notebooks/
│   └── ag_news_text_classifier.ipynb
│
├── src/
│
├── results/
│   ├── figures/
│   └── metrics/
│
├── README.md
├── requirements.txt
└── .gitignore
```

### Descripción de directorios

- `data/raw/`: contiene los archivos originales del conjunto de datos.
- `data/processed/`: destinado a almacenar los datos procesados.
- `notebooks/`: contiene los notebooks utilizados durante el desarrollo y experimentación.
- `src/`: reservado para futuras funciones y módulos reutilizables del proyecto.
- `results/figures/`: almacena gráficos y matrices de confusión.
- `results/metrics/`: almacena informes y resultados de evaluación.

## 6. Desarrollo del proyecto

El desarrollo contempla las siguientes etapas:

1. Carga y exploración del conjunto de datos.
2. Limpieza y normalización del texto.
3. Tokenización y procesamiento lingüístico.
4. Análisis de frecuencias y extracción de n-gramas.
5. Representación textual mediante TF-IDF.
6. Entrenamiento de modelos de Machine Learning.
7. Evaluación y comparación de resultados.
8. Análisis de errores de clasificación.

Entre los modelos experimentados se incluyen:

- Regresión Logística.
- Random Forest.
- LinearSVC.
- ComplementNB.
- Modelos de redes neuronales recurrentes, como LSTM y GRU.

## 7. Evaluación y resultados

Se utilizan herramientas de Scikit-learn para analizar el rendimiento de los modelos.

Los recursos de evaluación incluyen:

- Accuracy.
- Precision.
- Recall.
- F1-score.
- Classification Report.
- Matriz de confusión.
- Análisis de errores de clasificación.

### Checkpoint: ComplementNB

Como parte de los experimentos iniciales se evaluó un clasificador ComplementNB utilizando características TF-IDF.

Configuración principal:

- Vectorización: TF-IDF.
- `max_features=20000`.
- `ngram_range=(1, 2)`.
- `min_df=2`.
- `max_df=0.95`.
- Modelo: ComplementNB.
- `alpha=0.5`.

Resultados obtenidos sobre el conjunto de prueba:

| Métrica | Resultado |
|---|---:|
| Accuracy | 0.8960 |
| Macro Precision | 0.8957 |
| Macro Recall | 0.8960 |
| Macro F1-score | 0.8957 |
| Weighted F1-score | 0.8957 |

El modelo obtuvo 1.792 predicciones correctas sobre 2.000 registros de prueba.

Estos resultados constituyen un punto de referencia para las siguientes etapas de experimentación y comparación.

## 8. Instalación

### Clonar el repositorio

```bash
git clone https://github.com/Kanon2212/ag-news-text-classifier.git

cd ag-news-text-classifier
```

### Crear un entorno virtual (recomendado)

```bash
python -m venv .venv
```

Activar el entorno virtual en Windows:

```bash
.venv\Scripts\activate
```

### Instalar las dependencias

```bash
python -m pip install -r requirements.txt
```

Si se utiliza SpaCy con su modelo de inglés, instalarlo mediante:

```bash
python -m spacy download en_core_web_sm
```

## 9. Ejecución del proyecto

El proyecto utiliza dos entornos complementarios:

**Google Colab**
- Desarrollo inicial de los notebooks.
- Experimentación con técnicas de NLP y Machine Learning.
- Entrenamiento y evaluación de modelos.

**PyCharm**
- Ejecución local de los notebooks.
- Organización de archivos y estructura del repositorio.
- Administración de dependencias y entorno Python.
- Control de versiones mediante Git.
- Publicación de avances en GitHub.

Para ejecutar localmente el proyecto, abrir el repositorio desde PyCharm, configurar el intérprete Python correspondiente y ejecutar el notebook ubicado en `notebooks/`.

Los resultados generados se organizan dentro del directorio `results/`.

## 10. Estado del proyecto

El proyecto se encuentra en desarrollo y contempla la ampliación progresiva de los experimentos, la comparación de modelos y el análisis de sus resultados.

La estructura del repositorio permite separar los datos, los notebooks, el código reutilizable y los resultados experimentales, facilitando su mantenimiento y evolución.
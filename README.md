# Modelo de aprobación crediticia con Machine Learning

Proyecto académico de clasificación binaria desarrollado con Python y Scikit-learn para analizar la preparación de datos y la construcción de un pipeline reproducible aplicado a la aprobación de créditos para microemprendedores.

El proyecto integra el preprocesamiento de variables numéricas y categóricas con un modelo de Regresión Logística, evitando aplicar transformaciones manuales por separado y reduciendo el riesgo de fuga de información durante la validación.

## Problema

El objetivo es estimar si una solicitud puede clasificarse como **aprobada** o **no aprobada** a partir de variables financieras y demográficas.

Las variables empleadas por el pipeline son:

- Edad.
- Ingreso mensual.
- Deuda actual.
- Región.
- Género.

La variable objetivo es `credito_aprobado`.

## Enfoque metodológico

1. Carga e inspección de los datos.
2. Separación entre variables predictoras y variable objetivo.
3. Identificación de variables numéricas y categóricas.
4. Estandarización de variables numéricas con `StandardScaler`.
5. Codificación de variables categóricas con `OneHotEncoder`.
6. Integración del preprocesamiento mediante `ColumnTransformer`.
7. Construcción de un `Pipeline` con Regresión Logística.
8. Evaluación mediante validación cruzada estratificada de cinco particiones.
9. Interpretación de `accuracy` y `F1 macro`.
10. Entrenamiento final del pipeline y ejemplo ilustrativo de predicción.

## Resultados del notebook

| Métrica de validación | Promedio | Desviación estándar |
|---|---:|---:|
| Accuracy | 93,60 % | 1,85 % |
| F1 macro | 93,13 % | 2,08 % |

Estos resultados corresponden a la ejecución registrada en el notebook sobre un conjunto de **500 observaciones**.

Se utiliza **F1 macro** como métrica principal de interpretación porque evalúa las dos clases con la misma importancia. Esto resulta especialmente relevante en un problema crediticio, donde aprobar una solicitud de mayor riesgo y rechazar una solicitud viable representan errores con consecuencias diferentes.

> Los resultados pertenecen a un ejercicio académico y no representan el desempeño de un sistema crediticio en producción.

## Valor para el negocio

Este proyecto demuestra cómo construir una base técnica reproducible para apoyar el análisis de solicitudes de crédito:

- Aplica el mismo preprocesamiento durante el entrenamiento y las predicciones.
- Reduce el riesgo de fuga de información al mantener las transformaciones dentro del pipeline.
- Evalúa el modelo en diferentes particiones de los datos.
- Considera el equilibrio entre las clases mediante F1 macro.
- Facilita la incorporación futura de métricas relacionadas con el costo de los falsos positivos y falsos negativos.

El modelo funciona como demostración técnica y no sustituye las políticas de riesgo, validaciones regulatorias ni evaluaciones humanas requeridas en una aplicación financiera real.

## Tecnologías utilizadas

- Python.
- Pandas.
- Scikit-learn.
- Jupyter Notebook.
- `Pipeline`.
- `ColumnTransformer`.
- `StandardScaler`.
- `OneHotEncoder`.
- Regresión Logística.
- `StratifiedKFold`.
- Validación cruzada.

## Estructura actual

```text
modelo-crediticio-machine-learning/
├── modelo_crediticio_machine_learning.ipynb
├── loan_sanction_train.csv
├── loan_sanction_test.csv
└── README.md
```

## Ejecución

1. Clona el repositorio:

```bash
git clone https://github.com/oreon36/modelo-crediticio-machine-learning.git
cd modelo-crediticio-machine-learning
```

2. Abre el notebook:

```bash
jupyter notebook modelo_crediticio_machine_learning.ipynb
```

3. Verifica que el dataset requerido por el notebook esté disponible en la ruta indicada antes de ejecutar todas las celdas.

## Mejoras previstas

- Unificar el notebook y los archivos de datos disponibles en el repositorio.
- Añadir un archivo `requirements.txt`.
- Incorporar matriz de confusión, precisión y recall por clase.
- Documentar el origen y el diccionario del dataset.
- Comparar la Regresión Logística con otros algoritmos de clasificación.
- Analizar el costo de los distintos tipos de error.
- Separar el código de entrenamiento, evaluación y predicción.

## Autor

**Héctor López**  
Estudiante de Técnico en Data Science, orientado a Análisis de Datos, Business Intelligence y Control de Gestión.

- [LinkedIn](https://www.linkedin.com/in/hector87)
- [GitHub](https://github.com/oreon36)

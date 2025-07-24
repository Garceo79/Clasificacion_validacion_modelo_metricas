# Clasificación: Validación de Modelos y Métricas de Evaluación

Este proyecto tiene como objetivo automatizar el proceso de detección de pacientes con diabetes en un laboratorio de diagnóstico, utilizando técnicas de clasificación con aprendizaje automático.

## Descripción del Proyecto

Actualmente, el análisis de pacientes se realiza de forma manual, lo que consume mucho tiempo y es impreciso. Nuestra tarea es desarrollar un modelo de clasificación que identifique a los pacientes con y sin diabetes basándose en datos proporcionados por el laboratorio.

## Datos

El conjunto de datos utilizado en este proyecto se encuentra en el archivo `diabetes.csv`. Contiene información relevante de los pacientes, incluyendo métricas como glicemia, presión sanguínea, grasa subcutánea, insulina e IMC, además de una columna indicando si el paciente tiene diabetes o no.

## Análisis y Modelado

El proyecto sigue los siguientes pasos:

1.  **Lectura y Separación de Datos**: Se cargan los datos y se dividen en variables explicativas (X) y variable objetivo (y), que es la columna 'diabetes'.
2.  **Creación de Modelos Iniciales**: Se crean dos modelos de clasificación iniciales: un Árbol de Decisión y un Bosque Aleatorio.
3.  **Validación de Modelos**: Se dividen los datos en conjuntos de entrenamiento, validación y prueba para evaluar la capacidad de generalización de los modelos.
4.  **Evaluación de Modelos**: Se utilizan métricas como la matriz de confusión, exactitud, precisión, sensibilidad (recall) y F1-score para evaluar el rendimiento de los modelos.
5.  **Curvas ROC y Precision-Recall**: Se visualizan estas curvas para comprender el rendimiento de los modelos en diferentes umbrales de decisión.
6.  **Validación Cruzada**: Se aplica KFold y StratifiedKFold para una evaluación más robusta de los modelos, calculando intervalos de confianza para las métricas. Se explora también el método LeaveOneOut para conjuntos de datos pequeños.
7.  **Balanceo de Datos**: Se analiza el desbalanceo en la variable objetivo y se aplican técnicas de balanceo como Oversampling (SMOTE), Undersampling (NearMiss) y combinaciones para mejorar el rendimiento del modelo, utilizando pipelines para evitar el sobreajuste durante la validación cruzada.
8.  **Prueba del Modelo Final**: Se selecciona el modelo con mejor rendimiento (Bosque Aleatorio con undersampling en este caso) y se evalúa en el conjunto de datos de prueba no visto anteriormente.

## Resultados

Se presenta un informe detallado de las métricas obtenidas con los modelos, incluyendo las matrices de confusión y los informes de clasificación. Se discute el rendimiento de cada modelo y el impacto de las técnicas de balanceo de datos.

La evaluación final en el conjunto de prueba del modelo de Bosque Aleatorio con undersampling mostró una exactitud del 70%. La precisión y recall para las clases 'No Diabetes' y 'Diabetes' se analizaron en detalle, indicando la necesidad de posibles mejoras para lograr un balance más equitativo en la clasificación.

## Conclusión

El modelo desarrollado es un primer paso para automatizar la detección de diabetes, con un desempeño aceptable pero con margen de mejora. Se destaca la importancia de las métricas de evaluación y las técnicas de validación cruzada y balanceo de datos para construir modelos robustos y confiables en problemas de clasificación con clases desbalanceadas. Se recomienda la validación adicional de los resultados positivos de diabetes debido a la precisión del modelo en esta clase.

## Requisitos

Para ejecutar este proyecto, necesitarás tener instaladas las siguientes bibliotecas de Python:

-   pandas
-   scikit-learn
-   seaborn
-   matplotlib
-   imblearn

# Telecom X - Parte 2: Prediccion de Cancelacion (Churn)

Proyecto desarrollado en el programa **Alura LATAM** como parte del **Desafio 3 (final) de la formacion de Base de Datos / Data Science**.

## Descripcion

En este desafio se construye una primera solucion de **Machine Learning** para predecir la cancelacion de clientes (churn) en Telecom X.

La propuesta cubre el ciclo completo inicial de modelado:

- Preparacion y limpieza de datos.
- Codificacion de variables categoricas.
- Normalizacion de variables para modelos sensibles a escala.
- Analisis de correlacion y seleccion de variables relevantes.
- Entrenamiento y comparacion de modelos de clasificacion.
- Evaluacion con metricas de negocio y de ML.
- Interpretacion de resultados y recomendaciones estrategicas de retencion.

## Contexto del desafio

Despues del analisis exploratorio de la Parte 1, el objetivo en esta segunda parte es anticipar que clientes tienen mayor probabilidad de cancelar para habilitar acciones preventivas.

## Objetivos

- Preparar los datos para modelado (tratamiento, encoding, normalizacion).
- Realizar analisis de correlacion y seleccion de variables.
- Entrenar dos o mas modelos de clasificacion.
- Evaluar rendimiento con metricas (accuracy, precision, recall, F1, matriz de confusion).
- Interpretar importancia de variables.
- Entregar una conclusion estrategica enfocada en retencion.

## Estructura del proyecto

- `TelecomX_LATAM.ipynb`: notebook principal con todo el flujo de trabajo.
- `telecomx_latam_limpio.csv`: dataset limpio de entrada para el modelado.

## Flujo realizado en el notebook

1. Carga de datos y revision inicial.
2. Eliminacion de columnas irrelevantes o redundantes.
3. Transformacion de variables binarias (`yes/no` -> `1/0`).
4. Encoding de variables categoricas con `OneHotEncoder`.
5. Escalado con `MinMaxScaler`.
6. Agregado de constante con `add_constant` para preparar escenarios de modelado que requieren intercepto.
7. Analisis de correlacion (matrices de calor y lectura dirigida).
8. Entrenamiento de modelos:
   - DummyClassifier (baseline)
   - RandomForestClassifier
   - KNeighborsClassifier (KNN)
9. Ajuste de hiperparametros con grilla manual.
10. Evaluacion de desempeno e interpretacion de resultados.
11. Conclusiones y propuestas de retencion.

## Principales hallazgos

- El **contrato mes a mes** aparece como uno de los factores con mayor asociacion a cancelacion.
- La **antiguedad del cliente** se relaciona de forma inversa con churn: a mayor antiguedad, menor probabilidad de cancelar.
- Variables como **soporte tecnico** y **seguridad online** se asocian con mayor retencion.
- En terminos de negocio, se prioriza el modelo que mejore la deteccion de clientes en riesgo (recall), aun con cierto costo en falsos positivos.

## Requisitos

- Python 3.10+
- Jupyter Notebook
- Librerias de Python:
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn
  - statsmodels

## Como ejecutar

1. Clona este repositorio.
2. Instala las dependencias necesarias.
3. Abre el notebook `TelecomX_LATAM.ipynb`.
4. Ejecuta las celdas en orden para reproducir el analisis y los resultados.

Ejemplo de instalacion:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels notebook
```

## Resultado esperado

Un pipeline funcional de prediccion de churn y una base de recomendaciones accionables para estrategias de retencion en Telecom X.

## Autor

Proyecto realizado por estudiante de **Alura LATAM** en el marco del **Desafio 3 (final)**.

# Predicción de Recuperación de Oro en el Circuito Metalúrgico

## Problema
En la industria minera, optimizar la recuperación de oro es fundamental para maximizar la eficiencia del proceso y reducir pérdidas.  
El objetivo de este proyecto es desarrollar un modelo de machine learning capaz de predecir la recuperación de oro en distintas etapas del circuito metalúrgico.

---

## Datos
Se utilizaron tres conjuntos de datos:

- Entrenamiento  
- Prueba  
- Dataset completo  

Se verificó la consistencia de los datos mediante el cálculo de la recuperación:

- Error Absoluto Medio (EAM): 9.3×10⁻¹⁵ (prácticamente cero)

Esto confirma que los datos son consistentes y confiables.

Durante el preprocesamiento:

- Se alinearon las características entre entrenamiento y prueba  
- Se eliminaron filas con valores de metales totales menores a 0.1%  
- Se filtraron valores extremos o inválidos  

---

## Análisis Exploratorio
Se analizó la distribución de metales (Au, Ag, Pb y solutos) en diferentes etapas del proceso:

- Rougher output  
  - Media: 67.78%  
  - Desviación estándar: 5.32%  
  - Presencia de valores extremos (<30%)

- Final output  
  - Media: 68.26%  
  - Desviación estándar: 3.09%  
  - Mayor estabilidad  

Hallazgos clave:

- La etapa Rougher presenta mayor variabilidad y posibles anomalías  
- La etapa Final muestra una concentración más estable  
- Se recomienda eliminar valores nulos o extremadamente bajos antes del modelado  

---

## Enfoque
Se entrenaron diferentes modelos de regresión:

- Random Forest Regressor  
- Linear Regression  
- Ridge Regression  

Evaluación mediante validación cruzada (5 folds):

- Random Forest: RMSE = 3.94  
- Linear Regression: RMSE = 5.41  
- Ridge Regression: RMSE = 5.41  

El modelo Random Forest mostró el mejor desempeño.

---

## Resultados

### Rougher Output
- Modelo: Random Forest Regressor  
- Parámetros: n_estimators=50, max_depth=10, min_samples_split=2  
- R²: 0.873  
- RMSE: 2.84  

### Final Output
- Modelo: Random Forest Regressor  
- R²: ~0.87  
- RMSE: ~2.92  
- SMAPE: ~2.50%  

Los gráficos de valores reales vs predichos muestran una buena correspondencia entre las predicciones del modelo y los datos reales.

---

## Conclusión
El modelo Random Forest proporciona predicciones precisas y robustas, superando claramente a los modelos lineales.

La limpieza de datos y la eliminación de valores extremos mejoraron significativamente la estabilidad del modelo.

La etapa final del circuito metalúrgico muestra una mayor estabilidad en la recuperación de oro, lo que valida el comportamiento esperado del proceso.

La métrica SMAPE confirma la precisión relativa del modelo, siendo adecuada para este tipo de problema.

---

## Herramientas y Tecnologías
- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib  
- Seaborn  

---

## Conclusión Clave
Este proyecto demuestra cómo aplicar machine learning en un contexto industrial para optimizar procesos y mejorar la toma de decisiones basada en datos.



---



# Gold Recovery Prediction in a Metallurgical Process

## Problem
In the mining industry, optimizing gold recovery is critical to maximize process efficiency and reduce material losses.  
The goal of this project is to develop a machine learning model capable of predicting gold recovery at different stages of a metallurgical process.

---

## Data
Three datasets were used:

- Training set  
- Test set  
- Full dataset  

Data consistency was verified by recalculating recovery:

- Mean Absolute Error (MAE): 9.3×10⁻¹⁵ (effectively zero)

This confirms that the data is reliable and internally consistent.

During preprocessing:

- Features were aligned between training and test datasets  
- Rows with total metal concentrations below 0.1% were removed  
- Invalid and extreme values were filtered out  

---

## Exploratory Data Analysis
The distribution of metals (Au, Ag, Pb, and others) was analyzed across different stages:

- Rougher output  
  - Mean: 67.78%  
  - Standard deviation: 5.32%  
  - Presence of extreme values (<30%)

- Final output  
  - Mean: 68.26%  
  - Standard deviation: 3.09%  
  - More stable distribution  

Key findings:

- The Rougher stage shows higher variability and potential anomalies  
- The Final stage stabilizes metal concentration  
- Removing null or extremely low values improves model performance  

---

## Approach
Several regression models were trained:

- Random Forest Regressor  
- Linear Regression  
- Ridge Regression  

Model evaluation using 5-fold cross-validation:

- Random Forest: RMSE = 3.94  
- Linear Regression: RMSE = 5.41  
- Ridge Regression: RMSE = 5.41  

Random Forest achieved the best performance.

---

## Results

### Rougher Output
- Model: Random Forest Regressor  
- Parameters: n_estimators=50, max_depth=10, min_samples_split=2  
- R²: 0.873  
- RMSE: 2.84  

### Final Output
- Model: Random Forest Regressor  
- R²: ~0.87  
- RMSE: ~2.92  
- SMAPE: ~2.50%  

The predicted vs actual plots show a strong alignment, indicating good model performance.

---

## Conclusion
The Random Forest model provides accurate and robust predictions, clearly outperforming linear models.

Data cleaning and removal of extreme values significantly improved model stability and consistency.

The final stage of the metallurgical process shows more stable gold recovery, aligning with expected process behavior.

The SMAPE metric confirms the model’s suitability for evaluating relative prediction accuracy in this context.

---

## Tools and Technologies
- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib  
- Seaborn  

---

## Key Takeaway
This project demonstrates how machine learning can be applied in an industrial context to optimize processes and improve data-driven decision-making.

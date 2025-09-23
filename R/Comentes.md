## Pregunta 1
Cuando se estima un modelo LASSO con un valor de λ muy grande, la penalización domina en la optimización. En ese caso, la mayoría de los coeficientes se reducen fuertemente hacia cero e incluso algunos se eliminan por completo, dejando un modelo muy simple. Esto genera un error de entrenamiento alto, porque el modelo no logra capturar bien la señal (underfitting), y también un error de prueba elevado debido a la pérdida de capacidad predictiva. 
Por el contrario, cuando λ es muy pequeño, la penalización casi desaparece y el modelo se aproxima a una regresión de mínimos cuadrados ordinarios. Aquí los coeficientes tienden a ser grandes y pocos se eliminan, por lo que el error de entrenamiento es muy bajo. Sin embargo, el error de prueba aumenta porque el modelo se ajusta demasiado a los datos de entrenamiento, incluyendo el ruido, lo que provoca overfitting. 

## Pregunta 2
La técnica de cross-validation es un método de validación que consiste en dividir la muestra en K subconjuntos o “folds”. En cada iteración, se entrena el modelo con K-1 subconjuntos y se evalúa en el fold que quedó fuera. Este proceso se repite hasta que cada fold haya servido como conjunto de validación, y finalmente se promedian los errores de predicción para estimar el error fuera de muestra. Este es un método suumamente útil en el contexto del machine learning porque permite estimar de manera más confiable la capacidad de generalización del modelo. Además, ayuda a elegir hiperparámetros (como λ en LASSO) que logren un buen equilibrio entre sesgo y varianza, reduciendo el riesgo de sobreajuste o subajuste. 

Datos: [Fold1 | Fold2 | Fold3 | Fold4 | Fold5]

Iteración 1: Entreno [F2+F3+F4+F5], valido en F1

Iteración 2: Entreno [F1+F3+F4+F5], valido en F2

Iteración 3: Entreno [F1+F2+F4+F5], valido en F3

Iteración 4: Entreno [F1+F2+F3+F5], valido en F4

Iteración 5: Entreno [F1+F2+F3+F4], valido en F5


Error final = promedio de los 5 errores

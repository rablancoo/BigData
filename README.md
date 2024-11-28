# CLASE 4 Modelo de Reconocimiento de Dígitos MNIST

## Descripción
Este proyecto tiene como objetivo mejorar la precisión de un modelo de reconocimiento de dígitos utilizando el conjunto de datos MNIST. Los experimentos iniciales se centraron en varios ajustes a la arquitectura del modelo y los parámetros de entrenamiento.

## Experimentación

1. **División de Datos**: Inicialmente, se probó cambiar la división entre los datos de entrenamiento y prueba, dejando solo el 10% para prueba. Sin embargo, este ajuste no produjo mejoras en los resultados.

2. **Arquitectura del Modelo**: 
   - Se aumentó el número de filtros y capas a 32 y 64, respectivamente. Este cambio buscó crear más capas con tamaños de filtro basados en potencias de 2 (1, 2, 4, 8, 16, 32, 64...) para facilitar la eficiencia computacional.
   - Se incrementó el número de épocas de entrenamiento a 20.

3. **Función de Activación**: 
   - La función de activación se cambió de `tanh` a `ReLU`. Se eligió ReLU porque no se satura como lo hace `tanh`, lo que puede mejorar el rendimiento del aprendizaje.

4. **Cambio de Optimizador**: 
   - El optimizador se cambió de Gradiente Descendente Estocástico (SGD) a Adam. Este cambio se realizó para mejorar la velocidad de convergencia y el rendimiento general del modelo.

5. **Resultados**: 
   - Durante el entrenamiento, se observaron mejoras incrementales en la precisión en el entrenamiento:
     - Época 13: Precisión alcanzó 0.9001
     - Época 14: Precisión aumentó a 0.9002
     - Época 18: Precisión alcanzó un máximo de 0.9009
   - Durante la prueba, apenas de logró el 89.91%

## Recomendaciones para Mejora Adicional
A pesar de estos esfuerzos, las mejoras en la precisión fueron modestas. Para mejorar aún más el rendimiento del modelo se hace uso de la IA, la cual, sugiere las siguientes recomendaciones:
- **Especificación de la Tasa de Aprendizaje**: Especificar claramente la tasa de aprendizaje para el método de optimización.
- **Capa de Regularización**: Introducir una capa de regularización para mitigar el sobreentrenamiento durante el entrenamiento.

Al implementar estas recomendaciones, esperamos lograr mejores resultados en futuras iteraciones del modelo.

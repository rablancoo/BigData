# CLASE 4 Ajuste de código para mejorar el desempeño del 90%

## Descripción
Este proyecto tiene como objetivo mejorar la precisión de un modelo de reconocimiento de dígitos utilizando el conjunto de datos MNIST. Los experimentos iniciales se centraron en varios ajustes a la arquitectura del modelo y los parámetros de entrenamiento como se puede ver en el archivo Clase_4_mnist_90_2.html.

## Experimentación

1. **División de Datos**: Inicialmente, se probó cambiar la división entre los datos de entrenamiento y prueba, dejando solo el 10% para prueba. Sin embargo, este ajuste no produjo mejoras en los resultados. Se considero que habían muchos datos dedicados a la prueba y el modelo perdía información importante.

2. **Arquitectura del Modelo**: 
   - Se aumentó el número de filtros y capas a 32 y 64, respectivamente. Este cambio buscó crear más capas con tamaños de filtro basados en potencias de 2 (1, 2, 4, 8, 16, 32, 64...) para facilitar la eficiencia computacional.
   - Se incrementó el número de épocas de entrenamiento a 20. De pronto, en siguientes corridas se lograba mejorar el desempeño.
   - Se agrego normalización a la salida de cada capa para que se mantuvieran los datos normalizados entre capas y el error no se trasladara con mayor aumento.
   - Se agregó una capa de regularización para mitigar el sobreentrenamiento. Se consideró que el modelo se estaba sobre entrenando y por eso no subía el desempeño.

3. **Función de Activación**: 
   - La función de activación se cambió de `tanh` a `ReLU`. Se eligió ReLU porque no se satura como lo hace `tanh`, lo que puede mejorar el rendimiento del aprendizaje.

4. **Cambio de Optimizador**: 
   - El optimizador se cambió de Gradiente Descendente Estocástico (SGD) a Adam. Este cambio se realizó para mejorar la velocidad de convergencia y el rendimiento general del modelo.

5. **Resultados**: 
   - Durante el entrenamiento, se observaron mejoras incrementales en la precisión en el entrenamiento:
     - Época 9: Precisión alcanzó 0.9001
       - ![image](https://github.com/user-attachments/assets/bfd4b1de-f4f0-4cd4-85af-a641e9fe1d88)
     - Época 13: Precisión aumentó a 0.9003
       - ![image](https://github.com/user-attachments/assets/db0d685c-cc6d-4b54-a35c-e83e0c0cd1e8)
     - Época 14: Precisión aumentó a 0.9004
       - ![image](https://github.com/user-attachments/assets/8e13c74e-9d89-42d4-af91-7c29229a9005)
     - Época 15: Precisión aumentó a 0.9006
       - ![image](https://github.com/user-attachments/assets/bfaf69e7-64cf-48a0-9d7e-29a1506d23e6)
     - Época 16: Precisión aumentó a 0.9008
       - ![image](https://github.com/user-attachments/assets/bdd62e2f-0d40-43f4-b37a-d29a66f3b1ad)
     - Época 18: Precisión aumentó a 0.9009
       - ![image](https://github.com/user-attachments/assets/1829b16f-8fa2-46aa-a1e9-8fb89ef0cf59)
     - Época 19: Precisión alcanzó un máximo de 0.9013
       - ![image](https://github.com/user-attachments/assets/c489dc20-2f75-44f4-8aad-a02294aaf130)

   - Durante la prueba, apenas de logró el 89.91%

## Recomendaciones para Mejora Adicional
A pesar de estos esfuerzos, las mejoras en la precisión fueron modestas. Para mejorar aún más el rendimiento del modelo se hace uso de la IA, la cual, sugiere las siguientes recomendaciones:
- **Especificación de la Tasa de Aprendizaje**: Especificar claramente la tasa de aprendizaje para el método de optimización.
- Tal vez, con un mayor número de épocas se logré mejorar el desempeño.

Al implementar estas recomendaciones, esperamos lograr mejores resultados en futuras iteraciones del modelo.

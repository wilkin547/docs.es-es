---
title: Automatizar el entrenamiento del modelo con la CLI de ML.NET
description: Descubra cómo usar la herramienta de la CLI de ML.NET para entrenar automáticamente el mejor modelo desde la línea de comandos.
ms.date: 12/17/2019
ms.custom: how-to, mlnet-tooling
ms.openlocfilehash: 3344ed15266503d4d5c7cd9db0a0596f58a904fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185881"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a>Automatizar el entrenamiento del modelo con la CLI de ML.NET

La CLI de ML.NET automatiza la generación de modelos para desarrolladores de .NET.

Para usar la API de ML.NET por sí misma (sin la CLI de AutoML de ML.NET) debe elegir un instructor (implementación de un algoritmo de aprendizaje automático para una tarea determinada) y el conjunto de transformaciones de datos (ingeniería de características) para aplicar a los datos. La canalización óptima puede variar para cada conjunto de datos y seleccionar el algoritmo óptimo entre todas las opciones agrega complejidad. Aún más, cada algoritmo tiene un conjunto de hiperparámetros que se deben optimizar. Por lo tanto, puede ahorrar semanas y a veces meses en la optimización del modelo de Machine Learning intentando encontrar las mejores combinaciones de ingeniería de características, algoritmos de aprendizaje e hiperparámetros.

La CLI de ML.NET simplifica este proceso mediante el aprendizaje automático automatizado (AutoML).

> [!NOTE]
> Este tema hace referencia a la **CLI** de ML.NET y **AutoML** de ML.NET, que se encuentran actualmente en versión preliminar, por lo que el material está sujeto a cambios.

## <a name="what-is-the-mlnet-command-line-interface-cli"></a>¿Qué es la herramienta de la interfaz de la línea de comandos (CLI) de ML.NET?

La CLI de ML.NET es una [herramienta de .NET Core](../core/tools/global-tools.md). Una vez instalada, se proporciona una tarea de aprendizaje automático y un conjunto de datos de entrenamiento, y genera un modelo de ML.NET, así como el código de C# que se va a ejecutar para usar el modelo en la aplicación.

Tal y como se muestra en la siguiente imagen, es fácil generar un modelo de ML.NET de alta calidad (archivo .zip del modelo serializado) además del código de C# de ejemplo para ejecutar o calificar dicho modelo. Además, el código de C# para crear o entrenar dicho modelo también se genera automáticamente para que pueda investigar e iterar en el algoritmo y la configuración que se usan para ese "mejor modelo" generado.

![imagen](media/automate-training-with-cli/cli-high-level-process.png "Motor de AutoML trabajando dentro de la CLI de ML.NET")

Puede generar dichos recursos desde sus propios conjuntos de datos sin necesidad de codificarlos usted, lo cual mejora también su productividad incluso si ya conoce ML.NET.

Actualmente, las tareas de Machine Learning compatibles con la CLI de ML.NET son:

- `binary-classification`
- `multiclass-classification`
- `regression`
- Futuro: otras tareas de aprendizaje automático, como `recommendation`, `ranking`, `anomaly-detection`, `clustering`

Ejemplo de uso:

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

![imagen](media/automate-training-with-cli/cli-model-generation.gif)

Se puede ejecutar de la misma manera en *Windows PowerShell*, * bash de macOS o Linux, o *Windows CMD*. Sin embargo, Autocompletar tabular (sugerencias de parámetro) no funcionará en *Windows CMD*.

## <a name="output-assets-generated"></a>Recursos de salida generados

El comando `auto-train` de la CLI genera los siguientes recursos en la carpeta de salida:

- Un archivo .zip de modelo serializado ("mejor modelo") listo para usarse en la ejecución de predicciones.
- Solución de C# con:
  - El código de C# para ejecutar o calificar dicho modelo generado (para realizar predicciones en las aplicaciones del usuario final con ese modelo).
  - El código de C# con el código de entrenamiento utilizado para generar ese modelo (con fines de aprendizaje o posibilidad de volver a entrenar el modelo).
- Archivo de registro con información de todas las iteraciones o barridos en varios algoritmos evaluados, incluida su canalización o configuración detallada.

Los dos primeros recursos se pueden usar directamente en las aplicaciones de usuario final (aplicación web ASP.NET Core, servicios, aplicación de escritorio, etc.) para realizar predicciones con dicho modelo de ML generado.

El tercer recurso, el código de aprendizaje, le muestra el código de la API de ML.NET que utilizó la CLI para entrenar el modelo generado, de modo que pueda volver a entrenar el modelo e investigar e iterar en qué hiperparámetros y algoritmos o instructores específicos seleccionó la CLI y AutoML en el interior.

## <a name="understanding-the-quality-of-the-model"></a>Descripción de la calidad del modelo

Al generar un "modelo mejor" con la herramienta de la CLI, verá métricas de calidad (como precisión y R cuadrado) según corresponda a la tarea de ML que tiene como destino.

Aquí se resumen esas métricas agrupadas por tareas de ML para que pueda comprender la calidad de su "mejor modelo" autogenerado.

### <a name="metrics-for-binary-classification-models"></a>Métricas para los modelos de clasificación binaria

A continuación, se muestra la lista de métricas de la tarea de ML de clasificación binaria para los cinco principales modelos encontrados por la CLI:

![imagen](media/automate-training-with-cli/cli-binary-classification-metrics.png)

La precisión es una métrica popular en los problemas de clasificación, pero no siempre es la mejor métrica para seleccionar el mejor modelo, tal y como se explica en las siguientes referencias. Hay casos donde es necesario evaluar la calidad del modelo con métricas adicionales.

Para explorar y comprender las métricas que son el resultado de la CLI, consulte [Métricas de evaluación de clasificación binaria](resources/metrics.md#evaluation-metrics-for-binary-classification).

### <a name="metrics-for-multi-class-classification-models"></a>Métricas para modelos de clasificación multiclase

A continuación, se muestra la lista de métricas de la tarea de ML de clasificación multiclase para los cinco principales modelos encontrados por la CLI:

![imagen](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

Para explorar y comprender las métricas que son el resultado de la CLI, consulte [Métricas de evaluación de clasificación multiclase](resources/metrics.md#evaluation-metrics-for-multi-class-classification).

### <a name="metrics-for-regression-and-recommendation-models"></a>Métricas para modelos de regresión y recomendación

Un modelo de regresión se ajusta bien a los datos si las diferencias entre los valores observados y los valores de predicción del modelo son pequeñas y no están sesgadas. La regresión se puede evaluar con determinadas métricas.

Verá una lista similar de métricas de los cinco principales modelos de calidad mejor encontrados por la CLI. En este caso concreto relacionado con una tarea de ML de regresión:

![imagen](media/automate-training-with-cli/cli-regression-metrics.png)

Para explorar y comprender las métricas que son el resultado de la CLI, consulte [Métricas de evaluación de regresión](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).

## <a name="see-also"></a>Vea también

- [Cómo instalar la herramienta de la CLI de ML.NET](how-to-guides/install-ml-net-cli.md)
- [Tutorial: Análisis de opiniones mediante la CLI de ML.NET](tutorials/sentiment-analysis-cli.md)
- [Referencia de comandos de la CLI de ML.NET](reference/ml-net-cli-reference.md)
- [Telemetría en la CLI de ML.NET](resources/ml-net-cli-telemetry.md)

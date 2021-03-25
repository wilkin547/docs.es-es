---
title: Automatizar el entrenamiento del modelo con la CLI de ML.NET
description: Descubra cómo usar la herramienta de la CLI de ML.NET para entrenar automáticamente el mejor modelo desde la línea de comandos.
ms.date: 06/03/2020
ms.custom: how-to, mlnet-tooling
ms.openlocfilehash: 0b230e4a517b6493abdb1ec975776fd286b654e3
ms.sourcegitcommit: b27645cb378d4e8137a267e5467ff31409acf6c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "103231412"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a><span data-ttu-id="096f6-103">Automatizar el entrenamiento del modelo con la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="096f6-103">Automate model training with the ML.NET CLI</span></span>

<span data-ttu-id="096f6-104">La CLI de ML.NET automatiza la generación de modelos para desarrolladores de .NET.</span><span class="sxs-lookup"><span data-stu-id="096f6-104">The ML.NET CLI automates model generation for .NET developers.</span></span>

<span data-ttu-id="096f6-105">Para usar la API de ML.NET por sí misma (sin la CLI de AutoML de ML.NET) debe elegir un instructor (implementación de un algoritmo de aprendizaje automático para una tarea determinada) y el conjunto de transformaciones de datos (ingeniería de características) para aplicar a los datos.</span><span class="sxs-lookup"><span data-stu-id="096f6-105">To use the ML.NET API by itself, (without the ML.NET AutoML CLI) you need to choose a trainer (implementation of a machine learning algorithm for a particular task), and the set of data transformations (feature engineering) to apply to your data.</span></span> <span data-ttu-id="096f6-106">La canalización óptima puede variar para cada conjunto de datos y seleccionar el algoritmo óptimo entre todas las opciones agrega complejidad.</span><span class="sxs-lookup"><span data-stu-id="096f6-106">The optimal pipeline will vary for each dataset and selecting the optimal algorithm from all the choices adds to the complexity.</span></span> <span data-ttu-id="096f6-107">Aún más, cada algoritmo tiene un conjunto de hiperparámetros que se deben optimizar.</span><span class="sxs-lookup"><span data-stu-id="096f6-107">Even further, each algorithm has a set of hyperparameters to be tuned.</span></span> <span data-ttu-id="096f6-108">Por lo tanto, puede ahorrar semanas y a veces meses en la optimización del modelo de Machine Learning intentando encontrar las mejores combinaciones de ingeniería de características, algoritmos de aprendizaje e hiperparámetros.</span><span class="sxs-lookup"><span data-stu-id="096f6-108">Hence, you can spend weeks and sometimes months on machine learning model optimization trying to find the best combinations of feature engineering, learning algorithms, and hyperparameters.</span></span>

<span data-ttu-id="096f6-109">La CLI de ML.NET simplifica este proceso mediante el aprendizaje automático automatizado (AutoML).</span><span class="sxs-lookup"><span data-stu-id="096f6-109">The ML.NET CLI simplifies this process using automated machine learning (AutoML).</span></span>

> [!NOTE]
> <span data-ttu-id="096f6-110">Este tema hace referencia a la **CLI** de ML.NET y **AutoML** de ML.NET, que se encuentran actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="096f6-110">This topic refers to ML.NET **CLI** and ML.NET **AutoML**, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="what-is-the-mlnet-command-line-interface-cli"></a><span data-ttu-id="096f6-111">¿Qué es la herramienta de la interfaz de la línea de comandos (CLI) de ML.NET?</span><span class="sxs-lookup"><span data-stu-id="096f6-111">What is the ML.NET command-line interface (CLI)?</span></span>

<span data-ttu-id="096f6-112">La CLI de ML.NET es una [herramienta de .NET Core](../core/tools/global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="096f6-112">The ML.NET CLI is a [.NET Core tool](../core/tools/global-tools.md).</span></span> <span data-ttu-id="096f6-113">Una vez instalada, se proporciona una tarea de aprendizaje automático y un conjunto de datos de entrenamiento, y genera un modelo de ML.NET, así como el código de C# que se va a ejecutar para usar el modelo en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="096f6-113">Once installed, you give it a machine learning task and a training dataset, and it generates an ML.NET model, as well as the C# code to run to use the model in your application.</span></span>

<span data-ttu-id="096f6-114">Tal y como se muestra en la siguiente imagen, es fácil generar un modelo de ML.NET de alta calidad (archivo .zip del modelo serializado) además del código de C# de ejemplo para ejecutar o calificar dicho modelo.</span><span class="sxs-lookup"><span data-stu-id="096f6-114">As shown in the following figure, it is simple to generate a high quality ML.NET model (serialized model .zip file) plus the sample C# code to run/score that model.</span></span> <span data-ttu-id="096f6-115">Además, el código de C# para crear o entrenar dicho modelo también se genera automáticamente para que pueda investigar e iterar en el algoritmo y la configuración que se usan para ese "mejor modelo" generado.</span><span class="sxs-lookup"><span data-stu-id="096f6-115">In addition, the C# code to create/train that model is also generated, so that you can research and iterate on the algorithm and settings used for that generated "best model".</span></span>

![Motor de AutoML trabajando dentro de la CLI de ML.NET](media/automate-training-with-cli/cli-high-level-process.png)

<span data-ttu-id="096f6-117">Puede generar dichos recursos desde sus propios conjuntos de datos sin necesidad de codificarlos usted, lo cual mejora también su productividad incluso si ya conoce ML.NET.</span><span class="sxs-lookup"><span data-stu-id="096f6-117">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="096f6-118">Actualmente, las tareas de Machine Learning compatibles con la CLI de ML.NET son:</span><span class="sxs-lookup"><span data-stu-id="096f6-118">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- <span data-ttu-id="096f6-119">clasificación</span><span class="sxs-lookup"><span data-stu-id="096f6-119">classification</span></span>
- <span data-ttu-id="096f6-120">Regresión</span><span class="sxs-lookup"><span data-stu-id="096f6-120">regression</span></span>
- <span data-ttu-id="096f6-121">recomendación</span><span class="sxs-lookup"><span data-stu-id="096f6-121">recommendation</span></span>
- <span data-ttu-id="096f6-122">clasificación de imágenes</span><span class="sxs-lookup"><span data-stu-id="096f6-122">image classification</span></span>

<span data-ttu-id="096f6-123">Ejemplo de uso (escenario de clasificación):</span><span class="sxs-lookup"><span data-stu-id="096f6-123">Example of usage (classification scenario):</span></span>

```console
mlnet classification --dataset "yelp_labelled.txt" --label-col 1 --has-header false --train-time 10
```

![Clasificación de ML.NET desde la línea de comandos](media/automate-training-with-cli/mlnet-classification-powershell.gif)

<span data-ttu-id="096f6-125">Se puede ejecutar de la misma manera en *Windows PowerShell*, *macOS/Linux bash* o *Windows CMD*.</span><span class="sxs-lookup"><span data-stu-id="096f6-125">You can run it the same way on *Windows PowerShell*, *macOS/Linux bash*, or *Windows CMD*.</span></span> <span data-ttu-id="096f6-126">Sin embargo, Autocompletar tabular (sugerencias de parámetro) no funcionará en *Windows CMD*.</span><span class="sxs-lookup"><span data-stu-id="096f6-126">However, tabular auto-completion (parameter suggestions) won't work on *Windows CMD*.</span></span>

## <a name="output-assets-generated"></a><span data-ttu-id="096f6-127">Recursos de salida generados</span><span class="sxs-lookup"><span data-stu-id="096f6-127">Output assets generated</span></span>

<span data-ttu-id="096f6-128">Los comandos de tarea de ML de la CLI generan los siguientes recursos en la carpeta de salida:</span><span class="sxs-lookup"><span data-stu-id="096f6-128">The ML task commands in the CLI generate the following assets in the output folder:</span></span>

- <span data-ttu-id="096f6-129">Un archivo .zip de modelo serializado ("mejor modelo") listo para usarse en la ejecución de predicciones.</span><span class="sxs-lookup"><span data-stu-id="096f6-129">A serialized model .zip ("best model") ready to use for running predictions.</span></span>
- <span data-ttu-id="096f6-130">Solución de C# con:</span><span class="sxs-lookup"><span data-stu-id="096f6-130">C# solution with:</span></span>
  - <span data-ttu-id="096f6-131">El código de C# para ejecutar o calificar dicho modelo generado (para realizar predicciones en las aplicaciones del usuario final con ese modelo).</span><span class="sxs-lookup"><span data-stu-id="096f6-131">C# code to run/score that generated model (to make predictions in your end-user apps with that model).</span></span>
  - <span data-ttu-id="096f6-132">El código de C# con el código de entrenamiento utilizado para generar ese modelo (con fines de aprendizaje o posibilidad de volver a entrenar el modelo).</span><span class="sxs-lookup"><span data-stu-id="096f6-132">C# code with the training code used to generate that model (for learning purposes or model retraining).</span></span>
- <span data-ttu-id="096f6-133">Archivo de registro con información de todas las iteraciones o barridos en varios algoritmos evaluados, incluida su canalización o configuración detallada.</span><span class="sxs-lookup"><span data-stu-id="096f6-133">Log file with information of all iterations/sweeps across the multiple algorithms evaluated, including their detailed configuration/pipeline.</span></span>

<span data-ttu-id="096f6-134">Los dos primeros recursos se pueden usar directamente en las aplicaciones de usuario final (aplicación web ASP.NET Core, servicios, aplicación de escritorio, etc.) para realizar predicciones con dicho modelo de ML generado.</span><span class="sxs-lookup"><span data-stu-id="096f6-134">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="096f6-135">El tercer recurso, el código de aprendizaje, le muestra el código de la API de ML.NET que utilizó la CLI para entrenar el modelo generado, de modo que pueda volver a entrenar el modelo e investigar e iterar en qué hiperparámetros y algoritmos o instructores específicos seleccionó la CLI y AutoML en el interior.</span><span class="sxs-lookup"><span data-stu-id="096f6-135">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can retrain your model and investigate and iterate on which specific trainer/algorithm and hyperparameters were selected by the CLI and AutoML under the covers.</span></span>

## <a name="understanding-the-quality-of-the-model"></a><span data-ttu-id="096f6-136">Descripción de la calidad del modelo</span><span class="sxs-lookup"><span data-stu-id="096f6-136">Understanding the quality of the model</span></span>

<span data-ttu-id="096f6-137">Al generar un "modelo mejor" con la herramienta de la CLI, verá métricas de calidad (como precisión y R cuadrado) según corresponda a la tarea de ML que tiene como destino.</span><span class="sxs-lookup"><span data-stu-id="096f6-137">When you generate a 'best model' with the CLI tool, you see quality metrics (such as accuracy and R-Squared) as appropriate for the ML task you're targeting.</span></span>

<span data-ttu-id="096f6-138">Aquí se resumen esas métricas agrupadas por tareas de ML para que pueda comprender la calidad de su "mejor modelo" autogenerado.</span><span class="sxs-lookup"><span data-stu-id="096f6-138">Here those metrics are summarized grouped by ML task so you can understand the quality of your auto-generated 'best model'.</span></span>

### <a name="metrics-for-classification-models"></a><span data-ttu-id="096f6-139">Métricas para modelos de clasificación</span><span class="sxs-lookup"><span data-stu-id="096f6-139">Metrics for Classification models</span></span>

<span data-ttu-id="096f6-140">En la imagen siguiente se muestra la lista de métricas de clasificación para los cinco modelos principales encontrados por la CLI:</span><span class="sxs-lookup"><span data-stu-id="096f6-140">The following image displays the classification metrics list for the top five models found by the CLI:</span></span>

![Métricas de clasificación para los cinco modelos principales](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

 <span data-ttu-id="096f6-142">La precisión es una métrica popular en los problemas de clasificación, pero no siempre es la mejor métrica para seleccionar el mejor modelo, tal y como se explica en las siguientes referencias.</span><span class="sxs-lookup"><span data-stu-id="096f6-142">Accuracy is a popular metric for classification problems, however accuracy isn't always the best metric to select the best model from as explained in the following references.</span></span> <span data-ttu-id="096f6-143">Hay casos donde es necesario evaluar la calidad del modelo con métricas adicionales.</span><span class="sxs-lookup"><span data-stu-id="096f6-143">There are cases where you need to evaluate the quality of your model with additional metrics.</span></span>

<span data-ttu-id="096f6-144">Para explorar y comprender las métricas que son el resultado de la CLI, consulte [Métricas de evaluación de clasificación](resources/metrics.md#evaluation-metrics-for-multi-class-classification).</span><span class="sxs-lookup"><span data-stu-id="096f6-144">To explore and understand the metrics that are output by the CLI, see [Evaluation metrics for classification](resources/metrics.md#evaluation-metrics-for-multi-class-classification).</span></span>

### <a name="metrics-for-regression-and-recommendation-models"></a><span data-ttu-id="096f6-145">Métricas para modelos de regresión y recomendación</span><span class="sxs-lookup"><span data-stu-id="096f6-145">Metrics for Regression and Recommendation models</span></span>

<span data-ttu-id="096f6-146">Un modelo de regresión se ajusta bien a los datos si las diferencias entre los valores observados y los valores de predicción del modelo son pequeñas y no están sesgadas.</span><span class="sxs-lookup"><span data-stu-id="096f6-146">A regression model fits the data well if the differences between the observed values and the model's predicted values are small and unbiased.</span></span> <span data-ttu-id="096f6-147">La regresión se puede evaluar con determinadas métricas.</span><span class="sxs-lookup"><span data-stu-id="096f6-147">Regression can be evaluated with certain metrics.</span></span>

<span data-ttu-id="096f6-148">Verá una lista similar de métricas para los cinco modelos de calidad principales encontrados por la CLI, pero en este caso, están relacionados con una tarea de ML de regresión:</span><span class="sxs-lookup"><span data-stu-id="096f6-148">You'll see a similar list of metrics for the top five quality models found by the CLI, except in this case, the top five are related to a regression ML task:</span></span>

![Métricas de regresión para los cinco modelos principales](media/automate-training-with-cli/cli-regression-metrics.png)

<span data-ttu-id="096f6-150">Para explorar y comprender las métricas que son el resultado de la CLI, consulte [Métricas de evaluación de regresión](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).</span><span class="sxs-lookup"><span data-stu-id="096f6-150">To explore and understand the metrics that are output by the CLI, see [Evaluation metrics for regression](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).</span></span>

## <a name="see-also"></a><span data-ttu-id="096f6-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="096f6-151">See also</span></span>

- [<span data-ttu-id="096f6-152">Cómo instalar la herramienta de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="096f6-152">How to install the ML.NET CLI tool</span></span>](how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="096f6-153">Tutorial: Análisis de opiniones mediante la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="096f6-153">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="096f6-154">Referencia de comandos de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="096f6-154">ML.NET CLI command reference</span></span>](reference/ml-net-cli-reference.md)
- [<span data-ttu-id="096f6-155">Telemetría en la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="096f6-155">Telemetry in ML.NET CLI</span></span>](resources/ml-net-cli-telemetry.md)

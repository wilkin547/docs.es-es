---
title: Automatizar el entrenamiento del modelo con la CLI de ML.NET
description: Descubra cómo usar la herramienta de la CLI de ML.NET para entrenar automáticamente el mejor modelo desde la línea de comandos.
author: CESARDELATORRE
ms.date: 04/17/2019
ms.custom: how-to
ms.openlocfilehash: 33383582140d9df4290a0bbf30659301af837d1d
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065898"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a><span data-ttu-id="68de6-103">Automatizar el entrenamiento del modelo con la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="68de6-103">Automate model training with the ML.NET CLI</span></span>

<span data-ttu-id="68de6-104">La CLI de ML.NET "democratiza" ML.NET para desarrolladores de .NET cuando se entrena ML.NET.</span><span class="sxs-lookup"><span data-stu-id="68de6-104">The ML.NET CLI "democratizes" ML.NET for .NET developers when learning ML.NET.</span></span>

<span data-ttu-id="68de6-105">Para usar la API de ML.NET por sí misma (sin la CLI de AutoML de ML.NET) debe elegir un instructor (implementación de un algoritmo de aprendizaje automático para una tarea determinada) y el conjunto de transformaciones de datos (ingeniería de características) para aplicar a los datos.</span><span class="sxs-lookup"><span data-stu-id="68de6-105">To use the ML.NET API by itself, (without the ML.NET AutoML CLI) you need to choose a trainer (implementation of a machine learning algorithm for a particular task), and the set of data transformations (feature engineering) to apply to your data.</span></span> <span data-ttu-id="68de6-106">La canalización óptima puede variar para cada conjunto de datos y seleccionar el algoritmo óptimo entre todas las opciones agrega complejidad.</span><span class="sxs-lookup"><span data-stu-id="68de6-106">The optimal pipeline will vary for each dataset and selecting the optimal algorithm from all the choices adds to the complexity.</span></span> <span data-ttu-id="68de6-107">Aún más, cada algoritmo tiene un conjunto de hiperparámetros que se deben optimizar.</span><span class="sxs-lookup"><span data-stu-id="68de6-107">Even further, each algorithm has a set of hyperparameters to be tuned.</span></span> <span data-ttu-id="68de6-108">Por lo tanto, puede ahorrar semanas y a veces meses en la optimización del modelo de Machine Learning intentando encontrar las mejores combinaciones de ingeniería de características, algoritmos de aprendizaje e hiperparámetros.</span><span class="sxs-lookup"><span data-stu-id="68de6-108">Hence, you can spend weeks and sometimes months on machine learning model optimization trying to find the best combinations of feature engineering, learning algorithms, and hyperparameters.</span></span>

<span data-ttu-id="68de6-109">Este proceso se puede automatizar con la CLI de ML.NET, que implementa el motor inteligente de AutoML de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="68de6-109">This process can be automated with the ML.NET CLI, which implements the ML.NET AutoML intelligent engine.</span></span> 

> [!NOTE]
> <span data-ttu-id="68de6-110">Este tema hace referencia a la **CLI** de ML.NET y **AutoML** de ML.NET, que se encuentran actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="68de6-110">This topic refers to ML.NET **CLI** and ML.NET **AutoML**, which are currently in Preview, and material may be subject to change.</span></span> 

## <a name="what-is-the-mlnet-command-line-interface-cli"></a><span data-ttu-id="68de6-111">¿Qué es la herramienta de la interfaz de la línea de comandos (CLI) de ML.NET?</span><span class="sxs-lookup"><span data-stu-id="68de6-111">What is the ML.NET Command-line Interface (CLI)?</span></span>

<span data-ttu-id="68de6-112">Puede ejecutar la CLI de ML.NET en cualquier símbolo del sistema (Windows, Mac o Linux) para generar modelos de ML.NET de buena calidad y el código fuente basado en sus conjuntos de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="68de6-112">You can run the ML.NET CLI on any command-prompt (Windows, Mac, or Linux) for generating good quality ML.NET models and source code based on your training dataset.</span></span>

<span data-ttu-id="68de6-113">Tal como se muestra en la siguiente figura, es fácil generar un modelo de ML.NET de alta calidad (archivo .zip del modelo serializado) además del código de C# de ejemplo para ejecutar o calificar dicho modelo.</span><span class="sxs-lookup"><span data-stu-id="68de6-113">As shown in the figure below, it is simple to generate a high quality ML.NET model (serialized model .zip file) plus the sample C# code to run/score that model.</span></span> <span data-ttu-id="68de6-114">Además, el código de C# para crear o entrenar dicho modelo también se genera automáticamente para que pueda investigar e iterar en el algoritmo y la configuración que se usan para ese "mejor modelo" generado.</span><span class="sxs-lookup"><span data-stu-id="68de6-114">In addition, the C# code to create/train that model is also generated, so that you can research and iterate on the algorithm and settings used for that generated "best model".</span></span> 

<span data-ttu-id="68de6-115">![imagen](media/automate-training-with-cli/cli-high-level-process.png "motor de AutoML trabajando dentro de la CLI de ML.NET")</span><span class="sxs-lookup"><span data-stu-id="68de6-115">![image](media/automate-training-with-cli/cli-high-level-process.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="68de6-116">Puede generar dichos recursos desde sus propios conjuntos de datos sin necesidad de codificarlos usted, lo cual mejora también su productividad incluso si ya conoce ML.NET.</span><span class="sxs-lookup"><span data-stu-id="68de6-116">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="68de6-117">Actualmente, las tareas de Machine Learning compatibles con la CLI de ML.NET son:</span><span class="sxs-lookup"><span data-stu-id="68de6-117">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification` 
- `regression`
- <span data-ttu-id="68de6-118">Futuro: otras tareas de aprendizaje automático, como `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span><span class="sxs-lookup"><span data-stu-id="68de6-118">Future: other machine learning tasks such as `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span></span>

<span data-ttu-id="68de6-119">Ejemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="68de6-119">Example of usage:</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

![imagen](media/automate-training-with-cli/cli-model-generation.gif)

<span data-ttu-id="68de6-121">Se puede ejecutar de la misma manera en *Windows PowerShell*, \* bash de macOS o Linux, o *Windows CMD*.</span><span class="sxs-lookup"><span data-stu-id="68de6-121">You can run it the same way on *Windows PowerShell*, \*macOS/Linux bash, or *Windows CMD*.</span></span> <span data-ttu-id="68de6-122">Sin embargo, Autocompletar tabular (sugerencias de parámetro) no funcionará en *Windows CMD*.</span><span class="sxs-lookup"><span data-stu-id="68de6-122">However, tabular auto-completion (parameter suggestions) won't work on *Windows CMD*.</span></span>

## <a name="output-assets-generated"></a><span data-ttu-id="68de6-123">Recursos de salida generados</span><span class="sxs-lookup"><span data-stu-id="68de6-123">Output assets generated</span></span>

<span data-ttu-id="68de6-124">El comando `auto-train` de la CLI genera los siguientes recursos en la carpeta de salida:</span><span class="sxs-lookup"><span data-stu-id="68de6-124">The CLI `auto-train` command generates the following assets in the output folder:</span></span>

- <span data-ttu-id="68de6-125">Un archivo .zip de modelo serializado ("mejor modelo") listo para usarse en la ejecución de predicciones.</span><span class="sxs-lookup"><span data-stu-id="68de6-125">A serialized model .zip ("best model") ready to use for running predictions.</span></span> 
- <span data-ttu-id="68de6-126">Solución de C# con:</span><span class="sxs-lookup"><span data-stu-id="68de6-126">C# solution with:</span></span>
    - <span data-ttu-id="68de6-127">El código de C# para ejecutar o calificar dicho modelo generado (para realizar predicciones en las aplicaciones del usuario final con ese modelo).</span><span class="sxs-lookup"><span data-stu-id="68de6-127">C# code to run/score that generated model (to make predictions in your end-user apps with that model).</span></span>
    - <span data-ttu-id="68de6-128">El código de C# con el código de entrenamiento utilizado para generar ese modelo (con fines de aprendizaje o posibilidad de volver a entrenar el modelo).</span><span class="sxs-lookup"><span data-stu-id="68de6-128">C# code with the training code used to generate that model (for learning purposes or model retraining).</span></span>
- <span data-ttu-id="68de6-129">Archivo de registro con información de todas las iteraciones o barridos en varios algoritmos evaluados, incluida su canalización o configuración detallada.</span><span class="sxs-lookup"><span data-stu-id="68de6-129">Log file with information of all iterations/sweeps across the multiple algorithms evaluated, including their detailed configuration/pipeline.</span></span>

<span data-ttu-id="68de6-130">Los dos primeros recursos se pueden usar directamente en las aplicaciones de usuario final (aplicación web ASP.NET Core, servicios, aplicación de escritorio, etc.) para realizar predicciones con dicho modelo de ML generado.</span><span class="sxs-lookup"><span data-stu-id="68de6-130">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="68de6-131">El tercer recurso, el código de aprendizaje, le muestra el código de la API de ML.NET que utilizó la CLI para entrenar el modelo generado, de modo que pueda volver a entrenar el modelo e investigar e iterar en qué hiperparámetros y algoritmos o instructores específicos seleccionó la CLI y AutoML en el interior.</span><span class="sxs-lookup"><span data-stu-id="68de6-131">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can retrain your model and investigate and iterate on which specific trainer/algorithm and hyperparameters were selected by the CLI and AutoML under the covers.</span></span> 

## <a name="understanding-the-quality-of-the-model"></a><span data-ttu-id="68de6-132">Descripción de la calidad del modelo</span><span class="sxs-lookup"><span data-stu-id="68de6-132">Understanding the quality of the model</span></span>

<span data-ttu-id="68de6-133">Al generar un "modelo mejor' con la herramienta de la CLI, verá métricas de calidad (como precisión y R cuadrado) según corresponda para la tarea de ML que tiene como destino.</span><span class="sxs-lookup"><span data-stu-id="68de6-133">When you generate a 'best model' with the CLI tool, you see quality metrics (such as accuracy, and R-Squared) as appropriate for the ML task you are targeting.</span></span>

<span data-ttu-id="68de6-134">Aquí se resumen esas métricas agrupadas por tareas de ML para que pueda comprender la calidad de su "mejor modelo" autogenerado.</span><span class="sxs-lookup"><span data-stu-id="68de6-134">Here we summarize those metrics grouped by ML task so you can understand the quality of your auto-generated 'best model'.</span></span>

### <a name="metrics-for-binary-classification-models"></a><span data-ttu-id="68de6-135">Métricas para los modelos de clasificación binaria</span><span class="sxs-lookup"><span data-stu-id="68de6-135">Metrics for Binary Classification models</span></span>

 <span data-ttu-id="68de6-136">A continuación, se muestra la lista de métricas de la tarea de ML de clasificación binaria para los cinco principales modelos encontrados por la CLI:</span><span class="sxs-lookup"><span data-stu-id="68de6-136">The following displays the binary classification ML task metrics list for the top five models found by the CLI:</span></span> 

![imagen](media/automate-training-with-cli/cli-binary-classification-metrics.png)

<span data-ttu-id="68de6-138">La precisión es una métrica popular para problemas de clasificación. Sin embargo, la precisión no siempre es la mejor métrica para seleccionar el mejor modelo, tal como se explica en las referencias siguientes.</span><span class="sxs-lookup"><span data-stu-id="68de6-138">Accuracy is a popular metric for classification problems, however accuracy is not always the best metric to select the best model from as explained in the references below.</span></span> <span data-ttu-id="68de6-139">Hay casos donde es necesario evaluar la calidad del modelo con métricas adicionales.</span><span class="sxs-lookup"><span data-stu-id="68de6-139">There are cases where you need to evaluate the quality of your model with additional metrics.</span></span>

<span data-ttu-id="68de6-140">Para explorar y comprender las métricas que son el resultado de la CLI, consulte [Métricas de clasificación binaria](resources/metrics.md#metrics-for-binary-classification).</span><span class="sxs-lookup"><span data-stu-id="68de6-140">To explore and understand the metrics that are output by the CLI, see [Metrics for binary classification](resources/metrics.md#metrics-for-binary-classification).</span></span>

### <a name="metrics-for-multi-class-classification-models"></a><span data-ttu-id="68de6-141">Métricas para modelos de clasificación multiclase</span><span class="sxs-lookup"><span data-stu-id="68de6-141">Metrics for Multi-class Classification models</span></span>

 <span data-ttu-id="68de6-142">A continuación, se muestra la lista de métricas de la tarea de ML de clasificación multiclase para los cinco principales modelos encontrados por la CLI:</span><span class="sxs-lookup"><span data-stu-id="68de6-142">The following displays the multi-class classification ML task metrics list for the top five models found by the CLI:</span></span> 

![imagen](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

<span data-ttu-id="68de6-144">Para explorar y comprender las métricas que son el resultado de la CLI, consulte [Métricas de clasificación multiclase](resources/metrics.md#metrics-for-multi-class-classification).</span><span class="sxs-lookup"><span data-stu-id="68de6-144">To explore and understand the metrics that are output by the CLI, see [Metrics for multiclass classification](resources/metrics.md#metrics-for-multi-class-classification).</span></span>

### <a name="metrics-for-regression-models"></a><span data-ttu-id="68de6-145">Métricas para modelos de regresión</span><span class="sxs-lookup"><span data-stu-id="68de6-145">Metrics for Regression models</span></span>

<span data-ttu-id="68de6-146">Un modelo de regresión se ajusta bien a los datos si las diferencias entre los valores observados y los valores de predicción del modelo son pequeñas y no están sesgadas.</span><span class="sxs-lookup"><span data-stu-id="68de6-146">A regression model fits the data well if the differences between the observed values and the model's predicted values are small and unbiased.</span></span> <span data-ttu-id="68de6-147">La regresión se puede evaluar con determinadas métricas.</span><span class="sxs-lookup"><span data-stu-id="68de6-147">Regression can be evaluated with certain metrics.</span></span>

<span data-ttu-id="68de6-148">Verá una lista similar de métricas para los cinco principales modelos de calidad mejor encontrados por la CLI.</span><span class="sxs-lookup"><span data-stu-id="68de6-148">You will see a similar list of metrics for the best top five quality models found by the CLI.</span></span> <span data-ttu-id="68de6-149">En este caso concreto relacionado con una tarea de ML de regresión:</span><span class="sxs-lookup"><span data-stu-id="68de6-149">In this particular case related to a regression ML task:</span></span>

![imagen](media/automate-training-with-cli/cli-regression-metrics.png)

<span data-ttu-id="68de6-151">Para explorar y comprender las métricas que son el resultado de la CLI, consulte [Métricas de regresión](resources/metrics.md#metrics-for-regression).</span><span class="sxs-lookup"><span data-stu-id="68de6-151">To explore and understand the metrics that are output by the CLI, see [Metrics for regression](resources/metrics.md#metrics-for-regression).</span></span>

## <a name="see-also"></a><span data-ttu-id="68de6-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="68de6-152">See also</span></span>

- [<span data-ttu-id="68de6-153">Cómo instalar la herramienta de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="68de6-153">How to install the ML.NET CLI tool</span></span>](how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="68de6-154">Tutorial: Generación automática de un clasificador binario mediante la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="68de6-154">Tutorial: Auto generate a binary classifier using the ML.NET CLI</span></span>](tutorials/mlnet-cli.md)
- [<span data-ttu-id="68de6-155">Referencia de comandos de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="68de6-155">ML.NET CLI command reference</span></span>](reference/ml-net-cli-reference.md)
- [<span data-ttu-id="68de6-156">Telemetría en la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="68de6-156">Telemetry in ML.NET CLI</span></span>](resources/ml-net-cli-telemetry.md)

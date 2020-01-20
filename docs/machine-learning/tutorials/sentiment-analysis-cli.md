---
title: Análisis de opiniones mediante la CLI de ML.NET
description: Generar automáticamente un modelo de ML y el código de C# relacionado desde un conjunto de datos de ejemplo
author: cesardl
ms.author: cesardl
ms.date: 12/23/2019
ms.custom: mvc
ms.topic: tutorial
ms.openlocfilehash: caf12296b208b3d2e57c3a74300cced225e4db66
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75738758"
---
# <a name="analyze-sentiment-using-the-mlnet-cli"></a><span data-ttu-id="9fd05-103">Análisis de opiniones mediante la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="9fd05-103">Analyze sentiment using the ML.NET CLI</span></span>

<span data-ttu-id="9fd05-104">Aprenda a usar la CLI de ML.NET para generar automáticamente un modelo de ML.NET y el código de C# subyacente.</span><span class="sxs-lookup"><span data-stu-id="9fd05-104">Learn how to use ML.NET CLI to automatically generate an ML.NET model and underlying C# code.</span></span> <span data-ttu-id="9fd05-105">Usted proporciona el conjunto de datos y la tarea de aprendizaje automático que desea implementar, y la CLI utiliza el motor de AutoML para crear el código fuente de implementación y generación de modelos, así como el modelo binario.</span><span class="sxs-lookup"><span data-stu-id="9fd05-105">You provide your dataset and the machine learning task you want to implement, and the CLI uses the AutoML engine to create model generation and deployment source code, as well as the binary model.</span></span>

<span data-ttu-id="9fd05-106">En este tutorial, llevará a cabo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9fd05-106">In this tutorial, you will do the following steps:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="9fd05-107">Preparar los datos para la tarea de aprendizaje automático seleccionada</span><span class="sxs-lookup"><span data-stu-id="9fd05-107">Prepare your data for the selected machine learning task</span></span>
> - <span data-ttu-id="9fd05-108">Ejecutar el comando "mlnet auto-train" desde la CLI</span><span class="sxs-lookup"><span data-stu-id="9fd05-108">Run the 'mlnet auto-train' command from the CLI</span></span>
> - <span data-ttu-id="9fd05-109">Revisar los resultados de métrica de calidad</span><span class="sxs-lookup"><span data-stu-id="9fd05-109">Review the quality metric results</span></span>
> - <span data-ttu-id="9fd05-110">Comprender el código de C# generado para usar el modelo en la aplicación</span><span class="sxs-lookup"><span data-stu-id="9fd05-110">Understand the generated C# code to use the model in your application</span></span>
> - <span data-ttu-id="9fd05-111">Explorar el código de C# generado que se usó para entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="9fd05-111">Explore the generated C# code that was used to train the model</span></span>

> [!NOTE]
> <span data-ttu-id="9fd05-112">Este tema hace referencia a la herramienta de la CLI de ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="9fd05-112">This topic refers to the ML.NET CLI tool, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="9fd05-113">Para obtener más información, visite la página de [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="9fd05-113">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="9fd05-114">La CLI de ML.NET forma parte de ML.NET y su objetivo principal es "democratizar" ML.NET para desarrolladores de .NET durante el aprendizaje de ML.NET, por lo que no es necesario codificar desde cero para empezar a trabajar.</span><span class="sxs-lookup"><span data-stu-id="9fd05-114">The ML.NET CLI is part of ML.NET and its main goal is to "democratize" ML.NET for .NET developers when learning ML.NET so you don't need to code from scratch to get started.</span></span>

<span data-ttu-id="9fd05-115">Puede ejecutar la CLI de ML.NET en cualquier símbolo del sistema (Windows, Mac o Linux) para generar modelos de ML.NET de buena calidad y el código fuente basado en los conjuntos de datos de entrenamiento que proporcione.</span><span class="sxs-lookup"><span data-stu-id="9fd05-115">You can run the ML.NET CLI on any command-prompt (Windows, Mac, or Linux) to generate good quality ML.NET models and source code based on training datasets you provide.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="9fd05-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9fd05-116">Pre-requisites</span></span>

- <span data-ttu-id="9fd05-117">[SDK de .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2) o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9fd05-117">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) or later</span></span>
- <span data-ttu-id="9fd05-118">(Opcional) [Visual Studio 2017 o 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="9fd05-118">(Optional) [Visual Studio 2017 or 2019](https://visualstudio.microsoft.com/vs/)</span></span>
- [<span data-ttu-id="9fd05-119">CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="9fd05-119">ML.NET CLI</span></span>](../how-to-guides/install-ml-net-cli.md)

<span data-ttu-id="9fd05-120">Puede ejecutar los proyectos del código de C# generado desde Visual Studio o con `dotnet run` (CLI de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="9fd05-120">You can either run the generated C# code projects from Visual Studio or with `dotnet run` (.NET Core CLI).</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="9fd05-121">Preparar los datos</span><span class="sxs-lookup"><span data-stu-id="9fd05-121">Prepare your data</span></span>

<span data-ttu-id="9fd05-122">Vamos a usar un conjunto de datos existente utilizado para un escenario de "análisis de sentimiento", que es una tarea de aprendizaje automático de clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="9fd05-122">We are going to use an existing dataset used for a 'Sentiment Analysis' scenario, which is a binary classification machine learning task.</span></span> <span data-ttu-id="9fd05-123">Puede usar su propio conjunto de datos de forma similar, y el modelo y el código se generarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9fd05-123">You can use your own dataset in a similar way, and the model and code will be generated for you.</span></span>

1. <span data-ttu-id="9fd05-124">Descargue el [archivo ZIP del conjunto de datos UCI Sentiment Labeled Sentences (vea la referencia en la nota siguiente)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) y descomprímalo en la carpeta de su elección.</span><span class="sxs-lookup"><span data-stu-id="9fd05-124">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip it on any folder you choose.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9fd05-125">Los conjuntos de datos que se utilizan en este tutorial provienen de "From Group to Individual Labels using Deep Features", Kotzias et. al.,</span><span class="sxs-lookup"><span data-stu-id="9fd05-125">The datasets this tutorial uses a dataset from the 'From Group to Individual Labels using Deep Features', Kotzias et al,.</span></span> <span data-ttu-id="9fd05-126">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span><span class="sxs-lookup"><span data-stu-id="9fd05-126">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="9fd05-127">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml ].</span><span class="sxs-lookup"><span data-stu-id="9fd05-127">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="9fd05-128">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="9fd05-128">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

2. <span data-ttu-id="9fd05-129">Copie el archivo `yelp_labelled.txt` en cualquier carpeta que haya creado anteriormente (como `/cli-test`).</span><span class="sxs-lookup"><span data-stu-id="9fd05-129">Copy the `yelp_labelled.txt` file into any folder you previously created (such as `/cli-test`).</span></span>

3. <span data-ttu-id="9fd05-130">Abra su símbolo del sistema preferido y muévalo a la carpeta donde copió el archivo del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="9fd05-130">Open your preferred command prompt and move to the folder where you copied the dataset file.</span></span> <span data-ttu-id="9fd05-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9fd05-131">For example:</span></span>

    ```console
    cd /cli-test
    ```

    <span data-ttu-id="9fd05-132">Con cualquier editor de texto como Visual Studio Code, puede abrir y explorar el archivo del conjunto de datos `yelp_labelled.txt`.</span><span class="sxs-lookup"><span data-stu-id="9fd05-132">Using any text editor such as Visual Studio Code, you can open, and explore the `yelp_labelled.txt` dataset file.</span></span> <span data-ttu-id="9fd05-133">Puede ver la estructura de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9fd05-133">You can see that the structure is:</span></span>

    - <span data-ttu-id="9fd05-134">El archivo no tiene encabezado.</span><span class="sxs-lookup"><span data-stu-id="9fd05-134">The file has no header.</span></span> <span data-ttu-id="9fd05-135">Usará el índice de la columna.</span><span class="sxs-lookup"><span data-stu-id="9fd05-135">You will use the column's index.</span></span>

    - <span data-ttu-id="9fd05-136">Solo hay dos columnas:</span><span class="sxs-lookup"><span data-stu-id="9fd05-136">There are just two columns:</span></span>

        | <span data-ttu-id="9fd05-137">Texto (índice de la columna 0)</span><span class="sxs-lookup"><span data-stu-id="9fd05-137">Text (Column index 0)</span></span> | <span data-ttu-id="9fd05-138">Etiqueta (índice de la columna 1)</span><span class="sxs-lookup"><span data-stu-id="9fd05-138">Label (Column index 1)</span></span>|
        |--------------------------|-------|
        | <span data-ttu-id="9fd05-139">¡Anda! Me encantó el lugar.</span><span class="sxs-lookup"><span data-stu-id="9fd05-139">Wow... Loved this place.</span></span> | <span data-ttu-id="9fd05-140">1</span><span class="sxs-lookup"><span data-stu-id="9fd05-140">1</span></span> |
        | <span data-ttu-id="9fd05-141">La corteza no es buena.</span><span class="sxs-lookup"><span data-stu-id="9fd05-141">Crust is not good.</span></span> | <span data-ttu-id="9fd05-142">0</span><span class="sxs-lookup"><span data-stu-id="9fd05-142">0</span></span> |
        | <span data-ttu-id="9fd05-143">No es sabrosa y la textura era simplemente desagradable.</span><span class="sxs-lookup"><span data-stu-id="9fd05-143">Not tasty and the texture was just nasty.</span></span> | <span data-ttu-id="9fd05-144">0</span><span class="sxs-lookup"><span data-stu-id="9fd05-144">0</span></span> |
        | <span data-ttu-id="9fd05-145">...MUCHAS MÁS FILAS DE TEXTO...</span><span class="sxs-lookup"><span data-stu-id="9fd05-145">...MANY MORE TEXT ROWS...</span></span> | <span data-ttu-id="9fd05-146">...(1 o 0)...</span><span class="sxs-lookup"><span data-stu-id="9fd05-146">...(1 or 0)...</span></span> |

    <span data-ttu-id="9fd05-147">Asegúrese de cerrar el archivo del conjunto de datos desde el editor.</span><span class="sxs-lookup"><span data-stu-id="9fd05-147">Make sure you close the dataset file from the editor.</span></span>

    <span data-ttu-id="9fd05-148">Ya está listo para empezar a usar la CLI en este escenario de "análisis de sentimiento".</span><span class="sxs-lookup"><span data-stu-id="9fd05-148">Now, you are ready to start using the CLI for this 'Sentiment Analysis' scenario.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9fd05-149">Al finalizar este tutorial, también puede probar con sus propios conjuntos de datos, siempre que estén listos para usarse en cualquiera de las tareas de ML compatibles actualmente con la versión preliminar de la CLI de ML.NET, que son *"Clasificación binaria", "Clasificación multiclase" y "Regresión"* ).</span><span class="sxs-lookup"><span data-stu-id="9fd05-149">After finishing this tutorial you can also try with your own datasets as long as they are ready to be used for any of the ML tasks currently supported by the ML.NET CLI Preview which are *'Binary Classification', 'Multi-class Classification' and 'Regression'*).</span></span>

## <a name="run-the-mlnet-auto-train-command"></a><span data-ttu-id="9fd05-150">Ejecutar el comando "mlnet auto-train"</span><span class="sxs-lookup"><span data-stu-id="9fd05-150">Run the 'mlnet auto-train' command</span></span>

1. <span data-ttu-id="9fd05-151">Ejecute el siguiente comando de la CLI de ML.NET:</span><span class="sxs-lookup"><span data-stu-id="9fd05-151">Run the following ML.NET CLI command:</span></span>

    ```console
    mlnet auto-train --task binary-classification --dataset "yelp_labelled.txt" --label-column-index 1 --has-header false --max-exploration-time 10
    ```

    <span data-ttu-id="9fd05-152">Este comando ejecuta el **comando `mlnet auto-train`** :</span><span class="sxs-lookup"><span data-stu-id="9fd05-152">This command runs the **`mlnet auto-train` command**:</span></span>
    - <span data-ttu-id="9fd05-153">para una **tarea de ML** de tipo **`binary-classification`**</span><span class="sxs-lookup"><span data-stu-id="9fd05-153">for an **ML task** of type **`binary-classification`**</span></span>
    - <span data-ttu-id="9fd05-154">usa el **archivo del conjunto de datos `yelp_labelled.txt`** como conjunto de datos de entrenamiento y pruebas (internamente la CLI utilizará la validación cruzada o lo dividirá en dos conjuntos de datos: uno para el entrenamiento y otro para las pruebas)</span><span class="sxs-lookup"><span data-stu-id="9fd05-154">uses the **dataset file `yelp_labelled.txt`** as training and testing dataset (internally the CLI will either use cross-validation or split it in two datasets, one for training and one for testing)</span></span>
    - <span data-ttu-id="9fd05-155">donde la **columna de objetivo/destino** que desea predecir (comúnmente denominada **"etiqueta"** ) es la **columna con el índice 1** (que es la segunda columna, ya que el índice es de base cero)</span><span class="sxs-lookup"><span data-stu-id="9fd05-155">where the **objective/target column** you want to predict (commonly called **'label'**) is the **column with index 1** (that is the second column, since the index is zero-based)</span></span>
    - <span data-ttu-id="9fd05-156">**no usa un encabezado de archivo** con nombres de columna, puesto que este archivo de conjunto de datos concreto no tiene un encabezado</span><span class="sxs-lookup"><span data-stu-id="9fd05-156">does **not use a file header** with column names since this particular dataset file doesn't have a header</span></span>
    - <span data-ttu-id="9fd05-157">el **tiempo de exploración dirigida** para el experimento es de **10 segundos**</span><span class="sxs-lookup"><span data-stu-id="9fd05-157">the **targeted exploration time** for the experiment is **10 seconds**</span></span>

    <span data-ttu-id="9fd05-158">Verá la salida de la CLI, similar a:</span><span class="sxs-lookup"><span data-stu-id="9fd05-158">You will see output from the CLI, similar to:</span></span>

    <!-- markdownlint-disable MD023 MD025 -->

    # <a name="windowstabwindows"></a>[<span data-ttu-id="9fd05-159">Windows</span><span class="sxs-lookup"><span data-stu-id="9fd05-159">Windows</span></span>](#tab/windows)

    ![Comando de entrenamiento automático de la CLI de ML.NET en PowerShell](./media/mlnet-cli/mlnet-auto-train-binary-classification-powershell.gif)

    # <a name="macos-bashtabmacosbash"></a>[<span data-ttu-id="9fd05-161">Bash de macOS</span><span class="sxs-lookup"><span data-stu-id="9fd05-161">macOS Bash</span></span>](#tab/macosbash)

    ![Comando de entrenamiento automático de la CLI de ML.NET en PowerShell](./media/mlnet-cli/mlnet-auto-train-binary-classification-bash.gif)

    <span data-ttu-id="9fd05-163">En este caso en concreto, en solo 10 segundos y con el pequeño conjunto de datos proporcionado, la herramienta de la CLI fue capaz de ejecutar varias iteraciones, lo que implica entrenar varias veces según diferentes combinaciones de algoritmos o la configuración con diferentes transformaciones de datos internos e hiperparámetros del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="9fd05-163">In this particular case, in only 10 seconds and with the small dataset provided, the CLI tool was able to run quite a few iterations, meaning training multiple times based on different combinations of algorithms/configuration with different internal data transformations and algorithm's hyper-parameters.</span></span>

    <span data-ttu-id="9fd05-164">Por último, el modelo de "mejor calidad" que se encontró en 10 segundos es un modelo que usa un instructor o algoritmo concreto con cualquier configuración específica.</span><span class="sxs-lookup"><span data-stu-id="9fd05-164">Finally, the "best quality" model found in 10 seconds is a model using a particular trainer/algorithm with any specific configuration.</span></span> <span data-ttu-id="9fd05-165">Según el tiempo de exploración, el comando puede generar un resultado diferente.</span><span class="sxs-lookup"><span data-stu-id="9fd05-165">Depending on the exploration time, the command can produce a different result.</span></span> <span data-ttu-id="9fd05-166">La selección se basa en las diversas métricas que se muestran, como `Accuracy`.</span><span class="sxs-lookup"><span data-stu-id="9fd05-166">The selection is based on the multiple metrics shown, such as `Accuracy`.</span></span>

    <span data-ttu-id="9fd05-167">**Descripción de las métricas de calidad del modelo**</span><span class="sxs-lookup"><span data-stu-id="9fd05-167">**Understanding the model's quality metrics**</span></span>

    <span data-ttu-id="9fd05-168">La primera métrica y la más sencilla para evaluar un modelo de clasificación binaria es la precisión, la cual es muy fácil de entender.</span><span class="sxs-lookup"><span data-stu-id="9fd05-168">The first and easiest metric to evaluate a binary-classification model is the accuracy, which is simple to understand.</span></span> <span data-ttu-id="9fd05-169">"La precisión es la proporción de predicciones correctas con un conjunto de datos de prueba".</span><span class="sxs-lookup"><span data-stu-id="9fd05-169">"Accuracy is the proportion of correct predictions with a test data set.".</span></span> <span data-ttu-id="9fd05-170">Cuanto más cerca del 100 % (1,00), mejor.</span><span class="sxs-lookup"><span data-stu-id="9fd05-170">The closer to 100% (1.00), the better.</span></span>

    <span data-ttu-id="9fd05-171">Sin embargo, hay casos en los que solo medir con la métrica de precisión no es suficiente, especialmente cuando la etiqueta (0 y 1 en este caso) está desequilibrada en el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="9fd05-171">However, there are cases where just measuring with the Accuracy metric is not enough, especially when the label (0 and 1 in this case) is unbalanced in the test dataset.</span></span>

    <span data-ttu-id="9fd05-172">Para ver métricas adicionales e **información más detallada acerca de las métricas**, como la precisión, AUC, AUCPR y la puntuación F1 utilizada para evaluar los distintos modelos, lea [Descripción de las métricas de ML.NET](../resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="9fd05-172">For additional metrics and more **detailed information about the metrics** such as Accuracy, AUC, AUCPR, and F1-score used to evaluate the different models, see [Understanding ML.NET metrics](../resources/metrics.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9fd05-173">Puede probar este mismo conjunto de datos y especificar unos minutos para `--max-exploration-time` (por ejemplo, tres minutos, por lo que se especifican 180 segundos) que encontrará un "mejor modelo" con una configuración de canalización de entrenamiento distinta para este conjunto de datos (que es bastante pequeño: 1000 filas).</span><span class="sxs-lookup"><span data-stu-id="9fd05-173">You can try this very same dataset and specify a few minutes for `--max-exploration-time` (for instance three minutes so you specify 180 seconds) which will find a better "best model" for you with a different training pipeline configuration for this dataset (which is pretty small, 1000 rows).</span></span>

    <span data-ttu-id="9fd05-174">Para encontrar un modelo de "mejor o buena calidad" que sea un "modelo listo para la producción" dirigido a conjuntos de datos grandes, debe realizar experimentos con la CLI normalmente especificando mucho más tiempo de exploración según el tamaño del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="9fd05-174">In order to find a "best/good quality" model that is a "production-ready model" targeting larger datasets, you should make experiments with the CLI usually specifying much more exploration time depending on the size of the dataset.</span></span> <span data-ttu-id="9fd05-175">De hecho, en muchos casos es posible que necesite varias horas de exploración, sobre todo si el conjunto de datos es de gran tamaño en filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="9fd05-175">In fact, in many cases you might require multiple hours of exploration time especially if the dataset is large on rows and columns.</span></span>

1. <span data-ttu-id="9fd05-176">La ejecución del comando anterior ha generado los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="9fd05-176">The previous command execution has generated the following assets:</span></span>

    - <span data-ttu-id="9fd05-177">Un .zip de modelo serializado ("mejor modelo") listo para usarse.</span><span class="sxs-lookup"><span data-stu-id="9fd05-177">A serialized model .zip ("best model") ready to use.</span></span>
    - <span data-ttu-id="9fd05-178">El código de C# para ejecutar o calificar dicho modelo generado (para realizar predicciones en las aplicaciones del usuario final con ese modelo).</span><span class="sxs-lookup"><span data-stu-id="9fd05-178">C# code to run/score that generated model (To make predictions in your end-user apps with that model).</span></span>
    - <span data-ttu-id="9fd05-179">El código de entrenamiento de C# utilizado para generar ese modelo (con fines de aprendizaje).</span><span class="sxs-lookup"><span data-stu-id="9fd05-179">C# training code used to generate that model (Learning purposes).</span></span>
    - <span data-ttu-id="9fd05-180">Un archivo de registro con todas las iteraciones exploradas con información detallada específica acerca de cada algoritmo que se ha intentado con su combinación de hiperparámetros y transformaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="9fd05-180">A log file with all the iterations explored having specific detailed information about each algorithm tried with its combination of hyper-parameters and data transformations.</span></span>

    <span data-ttu-id="9fd05-181">Los dos primeros recursos (modelo de archivo ZIP y el código de C# para ejecutar ese modelo) se pueden usar directamente en las aplicaciones de usuario final (aplicación web ASP.NET Core, servicios, aplicación de escritorio, etc.) para realizar predicciones con dicho modelo de ML generado.</span><span class="sxs-lookup"><span data-stu-id="9fd05-181">The first two assets (.ZIP file model and C# code to run that model) can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

    <span data-ttu-id="9fd05-182">El tercer recurso, el código de aprendizaje, le muestra el código de la API de ML.NET que utilizó la CLI para entrenar el modelo generado, de modo que pueda investigar qué hiperparámetros y algoritmos o instructores específicos seleccionó la CLI.</span><span class="sxs-lookup"><span data-stu-id="9fd05-182">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate what specific trainer/algorithm and hyper-parameters were selected by the CLI.</span></span>

<span data-ttu-id="9fd05-183">Esos recursos enumerados se explican en los pasos siguientes del tutorial.</span><span class="sxs-lookup"><span data-stu-id="9fd05-183">Those enumerated assets are explained in the following steps of the tutorial.</span></span>

## <a name="explore-the-generated-c-code-to-use-for-running-the-model-to-make-predictions"></a><span data-ttu-id="9fd05-184">Explorar el código de C# generado que se usará para ejecutar el modelo a fin de realizar predicciones</span><span class="sxs-lookup"><span data-stu-id="9fd05-184">Explore the generated C# code to use for running the model to make predictions</span></span>

1. <span data-ttu-id="9fd05-185">En Visual Studio (2017 o 2019), abra la solución generada en la carpeta denominada `SampleBinaryClassification` dentro de la carpeta de destino original (en el tutorial se denominaba `/cli-test`).</span><span class="sxs-lookup"><span data-stu-id="9fd05-185">In Visual Studio (2017 or 2019) open the solution generated in the folder named `SampleBinaryClassification` within your original destination folder (in the tutorial was named `/cli-test`).</span></span> <span data-ttu-id="9fd05-186">Debería ver una solución similar a esta:</span><span class="sxs-lookup"><span data-stu-id="9fd05-186">You should see a solution similar to:</span></span>

    > [!NOTE]
    > <span data-ttu-id="9fd05-187">En el tutorial, se recomienda usar Visual Studio, pero también puede explorar el código de C# generado (dos proyectos) con cualquier editor de texto y ejecutar la aplicación de consola generada con la `dotnet CLI` en macOS, máquina Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="9fd05-187">In the tutorial we suggest to use Visual Studio, but you can also explore the generated C# code (two projects) with any text editor and run the generated console app with the `dotnet CLI` on macOS, Linux or Windows machine.</span></span>

    ![Solución de VS generada por la CLI](./media/mlnet-cli/generated-csharp-solution-detailed.png)

    - <span data-ttu-id="9fd05-189">La **biblioteca de clases** generada que contiene el modelo serializado de ML (archivo .zip) y las clases de datos (modelo de datos) es algo que puede usar directamente en la aplicación del usuario final, incluso haciendo referencia directamente a esa biblioteca de clases (o moviendo el código, como desee).</span><span class="sxs-lookup"><span data-stu-id="9fd05-189">The generated **class library** containing the serialized ML model (.zip file) and the data classes (data models) is something you can directly use in your end-user application, even by directly referencing that class library (or moving the code, as you prefer).</span></span>
    - <span data-ttu-id="9fd05-190">La **aplicación de consola** generada contiene un código de ejecución que debe revisar. Después, normalmente reutiliza el "código de puntuación" (el código que ejecuta el modelo de ML para realizar predicciones) moviendo ese código sencillo (unas cuantas líneas) a la aplicación del usuario final en la que quiere realizar las predicciones.</span><span class="sxs-lookup"><span data-stu-id="9fd05-190">The generated **console app** contains execution code that you must review and then you usually reuse the 'scoring code' (code that runs the ML model to make predictions) by moving that simple code (just a few lines) to your end-user application where you want to make the predictions.</span></span>

1. <span data-ttu-id="9fd05-191">Abra los archivos de clase **ModelInput.cs** y **ModelOutput.cs** en el proyecto de la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="9fd05-191">Open the **ModelInput.cs** and **ModelOutput.cs** class files within the class library project.</span></span> <span data-ttu-id="9fd05-192">Verá que estas clases son "clases de datos" o clases POCO que se usan para almacenar datos.</span><span class="sxs-lookup"><span data-stu-id="9fd05-192">You will see that these classes are 'data classes' or POCO classes used to hold data.</span></span> <span data-ttu-id="9fd05-193">Se trata de "código reutilizable", pero resulta útil generarlo si el conjunto de datos tiene decenas o incluso centenares de columnas.</span><span class="sxs-lookup"><span data-stu-id="9fd05-193">It is 'boilerplate code' but useful to have it generated if your dataset has tens or even hundreds of columns.</span></span>
    - <span data-ttu-id="9fd05-194">La clase `ModelInput` se usa al leer los datos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="9fd05-194">The `ModelInput` class is used when reading data from the dataset.</span></span>
    - <span data-ttu-id="9fd05-195">La clase `ModelOutput` se utiliza para obtener el resultado de la predicción (datos de predicción).</span><span class="sxs-lookup"><span data-stu-id="9fd05-195">The `ModelOutput` class is used to get the prediction result (prediction data).</span></span>

1. <span data-ttu-id="9fd05-196">Abra el archivo Program.cs y explore el código.</span><span class="sxs-lookup"><span data-stu-id="9fd05-196">Open the Program.cs file and explore the code.</span></span> <span data-ttu-id="9fd05-197">En unas cuantas líneas, podrá ejecutar el modelo y realizar una predicción de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9fd05-197">In just a few lines, you are able to run the model and make a sample prediction.</span></span>

    ```csharp
    static void Main(string[] args)
    {
        MLContext mlContext = new MLContext();

        // Training code used by ML.NET CLI and AutoML to generate the model
        //ModelBuilder.CreateModel();

        ITransformer mlModel = mlContext.Model.Load(MODEL_FILEPATH, out DataViewSchema inputSchema);
        var predEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // Create sample data to do a single prediction with it
        ModelInput sampleData = CreateSingleDataSample(mlContext, DATA_FILEPATH);

        // Try a single prediction
        ModelOutput predictionResult = predEngine.Predict(sampleData);

        Console.WriteLine($"Single Prediction --> Actual value: {sampleData.Label} | Predicted value: {predictionResult.Prediction}");
    }
    ```

- <span data-ttu-id="9fd05-198">La primera línea de código crea simplemente un objeto `MLContext` necesario cada vez que se ejecuta el código de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="9fd05-198">The first line of code simply creates an `MLContext` object needed whenever you run ML.NET code.</span></span>

- <span data-ttu-id="9fd05-199">La segunda línea de código está comentada porque no es necesario entrenar el modelo debido a que la herramienta de la CLI ya lo ha entrenado y guardado en el archivo ZIP serializado del modelo.</span><span class="sxs-lookup"><span data-stu-id="9fd05-199">The second line of code is commented because you don't need to train the model since it was already trained for you by the CLI tool and saved into the model's serialized .ZIP file.</span></span> <span data-ttu-id="9fd05-200">Pero si desea ver *"cómo la CLI entrenó el modelo"* , puede quitar la marca del comentario en esa línea y ejecutar o depurar el código de aprendizaje para ese modelo particular de ML.</span><span class="sxs-lookup"><span data-stu-id="9fd05-200">But if you want to see *"how the model was trained"* by the CLI, you could uncomment that line and run/debug the training code used for that particular ML model.</span></span>

- <span data-ttu-id="9fd05-201">En la tercera línea de código, cargue el modelo desde el archivo ZIP del modelo serializado con la API `mlContext.Model.Load()` proporcionando la ruta de acceso al archivo ZIP de ese modelo.</span><span class="sxs-lookup"><span data-stu-id="9fd05-201">In the third line of code, you load the model from the serialized model .ZIP file with the `mlContext.Model.Load()` API by providing the path to that model .ZIP file.</span></span>

- <span data-ttu-id="9fd05-202">En la cuarta línea de código, cree el objeto `PredictionEngine` con la API `mlContext.Model.CreatePredictionEngine<TSrc,TDst>(ITransformer mlModel)`.</span><span class="sxs-lookup"><span data-stu-id="9fd05-202">In the fourth line of code you load create the `PredictionEngine` object with the `mlContext.Model.CreatePredictionEngine<TSrc,TDst>(ITransformer mlModel)` API.</span></span> <span data-ttu-id="9fd05-203">Necesitará el objeto `PredictionEngine` cada vez que desee realizar una predicción dirigida a una única muestra de datos (en este caso, un fragmento único de texto para su opinión).</span><span class="sxs-lookup"><span data-stu-id="9fd05-203">You need the `PredictionEngine` object whenever you want to make a prediction targeting a single sample of data (In this case, a single piece of text to predict its sentiment).</span></span>

- <span data-ttu-id="9fd05-204">La quinta línea de código es donde creará esos *datos de ejemplo únicos* que se usarán para la predicción mediante una llamada a la función `CreateSingleDataSample()`.</span><span class="sxs-lookup"><span data-stu-id="9fd05-204">The fifth line of code is where you create that *single sample data* to be used for the prediction by calling the function `CreateSingleDataSample()`.</span></span> <span data-ttu-id="9fd05-205">Dado que la herramienta de la CLI no sabe qué tipo de datos de ejemplo se usarán, dentro de esa función se carga la primera fila del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="9fd05-205">Since the CLI tool doesn't know what kind of sample data to use, within that function it is loading the first row of the dataset.</span></span> <span data-ttu-id="9fd05-206">Sin embargo, en este caso también puede crear sus propios datos "codificados de forma rígida", en lugar de la implementación actual de la función `CreateSingleDataSample()` mediante la actualización de este código más sencillo implementando esa función:</span><span class="sxs-lookup"><span data-stu-id="9fd05-206">However, for this case you can also create you own 'hard-coded' data instead of the current implementation of the `CreateSingleDataSample()` function by updating this simpler code implementing that function:</span></span>

    ```csharp
    private static ModelInput CreateSingleDataSample()
    {
        ModelInput sampleForPrediction = new ModelInput() { Col0 = "The ML.NET CLI is great for getting started. Very cool!", Label = true };
        return sampleForPrediction;
    }
    ```

1. <span data-ttu-id="9fd05-207">Ejecute el proyecto, ya sea mediante los datos de ejemplo originales cargados desde la primera fila del conjunto de datos o proporcionando sus propios datos de ejemplo codificados de forma rígida y personalizados.</span><span class="sxs-lookup"><span data-stu-id="9fd05-207">Run the project, either using the original sample data loaded from the first row of the dataset or by providing your own custom hard-coded sample data.</span></span> <span data-ttu-id="9fd05-208">Debería obtener una predicción comparable a esta:</span><span class="sxs-lookup"><span data-stu-id="9fd05-208">You should get a prediction comparable to:</span></span>

    # <a name="windowstabwindows"></a>[<span data-ttu-id="9fd05-209">Windows</span><span class="sxs-lookup"><span data-stu-id="9fd05-209">Windows</span></span>](#tab/windows)

    <span data-ttu-id="9fd05-210">Ejecute la aplicación de consola desde Visual Studio presionando F5 (botón de reproducción):</span><span class="sxs-lookup"><span data-stu-id="9fd05-210">Run the console app from Visual Studio by hitting F5 (Play button):</span></span>

    ![Comando de entrenamiento automático de la CLI de ML.NET en PowerShell](./media/mlnet-cli/sample-cli-prediction-execution.png)<span data-ttu-id="9fd05-212">)</span><span class="sxs-lookup"><span data-stu-id="9fd05-212">)</span></span>

    # <a name="macos-bashtabmacosbash"></a>[<span data-ttu-id="9fd05-213">Bash de macOS</span><span class="sxs-lookup"><span data-stu-id="9fd05-213">macOS Bash</span></span>](#tab/macosbash)

    <span data-ttu-id="9fd05-214">Ejecute la aplicación de consola desde el símbolo del sistema escribiendo los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="9fd05-214">Run the console app from the command-prompt by typing the following commands:</span></span>

     ```bash
     cd SampleBinaryClassification
     cd SampleBinaryClassification.ConsoleApp

     dotnet run
     ```

    ![Comando de entrenamiento automático de la CLI de ML.NET en PowerShell](./media/mlnet-cli/sample-cli-prediction-execution-bash.png)<span data-ttu-id="9fd05-216">)</span><span class="sxs-lookup"><span data-stu-id="9fd05-216">)</span></span>

    ---

1. <span data-ttu-id="9fd05-217">Pruebe a cambiar los datos de ejemplo codificados de forma rígida a otras frases con diferentes opiniones y vea cómo el modelo predice opiniones positivas o negativas.</span><span class="sxs-lookup"><span data-stu-id="9fd05-217">Try changing the hard-coded sample data to other sentences with different sentiment and see how the model predicts positive or negative sentiment.</span></span>

## <a name="infuse-your-end-user-applications-with-ml-model-predictions"></a><span data-ttu-id="9fd05-218">Incorporar las aplicaciones del usuario final con predicciones del modelo de ML</span><span class="sxs-lookup"><span data-stu-id="9fd05-218">Infuse your end-user applications with ML model predictions</span></span>

<span data-ttu-id="9fd05-219">Puede usar un "código de puntuación del modelo de ML" similar para ejecutar el modelo en la aplicación del usuario final y realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="9fd05-219">You can use similar 'ML model scoring code' to run the model in your end-user application and make predictions.</span></span>

<span data-ttu-id="9fd05-220">Por ejemplo, podría mover directamente ese código a cualquier aplicación de escritorio de Windows como **WPF** y **WinForms** y ejecutar el modelo de la misma manera que se realizó en la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="9fd05-220">For instance, you could directly move that code to any Windows desktop application such as **WPF** and **WinForms** and run the model in the same way than it was done in the console app.</span></span>

<span data-ttu-id="9fd05-221">Sin embargo, la forma de implementar esas líneas de código para ejecutar un modelo de ML debe optimizarse (es decir, copie en caché el archivo .zip del modelo y cárguelo una vez) y debe tener objetos singleton en lugar de crearlos en cada solicitud, especialmente si la aplicación debe ser escalable como una aplicación web o un servicio distribuido, tal como se explica en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="9fd05-221">However, the way you implement those lines of code to run an ML model should be optimized (that is, cache the model .zip file and load it once) and have singleton objects instead of creating them on every request, especially if your application needs to be scalable such as a web application or distributed service, as explained in the following section.</span></span>

### <a name="running-mlnet-models-in-scalable-aspnet-core-web-apps-and-services-multi-threaded-apps"></a><span data-ttu-id="9fd05-222">Ejecución de modelos de ML.NET en aplicaciones web y servicios escalables de ASP.NET Core (aplicaciones multiproceso)</span><span class="sxs-lookup"><span data-stu-id="9fd05-222">Running ML.NET models in scalable ASP.NET Core web apps and services (multi-threaded apps)</span></span>

<span data-ttu-id="9fd05-223">La creación del objeto de modelo (`ITransformer` cargado desde el archivo .zip de un modelo) y el objeto `PredictionEngine` debe optimizarse especialmente cuando se ejecuta en aplicaciones web escalables y servicios distribuidos.</span><span class="sxs-lookup"><span data-stu-id="9fd05-223">The creation of the model object (`ITransformer` loaded from a model's .zip file) and the `PredictionEngine` object should be optimized especially when running on scalable web apps and distributed services.</span></span> <span data-ttu-id="9fd05-224">En el primer caso, el objeto de modelo (`ITransformer`), la optimización es sencilla.</span><span class="sxs-lookup"><span data-stu-id="9fd05-224">For the first case, the model object (`ITransformer`) the optimization is straightforward.</span></span> <span data-ttu-id="9fd05-225">Puesto que el objeto `ITransformer` es seguro para subprocesos, puede copiar en caché el objeto como un singleton o un objeto estático para cargar el modelo una vez.</span><span class="sxs-lookup"><span data-stu-id="9fd05-225">Since the `ITransformer` object is thread-safe, you can cache the object as a singleton or static object so you load the model once.</span></span>

<span data-ttu-id="9fd05-226">En el segundo objeto, el objeto `PredictionEngine`, no es tan fácil porque el objeto `PredictionEngine` no es seguro para subprocesos, por lo que no se puede crear una instancia de este objeto como singleton u objeto estático en una aplicación de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9fd05-226">For the second object, the `PredictionEngine` object, it is not so easy because the `PredictionEngine` object is not thread-safe, therefore you cannot instantiate this object as singleton or static object in an ASP.NET Core app.</span></span> <span data-ttu-id="9fd05-227">Este problema de escalabilidad y seguridad para subprocesos se describe detalladamente en esta [entrada de blog](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span><span class="sxs-lookup"><span data-stu-id="9fd05-227">This thread-safe and scalability problem is deeply discussed in this [Blog Post](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span>

<span data-ttu-id="9fd05-228">Sin embargo, las cosas ahora son mucho más fáciles de lo que se explica en esa entrada de blog.</span><span class="sxs-lookup"><span data-stu-id="9fd05-228">However, things got a lot easier for you than what's explained in that blog post.</span></span> <span data-ttu-id="9fd05-229">Hemos trabajado en un enfoque más sencillo para usted y hemos creado un buen **"paquete de integración de .NET Core"** que puede usar fácilmente en sus servicios y aplicaciones de ASP.NET Core registrándolos en los servicios de DI de la aplicación (servicios de inserción de dependencias) y usándolos directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="9fd05-229">We worked on a simpler approach for you and have created a nice **'.NET Core Integration Package'** that you can  easily use in your ASP.NET Core apps and services by registering it in the application DI services (Dependency Injection services) and then directly use it from your code.</span></span> <span data-ttu-id="9fd05-230">Consulte el siguiente tutorial y ejemplo para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="9fd05-230">Check the following tutorial and example for doing that:</span></span>

- [<span data-ttu-id="9fd05-231">Tutorial: Ejecución de modelos de ML.NET en aplicaciones web escalables de ASP.NET Core y WebAPI</span><span class="sxs-lookup"><span data-stu-id="9fd05-231">Tutorial: Running ML.NET models on scalable ASP.NET Core web apps and WebAPIs</span></span>](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [<span data-ttu-id="9fd05-232">Ejemplo: Modelo de ML.NET escalable en ASP.NET Core WebAPI</span><span class="sxs-lookup"><span data-stu-id="9fd05-232">Sample: Scalable ML.NET model on ASP.NET Core WebAPI</span></span>](https://aka.ms/mlnet-sample-netcoreintegrationpkg)

## <a name="explore-the-generated-c-code-that-was-used-to-train-the-best-quality-model"></a><span data-ttu-id="9fd05-233">Explorar el código de C# generado que se usó para entrenar el modelo de "mejor calidad"</span><span class="sxs-lookup"><span data-stu-id="9fd05-233">Explore the generated C# code that was used to train the "best quality" model</span></span>

<span data-ttu-id="9fd05-234">Para fines de aprendizaje más avanzados, también puede explorar el código de C# generado que utilizó la herramienta de la CLI para entrenar el modelo generado.</span><span class="sxs-lookup"><span data-stu-id="9fd05-234">For more advanced learning purposes, you can also explore the generated C# code that was used by the CLI tool to train the generated model.</span></span>

<span data-ttu-id="9fd05-235">Dicho "código de modelo de entrenamiento" se genera actualmente en la clase personalizada generada denominada `ModelBuilder` para que pueda investigar el código de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="9fd05-235">That 'training model code' is currently generated in the custom class generated named `ModelBuilder` so you can investigate that training code.</span></span>

<span data-ttu-id="9fd05-236">Más importante aún, para este escenario en particular (modelo de análisis de sentimiento) también puede comparar dicho código de entrenamiento generado con el código que se explica en el tutorial siguiente:</span><span class="sxs-lookup"><span data-stu-id="9fd05-236">More importantly, for this particular scenario (Sentiment Analysis model) you can also compare that generated training code with the code explained in the following tutorial:</span></span>

- <span data-ttu-id="9fd05-237">Comparación: [Tutorial: Uso de ML.NET en un escenario de clasificación binaria de análisis de sentimiento](sentiment-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="9fd05-237">Compare: [Tutorial: Use ML.NET in a sentiment analysis binary classification scenario](sentiment-analysis.md).</span></span>

<span data-ttu-id="9fd05-238">Resulta interesante comparar el algoritmo elegido y la configuración de canalización en el tutorial con el código generado por la herramienta de la CLI.</span><span class="sxs-lookup"><span data-stu-id="9fd05-238">It is interesting to compare the chosen algorithm and pipeline configuration in the tutorial with the code generated by the CLI tool.</span></span> <span data-ttu-id="9fd05-239">Según cuánto tiempo dedique a iterar y buscar modelos mejores, el algoritmo elegido podría ser diferente, junto con su configuración de canalización e hiperparámetros determinados.</span><span class="sxs-lookup"><span data-stu-id="9fd05-239">Depending on how much time you spend iterating and searching for better models, the chosen algorithm might be different along with its particular hyper-parameters and pipeline configuration.</span></span>

<span data-ttu-id="9fd05-240">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="9fd05-240">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="9fd05-241">Preparar los datos para la tarea de ML seleccionada (problema para resolver)</span><span class="sxs-lookup"><span data-stu-id="9fd05-241">Prepare your data for the selected ML task (problem to solve)</span></span>
> - <span data-ttu-id="9fd05-242">Ejecutar el comando "mlnet auto-train" en la herramienta de la CLI</span><span class="sxs-lookup"><span data-stu-id="9fd05-242">Run the 'mlnet auto-train' command in the CLI tool</span></span>
> - <span data-ttu-id="9fd05-243">Revisar los resultados de métrica de calidad</span><span class="sxs-lookup"><span data-stu-id="9fd05-243">Review the quality metric results</span></span>
> - <span data-ttu-id="9fd05-244">Comprender el código de C# generado para ejecutar el modelo (código para usar en la aplicación del usuario final)</span><span class="sxs-lookup"><span data-stu-id="9fd05-244">Understand the generated C# code to run the model (Code to use in your end-user app)</span></span>
> - <span data-ttu-id="9fd05-245">Explorar el código de C# generado que se usó para entrenar el modelo de "mejor calidad" (con fines de aprendizaje)</span><span class="sxs-lookup"><span data-stu-id="9fd05-245">Explore the generated C# code that was used to train the "best quality" model (Learning purposes)</span></span>

## <a name="see-also"></a><span data-ttu-id="9fd05-246">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fd05-246">See also</span></span>

- [<span data-ttu-id="9fd05-247">Automatizar el entrenamiento del modelo con la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="9fd05-247">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="9fd05-248">Tutorial: Ejecución de modelos de ML.NET en aplicaciones web escalables de ASP.NET Core y WebAPI</span><span class="sxs-lookup"><span data-stu-id="9fd05-248">Tutorial: Running ML.NET models on scalable ASP.NET Core web apps and WebAPIs</span></span>](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [<span data-ttu-id="9fd05-249">Ejemplo: Modelo de ML.NET escalable en ASP.NET Core WebAPI</span><span class="sxs-lookup"><span data-stu-id="9fd05-249">Sample: Scalable ML.NET model on ASP.NET Core WebAPI</span></span>](https://aka.ms/mlnet-sample-netcoreintegrationpkg)
- [<span data-ttu-id="9fd05-250">Guía de referencia de comandos de entrenamiento automático de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="9fd05-250">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="9fd05-251">Telemetría en la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="9fd05-251">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)

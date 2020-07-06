---
title: Referencia de comandos de la CLI de ML.NET
description: Información general, ejemplos y referencia del comando de entrenamiento automático en la herramienta de la CLI de ML.NET.
ms.date: 06/03/2020
ms.custom: mlnet-tooling
ms.openlocfilehash: 4c6cb1346c16f6162077d3414140d693de9e0d8c
ms.sourcegitcommit: 182c7b6c079ebcc0e1898dfd9e921b9ef472ea2c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2020
ms.locfileid: "85946946"
---
# <a name="the-mlnet-cli-command-reference"></a><span data-ttu-id="2295b-103">Referencia de comandos de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="2295b-103">The ML.NET CLI command reference</span></span>

<span data-ttu-id="2295b-104">Los comandos `classification`, `regression` y `recommendation` son los comandos principales proporcionados por la herramienta CLI de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="2295b-104">The `classification`, `regression`, and `recommendation` commands are the main commands provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="2295b-105">Estos comandos permiten generar modelos de ML.NET de buena calidad que pueden usarse con fines de clasificación, regresión y recomendación mediante el aprendizaje automático automatizado (AutoML) y el código C# de ejemplo para ejecutar o calificar dicho modelo.</span><span class="sxs-lookup"><span data-stu-id="2295b-105">These commands allow you to generate good quality ML.NET models for classification, regression, and recommendation models using automated machine learning (AutoML) as well as the example C# code to run/score that model.</span></span> <span data-ttu-id="2295b-106">Además, se genera código C# para entrenar el modelo y poder investigar el algoritmo y la configuración del modelo.</span><span class="sxs-lookup"><span data-stu-id="2295b-106">In addition, the C# code to train the model is generated for you to research the algorithm and settings of the model.</span></span>

> [!NOTE]
> <span data-ttu-id="2295b-107">Este tema hace referencia a la CLI de ML.NET y AutoML de ML.NET, que se encuentran actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="2295b-107">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="overview"></a><span data-ttu-id="2295b-108">Información general</span><span class="sxs-lookup"><span data-stu-id="2295b-108">Overview</span></span>

<span data-ttu-id="2295b-109">Ejemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="2295b-109">Example usage:</span></span>

```console
mlnet regression --dataset "cars.csv" --label-col price
```

<span data-ttu-id="2295b-110">Los comandos de la tarea de ML `mlnet` (`classification`, `regression` y `recommendation`) generan los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2295b-110">The `mlnet` ML task commands (`classification`, `regression`, and `recommendation`) generate the following assets:</span></span>

- <span data-ttu-id="2295b-111">Un archivo .zip de modelo serializado ("mejor modelo") listo para usarse.</span><span class="sxs-lookup"><span data-stu-id="2295b-111">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="2295b-112">Código C# para ejecutar o puntuar el modelo generado.</span><span class="sxs-lookup"><span data-stu-id="2295b-112">C# code to run/score that generated model.</span></span>
- <span data-ttu-id="2295b-113">Código de C# con el código de entrenamiento utilizado para generar ese modelo.</span><span class="sxs-lookup"><span data-stu-id="2295b-113">C# code with the training code used to generate that model.</span></span>

<span data-ttu-id="2295b-114">Los dos primeros recursos se pueden usar directamente en las aplicaciones de usuario final (aplicación web ASP.NET Core, servicios, aplicación de escritorio, y mucho más) para realizar predicciones con el modelo.</span><span class="sxs-lookup"><span data-stu-id="2295b-114">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app and more) to make predictions with the model.</span></span>

<span data-ttu-id="2295b-115">El tercer recurso, el código de entrenamiento, le muestra el código de la API de ML.NET que utilizó la CLI para entrenar el modelo generado, de modo que pueda investigar el algoritmo y configuración específicos del modelo.</span><span class="sxs-lookup"><span data-stu-id="2295b-115">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate the specific algorithm and settings of the model.</span></span>

## <a name="examples"></a><span data-ttu-id="2295b-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2295b-116">Examples</span></span>

<span data-ttu-id="2295b-117">El comando de la CLI más sencillo para un problema de clasificación (AutoML infiere la mayor parte de la configuración de los datos proporcionados):</span><span class="sxs-lookup"><span data-stu-id="2295b-117">The simplest CLI command for a classification problem (AutoML infers most of the configuration from the provided data):</span></span>

```console
mlnet classification --dataset "customer-feedback.tsv" --label-col Sentiment
```

<span data-ttu-id="2295b-118">Otro comando de CLI sencillo para un problema de regresión:</span><span class="sxs-lookup"><span data-stu-id="2295b-118">Another simple CLI command for a regression problem:</span></span>

``` console
mlnet regression --dataset "cars.csv" --label-col Price
```

<span data-ttu-id="2295b-119">Cree y entrene un modelo de clasificación con un conjunto de datos de entrenamiento, un conjunto de datos de prueba y más argumentos explícitos de personalización:</span><span class="sxs-lookup"><span data-stu-id="2295b-119">Create and train a classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
mlnet classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-col "InsuranceRisk" --cache on --train-time 600
```

## <a name="command-options"></a><span data-ttu-id="2295b-120">Opciones de comando</span><span class="sxs-lookup"><span data-stu-id="2295b-120">Command options</span></span>

<span data-ttu-id="2295b-121">Los comandos de la tarea de ML `mlnet` (`classification`, `regression` y `recommendation`) entrenan varios modelos basados en el conjunto de datos proporcionado y en las opciones de la CLI de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="2295b-121">The `mlnet` ML task commands (`classification`, `regression`, and `recommendation`) train multiple models based on the provided dataset and ML.NET CLI options.</span></span> <span data-ttu-id="2295b-122">Estos comandos también seleccionan el mejor modelo, lo guardan como un archivo .zip serializado y generan el código C# correspondiente para la puntuación y el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2295b-122">These commands also select the best model, save the model as a serialized .zip file, and generate related C# code for scoring and training.</span></span>

### <a name="classification-options"></a><span data-ttu-id="2295b-123">Opciones de clasificación</span><span class="sxs-lookup"><span data-stu-id="2295b-123">Classification options</span></span>

<span data-ttu-id="2295b-124">La ejecución de `mlnet classification` entrenará un modelo de clasificación.</span><span class="sxs-lookup"><span data-stu-id="2295b-124">Running `mlnet classification` will train a classification model.</span></span> <span data-ttu-id="2295b-125">Elija este comando si quiere que un modelo de ML clasifique los datos en dos o más clases (por ejemplo, análisis de opiniones).</span><span class="sxs-lookup"><span data-stu-id="2295b-125">Choose this command if you want an ML Model to categorize data into 2 or more classes (e.g. sentiment analysis).</span></span>

```console
mlnet classification

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="regression-options"></a><span data-ttu-id="2295b-126">Opciones de regresión</span><span class="sxs-lookup"><span data-stu-id="2295b-126">Regression options</span></span>

<span data-ttu-id="2295b-127">La ejecución de `mlnet regression` entrenará un modelo de regresión.</span><span class="sxs-lookup"><span data-stu-id="2295b-127">Running `mlnet regression` will train a regression model.</span></span> <span data-ttu-id="2295b-128">Elija este comando si quiere que un modelo de ML prediga un valor numérico (por ejemplo, predicción de precio).</span><span class="sxs-lookup"><span data-stu-id="2295b-128">Choose this command if you want an ML Model to predict a numeric value (e.g. price prediction).</span></span>

```console
mlnet classification

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="recommendation-options"></a><span data-ttu-id="2295b-129">Opciones de recomendación</span><span class="sxs-lookup"><span data-stu-id="2295b-129">Recommendation options</span></span>

<span data-ttu-id="2295b-130">La ejecución de `mlnet recommendation` entrenará un modelo de recomendación.</span><span class="sxs-lookup"><span data-stu-id="2295b-130">Running `mlnet recommendation` will train a recommendation model.</span></span>  <span data-ttu-id="2295b-131">Elija este comando si quiere que un modelo de ML recomiende elementos a los usuarios en función de las clasificaciones (por ejemplo, recomendación de productos).</span><span class="sxs-lookup"><span data-stu-id="2295b-131">Choose this command if you want an ML Model to recommend items to users based on ratings (e.g. product recommendation).</span></span>

```console
mlnet classification

--dataset <path> (REQUIRED)

--item-col <col> (REQUIRED)

--rating-col <col> (REQUIRED)

--user-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

<span data-ttu-id="2295b-132">Las opciones de entrada no válidas hacen que la herramienta de la CLI emita una lista de entradas válidas y un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="2295b-132">Invalid input options cause the CLI tool to emit a list of valid inputs and an error message.</span></span>

## <a name="dataset"></a><span data-ttu-id="2295b-133">Conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="2295b-133">Dataset</span></span>

<span data-ttu-id="2295b-134">`--dataset | -d` (cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-134">`--dataset | -d` (string)</span></span>

<span data-ttu-id="2295b-135">Este argumento proporciona la ruta de acceso del archivo a cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2295b-135">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="2295b-136">*A: el archivo de conjunto de datos entero:* si utiliza esta opción y el usuario no proporciona `--test-dataset` y `--validation-dataset`, se utilizarán internamente enfoques de validación cruzada (de K iteraciones, etc.) o división de datos automatizada para validar el modelo.</span><span class="sxs-lookup"><span data-stu-id="2295b-136">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="2295b-137">En ese caso, el usuario solo deberá proporcionar la ruta de acceso al archivo del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="2295b-137">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="2295b-138">*B: el archivo del conjunto de datos de entrenamiento:* si el usuario también proporciona conjuntos de datos para la validación del modelo (con `--test-dataset` y, opcionalmente, `--validation-dataset`), el argumento `--dataset` significa tener solo el "conjunto de datos de entrenamiento".</span><span class="sxs-lookup"><span data-stu-id="2295b-138">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="2295b-139">Por ejemplo, cuando se usa un enfoque de 80-20 % para validar la calidad del modelo y obtener métricas de precisión, el "conjunto de datos de entrenamiento" tendrá un 80 % de los datos y el "conjunto de datos de prueba" tendría un 20 % de los datos.</span><span class="sxs-lookup"><span data-stu-id="2295b-139">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

## <a name="test-dataset"></a><span data-ttu-id="2295b-140">Conjunto de datos de prueba</span><span class="sxs-lookup"><span data-stu-id="2295b-140">Test dataset</span></span>

<span data-ttu-id="2295b-141">`--test-dataset | -t` (cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-141">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="2295b-142">Ruta de acceso al archivo que apunta al archivo del conjunto de datos de prueba, por ejemplo, cuando se usa un enfoque de 80-20 % al realizar validaciones regulares para obtener métricas de precisión.</span><span class="sxs-lookup"><span data-stu-id="2295b-142">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="2295b-143">Si usa `--test-dataset`, también se requiere `--dataset`.</span><span class="sxs-lookup"><span data-stu-id="2295b-143">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="2295b-144">El argumento `--test-dataset` es opcional, a menos que se utilice --validation-dataset.</span><span class="sxs-lookup"><span data-stu-id="2295b-144">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="2295b-145">En ese caso, el usuario debe utilizar los tres argumentos.</span><span class="sxs-lookup"><span data-stu-id="2295b-145">In that case, the user must use the three arguments.</span></span>

## <a name="validation-dataset"></a><span data-ttu-id="2295b-146">Conjunto de datos de validación</span><span class="sxs-lookup"><span data-stu-id="2295b-146">Validation dataset</span></span>

<span data-ttu-id="2295b-147">`--validation-dataset | -v` (cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-147">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="2295b-148">Ruta de acceso al archivo que apunta al archivo del conjunto de datos de validación.</span><span class="sxs-lookup"><span data-stu-id="2295b-148">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="2295b-149">El conjunto de datos de validación es opcional, en cualquier caso.</span><span class="sxs-lookup"><span data-stu-id="2295b-149">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="2295b-150">Si usa un `validation dataset`, el comportamiento debería ser el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2295b-150">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="2295b-151">Los argumentos `test-dataset` y `--dataset` también son necesarios.</span><span class="sxs-lookup"><span data-stu-id="2295b-151">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="2295b-152">El conjunto de datos `validation-dataset` se usa para calcular el error de predicción en la selección del modelo.</span><span class="sxs-lookup"><span data-stu-id="2295b-152">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="2295b-153">El `test-dataset` se usa para la valoración del error de generalización del último modelo elegido.</span><span class="sxs-lookup"><span data-stu-id="2295b-153">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="2295b-154">Idealmente, el conjunto de pruebas se debe mantener en un "almacén" y extraerse solo al final del análisis de datos.</span><span class="sxs-lookup"><span data-stu-id="2295b-154">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="2295b-155">Básicamente, cuando se usa un `validation dataset`, además del `test dataset`, la fase de validación se divide en dos partes:</span><span class="sxs-lookup"><span data-stu-id="2295b-155">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="2295b-156">En la primera parte, simplemente mira los modelos y selecciona el enfoque con mejor rendimiento mediante los datos de validación (=validación)</span><span class="sxs-lookup"><span data-stu-id="2295b-156">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="2295b-157">A continuación, calcula la precisión del enfoque seleccionado (=prueba).</span><span class="sxs-lookup"><span data-stu-id="2295b-157">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="2295b-158">Por lo tanto, la separación de datos podría ser 80/10/10 o 75/15/10.</span><span class="sxs-lookup"><span data-stu-id="2295b-158">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="2295b-159">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2295b-159">For example:</span></span>

- <span data-ttu-id="2295b-160">el archivo `training-dataset` debe tener un 75 % de los datos.</span><span class="sxs-lookup"><span data-stu-id="2295b-160">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="2295b-161">el archivo `validation-dataset` debe tener un 15 % de los datos.</span><span class="sxs-lookup"><span data-stu-id="2295b-161">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="2295b-162">el archivo `test-dataset` debe tener un 10 % de los datos.</span><span class="sxs-lookup"><span data-stu-id="2295b-162">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="2295b-163">En cualquier caso, el usuario decidirá los porcentajes mediante la CLI que proporcionará los archivos ya divididos.</span><span class="sxs-lookup"><span data-stu-id="2295b-163">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

## <a name="label-column"></a><span data-ttu-id="2295b-164">Columna de etiqueta</span><span class="sxs-lookup"><span data-stu-id="2295b-164">Label column</span></span>

<span data-ttu-id="2295b-165">`--label-col` (entero o cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-165">`--label-col` (int or string)</span></span>

<span data-ttu-id="2295b-166">Con este argumento, se puede especificar una columna concreta de destino/objetivo (es decir, la variable que se quiere predecir) utilizando el nombre de la columna establecido en el encabezado del conjunto de datos o bien el índice numérico de la columna en el archivo del conjunto de datos (los valores del índice de la columna empiezan en 0).</span><span class="sxs-lookup"><span data-stu-id="2295b-166">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="2295b-167">Este argumento se usa para problemas de *clasificación* y *regresión*.</span><span class="sxs-lookup"><span data-stu-id="2295b-167">This argument is used for *classification* and *regression* problems.</span></span>

## <a name="item-column"></a><span data-ttu-id="2295b-168">Columna de elementos</span><span class="sxs-lookup"><span data-stu-id="2295b-168">Item column</span></span>

<span data-ttu-id="2295b-169">`--item-col` (entero o cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-169">`--item-col` (int or string)</span></span>

<span data-ttu-id="2295b-170">La columna de elementos contiene la lista de elementos que los usuarios califican (los elementos se recomiendan a los usuarios).</span><span class="sxs-lookup"><span data-stu-id="2295b-170">The item column has the list of items that users rate (items are recommended to users).</span></span> <span data-ttu-id="2295b-171">Esta columna se puede especificar utilizando el nombre de la columna establecido en el encabezado del conjunto de datos o bien el índice numérico de la columna en el archivo del conjunto de datos (los valores del índice de la columna empiezan en 0).</span><span class="sxs-lookup"><span data-stu-id="2295b-171">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="2295b-172">Este argumento solo se usa para la tarea de *recomendación*.</span><span class="sxs-lookup"><span data-stu-id="2295b-172">This argument is used only for the *recommendation* task.</span></span>

## <a name="rating-column"></a><span data-ttu-id="2295b-173">Columna de clasificación</span><span class="sxs-lookup"><span data-stu-id="2295b-173">Rating column</span></span>

<span data-ttu-id="2295b-174">`--rating-col` (entero o cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-174">`--rating-col` (int or string)</span></span>

<span data-ttu-id="2295b-175">La columna de clasificación contiene la lista de clasificaciones que los usuarios otorgan a los elementos.</span><span class="sxs-lookup"><span data-stu-id="2295b-175">The rating column has the list of ratings that are given to items by users.</span></span> <span data-ttu-id="2295b-176">Esta columna se puede especificar utilizando el nombre de la columna establecido en el encabezado del conjunto de datos o bien el índice numérico de la columna en el archivo del conjunto de datos (los valores del índice de la columna empiezan en 0).</span><span class="sxs-lookup"><span data-stu-id="2295b-176">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="2295b-177">Este argumento solo se usa para la tarea de *recomendación*.</span><span class="sxs-lookup"><span data-stu-id="2295b-177">This argument is used only for the *recommendation* task.</span></span>

## <a name="user-column"></a><span data-ttu-id="2295b-178">Columna de usuarios</span><span class="sxs-lookup"><span data-stu-id="2295b-178">User column</span></span>

<span data-ttu-id="2295b-179">`--user-col` (entero o cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-179">`--user-col` (int or string)</span></span>

<span data-ttu-id="2295b-180">La columna de usuarios contiene la lista de usuarios que califican elementos.</span><span class="sxs-lookup"><span data-stu-id="2295b-180">The user column has the list of users that give ratings to items.</span></span> <span data-ttu-id="2295b-181">Esta columna se puede especificar utilizando el nombre de la columna establecido en el encabezado del conjunto de datos o bien el índice numérico de la columna en el archivo del conjunto de datos (los valores del índice de la columna empiezan en 0).</span><span class="sxs-lookup"><span data-stu-id="2295b-181">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="2295b-182">Este argumento solo se usa para la tarea de *recomendación*.</span><span class="sxs-lookup"><span data-stu-id="2295b-182">This argument is used only for the *recommendation* task.</span></span>

## <a name="ignore-columns"></a><span data-ttu-id="2295b-183">Omisión de columnas</span><span class="sxs-lookup"><span data-stu-id="2295b-183">Ignore columns</span></span>

<span data-ttu-id="2295b-184">`--ignore-columns` (cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-184">`--ignore-columns` (string)</span></span>

<span data-ttu-id="2295b-185">Con este argumento, puede omitir las columnas existentes en el archivo del conjunto de datos, de modo que los procesos de entrenamiento no las carguen ni utilicen.</span><span class="sxs-lookup"><span data-stu-id="2295b-185">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="2295b-186">Especifique los nombres de las columnas que desea omitir.</span><span class="sxs-lookup"><span data-stu-id="2295b-186">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="2295b-187">Use ", " (coma con espacio) o " " (espacio) para separar varios nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="2295b-187">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="2295b-188">Puede usar comillas para los nombres de columna que contienen espacios en blanco (por ejemplo, "inicio de sesión").</span><span class="sxs-lookup"><span data-stu-id="2295b-188">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="2295b-189">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2295b-189">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a><span data-ttu-id="2295b-190">Tiene encabezado</span><span class="sxs-lookup"><span data-stu-id="2295b-190">Has header</span></span>

<span data-ttu-id="2295b-191">`--has-header` (bool)</span><span class="sxs-lookup"><span data-stu-id="2295b-191">`--has-header` (bool)</span></span>

<span data-ttu-id="2295b-192">Especifique si los archivos del conjunto de datos tienen una fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="2295b-192">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="2295b-193">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="2295b-193">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="2295b-194">La CLI de ML.NET intentará detectar esta propiedad si el usuario no especifica este argumento.</span><span class="sxs-lookup"><span data-stu-id="2295b-194">The ML.NET CLI will try to detect this property if this argument is not specified by the user.</span></span>

## <a name="train-time"></a><span data-ttu-id="2295b-195">Tiempo de entrenamiento</span><span class="sxs-lookup"><span data-stu-id="2295b-195">Train time</span></span>

<span data-ttu-id="2295b-196">`--train-time` (cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-196">`--train-time` (string)</span></span>

<span data-ttu-id="2295b-197">De forma predeterminada, el tiempo máximo de exploración o entrenamiento es de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="2295b-197">By default, the maximum exploration / train time is 30 minutes.</span></span>

<span data-ttu-id="2295b-198">Este argumento establece el tiempo máximo (en segundos) para que el proceso explore varios instructores y configuraciones.</span><span class="sxs-lookup"><span data-stu-id="2295b-198">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="2295b-199">El tiempo configurado puede superarse so el tiempo proporcionado es demasiado corto (por ejemplo, 2 segundos) para una sola iteración.</span><span class="sxs-lookup"><span data-stu-id="2295b-199">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="2295b-200">En este caso, el tiempo real es el tiempo necesario para producir una configuración de modelo en una sola iteración.</span><span class="sxs-lookup"><span data-stu-id="2295b-200">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="2295b-201">El tiempo necesario para las iteraciones puede variar según el tamaño del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="2295b-201">The needed time for iterations can vary depending on the size of the dataset.</span></span>

## <a name="cache"></a><span data-ttu-id="2295b-202">instancias y claves</span><span class="sxs-lookup"><span data-stu-id="2295b-202">Cache</span></span>

<span data-ttu-id="2295b-203">`--cache` (cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-203">`--cache` (string)</span></span>

<span data-ttu-id="2295b-204">Si usa almacenamiento en caché, el conjunto de datos de entrenamiento completo se cargará en memoria.</span><span class="sxs-lookup"><span data-stu-id="2295b-204">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="2295b-205">Para conjuntos de datos pequeños y medianos, el uso de memoria caché puede mejorar significativamente el rendimiento del entrenamiento, lo que significa que el tiempo de entrenamiento puede ser más corto que cuando no se usa memoria caché.</span><span class="sxs-lookup"><span data-stu-id="2295b-205">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="2295b-206">Sin embargo, para conjuntos de datos grandes, cargar todos los datos en memoria puede tener un impacto negativo ya que podría obtener memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="2295b-206">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="2295b-207">Cuando se entrene con archivos de conjuntos de datos grandes y no se use la memoria caché, ML.NET transmitirá fragmentos de datos desde la unidad cuando necesite cargar más datos durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2295b-207">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="2295b-208">Puede especificar los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="2295b-208">You can specify the following values:</span></span>

<span data-ttu-id="2295b-209">`on`: Fuerza el uso de la memoria caché durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2295b-209">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="2295b-210">`off`: Fuerza el no uso de la memoria caché durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="2295b-210">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="2295b-211">`auto`: Según la heurística de AutoML, se usará o no la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="2295b-211">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="2295b-212">Normalmente, los conjuntos de datos pequeños y medianos utilizarán la memoria caché y los conjuntos de datos grandes no la usarán si se usa la opción `auto`.</span><span class="sxs-lookup"><span data-stu-id="2295b-212">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="2295b-213">Si no especifica el parámetro `auto`, la configuración `--cache` de la memoria caché se utilizara de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2295b-213">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

## <a name="name"></a><span data-ttu-id="2295b-214">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="2295b-214">Name</span></span>

<span data-ttu-id="2295b-215">`--name` (cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-215">`--name` (string)</span></span>

<span data-ttu-id="2295b-216">El nombre de la solución o el proyecto de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="2295b-216">The name for the created output project or solution.</span></span> <span data-ttu-id="2295b-217">Si no se especifica ningún nombre, se usará el nombre `sample-{mltask}`.</span><span class="sxs-lookup"><span data-stu-id="2295b-217">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="2295b-218">El archivo del modelo de ML.NET (archivo ZIP) obtendrá el mismo nombre también.</span><span class="sxs-lookup"><span data-stu-id="2295b-218">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

## <a name="output-path"></a><span data-ttu-id="2295b-219">Ruta de acceso de salida</span><span class="sxs-lookup"><span data-stu-id="2295b-219">Output path</span></span>

<span data-ttu-id="2295b-220">`--output | -o` (cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-220">`--output | -o` (string)</span></span>

<span data-ttu-id="2295b-221">Ubicación o carpeta para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="2295b-221">Root location/folder to place the generated output.</span></span> <span data-ttu-id="2295b-222">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="2295b-222">The default is the current directory.</span></span>

## <a name="verbosity"></a><span data-ttu-id="2295b-223">Nivel de detalle</span><span class="sxs-lookup"><span data-stu-id="2295b-223">Verbosity</span></span>

<span data-ttu-id="2295b-224">`--verbosity | -v` (cadena)</span><span class="sxs-lookup"><span data-stu-id="2295b-224">`--verbosity | -v` (string)</span></span>

<span data-ttu-id="2295b-225">Establece el nivel de detalle de la salida estándar.</span><span class="sxs-lookup"><span data-stu-id="2295b-225">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="2295b-226">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="2295b-226">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="2295b-227">`m[inimal]` (de manera predeterminada)</span><span class="sxs-lookup"><span data-stu-id="2295b-227">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="2295b-228">`diag[nostic]` (nivel de información de registro)</span><span class="sxs-lookup"><span data-stu-id="2295b-228">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="2295b-229">De forma predeterminada, la herramienta CLI debe mostrar un mínimo de comentarios (`minimal`) cuando trabaja, como mencionar que está trabajando y, a ser posible, cuánto tiempo queda o qué porcentaje de tiempo lleva completado.</span><span class="sxs-lookup"><span data-stu-id="2295b-229">By default, the CLI tool should show some minimum feedback (`minimal`) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

## <a name="help"></a><span data-ttu-id="2295b-230">Ayuda</span><span class="sxs-lookup"><span data-stu-id="2295b-230">Help</span></span>

`-h |--help`

<span data-ttu-id="2295b-231">Imprime la ayuda para el comando con una descripción para el parámetro de cada comando.</span><span class="sxs-lookup"><span data-stu-id="2295b-231">Prints out help for the command with a description for each command's parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="2295b-232">Vea también</span><span class="sxs-lookup"><span data-stu-id="2295b-232">See also</span></span>

- [<span data-ttu-id="2295b-233">Cómo instalar la herramienta de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="2295b-233">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="2295b-234">Introducción a la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="2295b-234">Overview of the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="2295b-235">Tutorial: Análisis de opiniones mediante la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="2295b-235">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="2295b-236">Telemetría en la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="2295b-236">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)

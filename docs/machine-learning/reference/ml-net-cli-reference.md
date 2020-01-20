---
title: Referencia de comandos de la CLI de ML.NET
description: Información general, ejemplos y referencia del comando de entrenamiento automático en la herramienta de la CLI de ML.NET.
ms.date: 12/18/2019
ms.openlocfilehash: 5e59eba91721b26622360818a73adb07a654dc28
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636125"
---
# <a name="the-mlnet-cli-command-reference"></a><span data-ttu-id="a54e7-103">Referencia de comandos de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="a54e7-103">The ML.NET CLI command reference</span></span>

<span data-ttu-id="a54e7-104">El comando `auto-train` es el comando principal proporcionado por la herramienta de la CLI de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="a54e7-104">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="a54e7-105">El comando permite generar un modelo de ML.NET de buena calidad mediante el aprendizaje automático automatizado (AutoML) además del código de C# de ejemplo para ejecutar o calificar dicho modelo.</span><span class="sxs-lookup"><span data-stu-id="a54e7-105">The command allows you to generate a good quality ML.NET model using automated machine learning (AutoML) as well as the the example C# code to run/score that model.</span></span> <span data-ttu-id="a54e7-106">Además, se genera código C# para entrenar el modelo y poder investigar el algoritmo y la configuración del modelo.</span><span class="sxs-lookup"><span data-stu-id="a54e7-106">In addition, the C# code to train the model is generated for you to research the algorithm and settings of the model.</span></span>

> [!NOTE]
> <span data-ttu-id="a54e7-107">Este tema hace referencia a la CLI de ML.NET y AutoML de ML.NET, que se encuentran actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="a54e7-107">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="overview"></a><span data-ttu-id="a54e7-108">Información general</span><span class="sxs-lookup"><span data-stu-id="a54e7-108">Overview</span></span>

<span data-ttu-id="a54e7-109">Ejemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="a54e7-109">Example usage:</span></span>

```console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="a54e7-110">El comando `mlnet auto-train` genera los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="a54e7-110">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="a54e7-111">Un archivo .zip de modelo serializado ("mejor modelo") listo para usarse.</span><span class="sxs-lookup"><span data-stu-id="a54e7-111">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="a54e7-112">Código C# para ejecutar o puntuar el modelo generado.</span><span class="sxs-lookup"><span data-stu-id="a54e7-112">C# code to run/score that generated model.</span></span>
- <span data-ttu-id="a54e7-113">Código de C# con el código de entrenamiento utilizado para generar ese modelo.</span><span class="sxs-lookup"><span data-stu-id="a54e7-113">C# code with the training code used to generate that model.</span></span>

<span data-ttu-id="a54e7-114">Los dos primeros recursos se pueden usar directamente en las aplicaciones de usuario final (aplicación web ASP.NET Core, servicios, aplicación de escritorio, y mucho más) para realizar predicciones con el modelo.</span><span class="sxs-lookup"><span data-stu-id="a54e7-114">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app and more) to make predictions with the model.</span></span>

<span data-ttu-id="a54e7-115">El tercer recurso, el código de entrenamiento, le muestra el código de la API de ML.NET que utilizó la CLI para entrenar el modelo generado, de modo que pueda investigar el algoritmo y configuración específicos del modelo.</span><span class="sxs-lookup"><span data-stu-id="a54e7-115">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate the specific algorithm and settings of the model.</span></span>

## <a name="examples"></a><span data-ttu-id="a54e7-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a54e7-116">Examples</span></span>

<span data-ttu-id="a54e7-117">El comando de la CLI más sencillo para un problema de clasificación binaria (AutoML infiere la mayor parte de la configuración de los datos proporcionados):</span><span class="sxs-lookup"><span data-stu-id="a54e7-117">The simplest CLI command for a binary classification problem (AutoML infers most of the configuration from the provided data):</span></span>

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="a54e7-118">Otro comando de CLI sencillo para un problema de regresión:</span><span class="sxs-lookup"><span data-stu-id="a54e7-118">Another simple CLI command for a regression problem:</span></span>

``` console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="a54e7-119">Cree y entrene un modelo de clasificación binaria con un conjunto de datos de entrenamiento, un conjunto de datos de prueba y más argumentos explícitos de personalización:</span><span class="sxs-lookup"><span data-stu-id="a54e7-119">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="command-options"></a><span data-ttu-id="a54e7-120">Opciones de comando</span><span class="sxs-lookup"><span data-stu-id="a54e7-120">Command options</span></span>

<span data-ttu-id="a54e7-121">`mlnet auto-train` entrena varios modelos según el conjunto de datos proporcionado y, por último, selecciona el mejor modelo, lo guarda como archivo .zip serializado y genera código C# relacionado para el entrenamiento y la puntuación.</span><span class="sxs-lookup"><span data-stu-id="a54e7-121">`mlnet auto-train` trains multiple models based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

```console
mlnet auto-train

--task | --mltask | -T <value>

--dataset | -d <value>

[
 [--validation-dataset | -v <value>]
  --test-dataset | -t <value>
]

--label-column-name | -n <value>
|
--label-column-index | -i <value>

[--ignore-columns | -I <value>]

[--has-header | -h <value>]

[--max-exploration-time | -x <value>]

[--verbosity | -V <value>]

[--cache | -c <value>]

[--name | -N <value>]

[--output-path | -o <value>]

[--help | -h]

```

<span data-ttu-id="a54e7-122">Las opciones de entrada no válidas hacen que la herramienta de la CLI emita una lista de entradas válidas y un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="a54e7-122">Invalid input options cause the CLI tool to emit a list of valid inputs and an error message.</span></span>

## <a name="task"></a><span data-ttu-id="a54e7-123">Tarea</span><span class="sxs-lookup"><span data-stu-id="a54e7-123">Task</span></span>

<span data-ttu-id="a54e7-124">`--task | --mltask | -T` (cadena)</span><span class="sxs-lookup"><span data-stu-id="a54e7-124">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="a54e7-125">Una sola cadena que proporciona el problema de ML que debe resolverse.</span><span class="sxs-lookup"><span data-stu-id="a54e7-125">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="a54e7-126">Por ejemplo, cualquiera de las siguientes tareas (la CLI finalmente será compatible con todas las tareas que se admiten en AutoML):</span><span class="sxs-lookup"><span data-stu-id="a54e7-126">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="a54e7-127">`regression`: elija si se usará el modelo de ML para predecir un valor numérico</span><span class="sxs-lookup"><span data-stu-id="a54e7-127">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="a54e7-128">`binary-classification`: elija si el resultado del modelo de ML tiene dos posibles valores booleanos categóricos (0 o 1).</span><span class="sxs-lookup"><span data-stu-id="a54e7-128">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="a54e7-129">`multiclass-classification`: elija si el resultado del modelo de ML tiene varios valores posibles categóricos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-129">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="a54e7-130">Solo debe proporcionarse una sola tarea de ML en este argumento.</span><span class="sxs-lookup"><span data-stu-id="a54e7-130">Only one ML task should be provided in this argument.</span></span>

## <a name="dataset"></a><span data-ttu-id="a54e7-131">Conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="a54e7-131">Dataset</span></span>

<span data-ttu-id="a54e7-132">`--dataset | -d` (cadena)</span><span class="sxs-lookup"><span data-stu-id="a54e7-132">`--dataset | -d` (string)</span></span>

<span data-ttu-id="a54e7-133">Este argumento proporciona la ruta de acceso del archivo a cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a54e7-133">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="a54e7-134">*A: el archivo de conjunto de datos entero:* si utiliza esta opción y el usuario no proporciona `--test-dataset` y `--validation-dataset`, se utilizarán internamente enfoques de validación cruzada (de K iteraciones, etc.) o división de datos automatizada para validar el modelo.</span><span class="sxs-lookup"><span data-stu-id="a54e7-134">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="a54e7-135">En ese caso, el usuario solo deberá proporcionar la ruta de acceso al archivo del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-135">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="a54e7-136">*B: el archivo del conjunto de datos de entrenamiento:* si el usuario también proporciona conjuntos de datos para la validación del modelo (con `--test-dataset` y, opcionalmente, `--validation-dataset`), el argumento `--dataset` significa tener solo el "conjunto de datos de entrenamiento".</span><span class="sxs-lookup"><span data-stu-id="a54e7-136">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="a54e7-137">Por ejemplo, cuando se usa un enfoque de 80-20 % para validar la calidad del modelo y obtener métricas de precisión, el "conjunto de datos de entrenamiento" tendrá un 80 % de los datos y el "conjunto de datos de prueba" tendría un 20 % de los datos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-137">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

## <a name="test-dataset"></a><span data-ttu-id="a54e7-138">Conjunto de datos de prueba</span><span class="sxs-lookup"><span data-stu-id="a54e7-138">Test dataset</span></span>

<span data-ttu-id="a54e7-139">`--test-dataset | -t` (cadena)</span><span class="sxs-lookup"><span data-stu-id="a54e7-139">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="a54e7-140">Ruta de acceso al archivo que apunta al archivo del conjunto de datos de prueba, por ejemplo, cuando se usa un enfoque de 80-20 % al realizar validaciones regulares para obtener métricas de precisión.</span><span class="sxs-lookup"><span data-stu-id="a54e7-140">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="a54e7-141">Si usa `--test-dataset`, también se requiere `--dataset`.</span><span class="sxs-lookup"><span data-stu-id="a54e7-141">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="a54e7-142">El argumento `--test-dataset` es opcional, a menos que se utilice --validation-dataset.</span><span class="sxs-lookup"><span data-stu-id="a54e7-142">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="a54e7-143">En ese caso, el usuario debe utilizar los tres argumentos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-143">In that case, the user must use the three arguments.</span></span>

## <a name="validation-dataset"></a><span data-ttu-id="a54e7-144">Conjunto de datos de validación</span><span class="sxs-lookup"><span data-stu-id="a54e7-144">Validation dataset</span></span>

<span data-ttu-id="a54e7-145">`--validation-dataset | -v` (cadena)</span><span class="sxs-lookup"><span data-stu-id="a54e7-145">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="a54e7-146">Ruta de acceso al archivo que apunta al archivo del conjunto de datos de validación.</span><span class="sxs-lookup"><span data-stu-id="a54e7-146">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="a54e7-147">El conjunto de datos de validación es opcional, en cualquier caso.</span><span class="sxs-lookup"><span data-stu-id="a54e7-147">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="a54e7-148">Si usa un `validation dataset`, el comportamiento debería ser el siguiente:</span><span class="sxs-lookup"><span data-stu-id="a54e7-148">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="a54e7-149">Los argumentos `test-dataset` y `--dataset` también son necesarios.</span><span class="sxs-lookup"><span data-stu-id="a54e7-149">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="a54e7-150">El conjunto de datos `validation-dataset` se usa para calcular el error de predicción en la selección del modelo.</span><span class="sxs-lookup"><span data-stu-id="a54e7-150">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="a54e7-151">El `test-dataset` se usa para la valoración del error de generalización del último modelo elegido.</span><span class="sxs-lookup"><span data-stu-id="a54e7-151">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="a54e7-152">Idealmente, el conjunto de pruebas se debe mantener en un "almacén" y extraerse solo al final del análisis de datos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-152">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="a54e7-153">Básicamente, cuando se usa un `validation dataset`, además del `test dataset`, la fase de validación se divide en dos partes:</span><span class="sxs-lookup"><span data-stu-id="a54e7-153">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="a54e7-154">En la primera parte, simplemente mira los modelos y selecciona el enfoque con mejor rendimiento mediante los datos de validación (=validación)</span><span class="sxs-lookup"><span data-stu-id="a54e7-154">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="a54e7-155">A continuación, calcula la precisión del enfoque seleccionado (=prueba).</span><span class="sxs-lookup"><span data-stu-id="a54e7-155">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="a54e7-156">Por lo tanto, la separación de datos podría ser 80/10/10 o 75/15/10.</span><span class="sxs-lookup"><span data-stu-id="a54e7-156">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="a54e7-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a54e7-157">For example:</span></span>

- <span data-ttu-id="a54e7-158">el archivo `training-dataset` debe tener un 75 % de los datos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-158">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="a54e7-159">el archivo `validation-dataset` debe tener un 15 % de los datos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-159">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="a54e7-160">el archivo `test-dataset` debe tener un 10 % de los datos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-160">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="a54e7-161">En cualquier caso, el usuario decidirá los porcentajes mediante la CLI que proporcionará los archivos ya divididos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-161">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

## <a name="label-column-name"></a><span data-ttu-id="a54e7-162">Nombre de la columna de etiqueta</span><span class="sxs-lookup"><span data-stu-id="a54e7-162">Label column name</span></span>

<span data-ttu-id="a54e7-163">`--label-column-name | -n` (cadena)</span><span class="sxs-lookup"><span data-stu-id="a54e7-163">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="a54e7-164">Con este argumento, se puede especificar una columna concreta de destino/objetivo (es decir, la variable que se desea predecir) utilizando el nombre de la columna establecido en el encabezado del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-164">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="a54e7-165">Este argumento se utiliza solo para tareas de ML supervisadas, como un *problema de clasificación*.</span><span class="sxs-lookup"><span data-stu-id="a54e7-165">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="a54e7-166">No se puede usar para tareas de ML no supervisadas, como *clústeres*.</span><span class="sxs-lookup"><span data-stu-id="a54e7-166">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="label-column-index"></a><span data-ttu-id="a54e7-167">Índice de la columna de etiqueta</span><span class="sxs-lookup"><span data-stu-id="a54e7-167">Label column index</span></span>

<span data-ttu-id="a54e7-168">`--label-column-index | -i` (int)</span><span class="sxs-lookup"><span data-stu-id="a54e7-168">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="a54e7-169">Con este argumento, se puede especificar una columna concreta de destino/objetivo (es decir, la variable que se desea predecir) utilizando el índice numérico de la columna en el archivo del conjunto de datos (los valores del índice de la columna empiezan en 1).</span><span class="sxs-lookup"><span data-stu-id="a54e7-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="a54e7-170">*Nota:* Si el usuario también usa el `--label-column-name`, el `--label-column-name` es el que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="a54e7-170">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="a54e7-171">Este argumento se utiliza solo para una tarea de ML supervisada, como un *problema de clasificación*.</span><span class="sxs-lookup"><span data-stu-id="a54e7-171">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="a54e7-172">No se puede usar para tareas de ML no supervisadas, como *clústeres*.</span><span class="sxs-lookup"><span data-stu-id="a54e7-172">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="ignore-columns"></a><span data-ttu-id="a54e7-173">Omisión de columnas</span><span class="sxs-lookup"><span data-stu-id="a54e7-173">Ignore columns</span></span>

<span data-ttu-id="a54e7-174">`--ignore-columns | -I` (cadena)</span><span class="sxs-lookup"><span data-stu-id="a54e7-174">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="a54e7-175">Con este argumento, puede omitir las columnas existentes en el archivo del conjunto de datos, de modo que los procesos de entrenamiento no las carguen ni utilicen.</span><span class="sxs-lookup"><span data-stu-id="a54e7-175">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="a54e7-176">Especifique los nombres de las columnas que desea omitir.</span><span class="sxs-lookup"><span data-stu-id="a54e7-176">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="a54e7-177">Use ", " (coma con espacio) o " " (espacio) para separar varios nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="a54e7-177">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="a54e7-178">Puede usar comillas para los nombres de columna que contienen espacios en blanco (por ejemplo, "inicio de sesión").</span><span class="sxs-lookup"><span data-stu-id="a54e7-178">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="a54e7-179">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a54e7-179">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a><span data-ttu-id="a54e7-180">Tiene encabezado</span><span class="sxs-lookup"><span data-stu-id="a54e7-180">Has header</span></span>

<span data-ttu-id="a54e7-181">`--has-header | -h` (bool)</span><span class="sxs-lookup"><span data-stu-id="a54e7-181">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="a54e7-182">Especifique si los archivos del conjunto de datos tienen una fila de encabezado.</span><span class="sxs-lookup"><span data-stu-id="a54e7-182">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="a54e7-183">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="a54e7-183">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="a54e7-184">El valor predeterminado es `true` si el usuario no especifica este argumento.</span><span class="sxs-lookup"><span data-stu-id="a54e7-184">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="a54e7-185">Para poder usar el argumento `--label-column-name`, debe tener un encabezado en el archivo del conjunto de datos y `--has-header` establecido en `true` (el cual es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="a54e7-185">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

## <a name="max-exploration-time"></a><span data-ttu-id="a54e7-186">Tiempo máximo de exploración</span><span class="sxs-lookup"><span data-stu-id="a54e7-186">Max exploration time</span></span>

<span data-ttu-id="a54e7-187">`--max-exploration-time | -x` (cadena)</span><span class="sxs-lookup"><span data-stu-id="a54e7-187">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="a54e7-188">De forma predeterminada, el tiempo máximo de exploración es de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-188">By default, the maximum exploration time is 30 minutes.</span></span>

<span data-ttu-id="a54e7-189">Este argumento establece el tiempo máximo (en segundos) para que el proceso explore varios instructores y configuraciones.</span><span class="sxs-lookup"><span data-stu-id="a54e7-189">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="a54e7-190">El tiempo configurado puede superarse so el tiempo proporcionado es demasiado corto (por ejemplo, 2 segundos) para una sola iteración.</span><span class="sxs-lookup"><span data-stu-id="a54e7-190">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="a54e7-191">En este caso, el tiempo real es el tiempo necesario para producir una configuración de modelo en una sola iteración.</span><span class="sxs-lookup"><span data-stu-id="a54e7-191">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="a54e7-192">El tiempo necesario para las iteraciones puede variar según el tamaño del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a54e7-192">The needed time for iterations can vary depending on the size of the dataset.</span></span>

## <a name="cache"></a><span data-ttu-id="a54e7-193">instancias y claves</span><span class="sxs-lookup"><span data-stu-id="a54e7-193">Cache</span></span>

<span data-ttu-id="a54e7-194">`--cache | -c` (cadena)</span><span class="sxs-lookup"><span data-stu-id="a54e7-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="a54e7-195">Si usa almacenamiento en caché, el conjunto de datos de entrenamiento completo se cargará en memoria.</span><span class="sxs-lookup"><span data-stu-id="a54e7-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="a54e7-196">Para conjuntos de datos pequeños y medianos, el uso de memoria caché puede mejorar significativamente el rendimiento del entrenamiento, lo que significa que el tiempo de entrenamiento puede ser más corto que cuando no se usa memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a54e7-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="a54e7-197">Sin embargo, para conjuntos de datos grandes, cargar todos los datos en memoria puede tener un impacto negativo ya que podría obtener memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="a54e7-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="a54e7-198">Cuando se entrene con archivos de conjuntos de datos grandes y no se use la memoria caché, ML.NET transmitirá fragmentos de datos desde la unidad cuando necesite cargar más datos durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="a54e7-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="a54e7-199">Puede especificar los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a54e7-199">You can specify the following values:</span></span>

<span data-ttu-id="a54e7-200">`on`: Fuerza el uso de la memoria caché durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="a54e7-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="a54e7-201">`off`: Fuerza el no uso de la memoria caché durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="a54e7-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="a54e7-202">`auto`: Según la heurística de AutoML, se usará o no la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a54e7-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="a54e7-203">Normalmente, los conjuntos de datos pequeños y medianos utilizarán la memoria caché y los conjuntos de datos grandes no la usarán si se usa la opción `auto`.</span><span class="sxs-lookup"><span data-stu-id="a54e7-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="a54e7-204">Si no especifica el parámetro `auto`, la configuración `--cache` de la memoria caché se utilizara de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a54e7-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

## <a name="name"></a><span data-ttu-id="a54e7-205">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="a54e7-205">Name</span></span>

<span data-ttu-id="a54e7-206">`--name | -N` (cadena)</span><span class="sxs-lookup"><span data-stu-id="a54e7-206">`--name | -N` (string)</span></span>

<span data-ttu-id="a54e7-207">El nombre de la solución o el proyecto de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="a54e7-207">The name for the created output project or solution.</span></span> <span data-ttu-id="a54e7-208">Si no se especifica ningún nombre, se usará el nombre `sample-{mltask}`.</span><span class="sxs-lookup"><span data-stu-id="a54e7-208">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="a54e7-209">El archivo del modelo de ML.NET (archivo ZIP) obtendrá el mismo nombre también.</span><span class="sxs-lookup"><span data-stu-id="a54e7-209">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

## <a name="output-path"></a><span data-ttu-id="a54e7-210">Ruta de acceso de salida</span><span class="sxs-lookup"><span data-stu-id="a54e7-210">Output path</span></span>

<span data-ttu-id="a54e7-211">`--output-path | -o` (cadena)</span><span class="sxs-lookup"><span data-stu-id="a54e7-211">`--output-path | -o` (string)</span></span>

<span data-ttu-id="a54e7-212">Ubicación o carpeta para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="a54e7-212">Root location/folder to place the generated output.</span></span> <span data-ttu-id="a54e7-213">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="a54e7-213">The default is the current directory.</span></span>

## <a name="verbosity"></a><span data-ttu-id="a54e7-214">Nivel de detalle</span><span class="sxs-lookup"><span data-stu-id="a54e7-214">Verbosity</span></span>

<span data-ttu-id="a54e7-215">`--verbosity | -V` (cadena)</span><span class="sxs-lookup"><span data-stu-id="a54e7-215">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="a54e7-216">Establece el nivel de detalle de la salida estándar.</span><span class="sxs-lookup"><span data-stu-id="a54e7-216">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="a54e7-217">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="a54e7-217">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="a54e7-218">`m[inimal]` (de manera predeterminada)</span><span class="sxs-lookup"><span data-stu-id="a54e7-218">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="a54e7-219">`diag[nostic]` (nivel de información de registro)</span><span class="sxs-lookup"><span data-stu-id="a54e7-219">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="a54e7-220">De forma predeterminada, la herramienta de la CLI debe mostrar un mínimo de comentarios cuando trabaja, como mencionar que está trabajando y, de ser posible, cuánto tiempo queda o qué porcentaje de tiempo lleva completado.</span><span class="sxs-lookup"><span data-stu-id="a54e7-220">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

## <a name="help"></a><span data-ttu-id="a54e7-221">Ayuda</span><span class="sxs-lookup"><span data-stu-id="a54e7-221">Help</span></span>

`-h|--help`

<span data-ttu-id="a54e7-222">Imprime la ayuda para el comando con una descripción para el parámetro de cada comando.</span><span class="sxs-lookup"><span data-stu-id="a54e7-222">Prints out help for the command with a description for each command's parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="a54e7-223">Vea también</span><span class="sxs-lookup"><span data-stu-id="a54e7-223">See also</span></span>

- [<span data-ttu-id="a54e7-224">Cómo instalar la herramienta de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="a54e7-224">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="a54e7-225">Introducción a la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="a54e7-225">Overview of the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="a54e7-226">Tutorial: Análisis de opiniones mediante la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="a54e7-226">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="a54e7-227">Telemetría en la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="a54e7-227">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)

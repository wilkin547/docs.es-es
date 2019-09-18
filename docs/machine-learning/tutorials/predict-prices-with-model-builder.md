---
title: Predicción de precios mediante regresión con el Generador de modelos
description: En este tutorial se muestra cómo compilar un modelo de regresión con el Generador de modelos de ML.NET para predecir precios, en concreto, las tarifas de taxi de Nueva York.
author: luisquintanilla
ms.author: luquinta
ms.date: 09/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 675ca58ab071293fe5c04b1b85337fb1e48dfbea
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991351"
---
# <a name="predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="95858-103">Predicción de precios mediante regresión con el Generador de modelos</span><span class="sxs-lookup"><span data-stu-id="95858-103">Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="95858-104">Obtenga información sobre cómo usar el Generador de modelos de ML.NET para crear un modelo de regresión para predecir precios.</span><span class="sxs-lookup"><span data-stu-id="95858-104">Learn how to use ML.NET Model Builder to build a regression model() to predict prices.</span></span>  <span data-ttu-id="95858-105">La aplicación de consola de .NET que desarrolla en este tutorial predice las tarifas de taxi en función de los datos históricos de tarifas de taxi de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="95858-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="95858-106">La plantilla de predicción de precios del Generador de modelos puede usarse para cualquier escenario que requiera la predicción de un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="95858-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="95858-107">Algunos escenarios de ejemplo son: predicción del precio de la vivienda, predicción de la demanda y previsión de ventas.</span><span class="sxs-lookup"><span data-stu-id="95858-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="95858-108">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="95858-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="95858-109">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="95858-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="95858-110">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="95858-110">Choose a scenario</span></span>
> - <span data-ttu-id="95858-111">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="95858-111">Load the data</span></span>
> - <span data-ttu-id="95858-112">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="95858-112">Train the model</span></span>
> - <span data-ttu-id="95858-113">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="95858-113">Evaluate the model</span></span>
> - <span data-ttu-id="95858-114">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="95858-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="95858-115">El Generador de modelos se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="95858-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="95858-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="95858-116">Pre-requisites</span></span>

<span data-ttu-id="95858-117">Para obtener una lista de los requisitos previos e instrucciones de instalación, visite la [Guía de instalación del Generador de modelos](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="95858-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="95858-118">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="95858-118">Create a console application</span></span>

1. <span data-ttu-id="95858-119">Cree una **aplicación de consola de .NET Core** denominada "TaxiFarePrediction".</span><span class="sxs-lookup"><span data-stu-id="95858-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="95858-120">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="95858-120">Prepare and understand the data</span></span>

1. <span data-ttu-id="95858-121">Cree un directorio denominado *Datos* en el proyecto para almacenarlos archivos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="95858-121">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="95858-122">El conjunto de datos que se usa para entrenar y evaluar el modelo de Machine Learning procede originalmente del conjunto de datos NYC TLC Taxi Trip.</span><span class="sxs-lookup"><span data-stu-id="95858-122">The data set used to train and evaluate the machine learning model is originally from the NYC TLC Taxi Trip data set.</span></span>

    <span data-ttu-id="95858-123">Para descargar el conjunto de datos, vaya al [vínculo de descarga de taxi-fare-train.csv](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span><span class="sxs-lookup"><span data-stu-id="95858-123">To download the data set, navigate to the [taxi-fare-train.csv download link](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span></span>

    <span data-ttu-id="95858-124">Cuando se cargue la página, haga clic con el botón derecho en cualquier parte de la página y seleccione **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="95858-124">When the page loads, right-click anywhere on the page and select **Save as**.</span></span>

    <span data-ttu-id="95858-125">Use el **cuadro de diálogo Guardar como** para guardar el archivo en la carpeta *Data* que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="95858-125">Use the **Save As Dialog** to save the file in the *Data* folder you created at the previous step.</span></span>

1. <span data-ttu-id="95858-126">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *taxi-fare-train.csv* y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="95858-126">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="95858-127">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="95858-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="95858-128">Cada fila del conjunto de datos `taxi-fare-train.csv` contiene los detalles de los viajes realizados por un taxi.</span><span class="sxs-lookup"><span data-stu-id="95858-128">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="95858-129">Abra el conjunto de datos **train.csv de taxi y tarifas**.</span><span class="sxs-lookup"><span data-stu-id="95858-129">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="95858-130">El conjunto de datos proporcionado contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="95858-130">The provided data set contains the following columns:</span></span>

    - <span data-ttu-id="95858-131">**vendor_id:** el identificador del taxista es una característica.</span><span class="sxs-lookup"><span data-stu-id="95858-131">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    - <span data-ttu-id="95858-132">**rate_code:** el tipo de tarifa del viaje en taxi es una característica.</span><span class="sxs-lookup"><span data-stu-id="95858-132">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    - <span data-ttu-id="95858-133">**passenger_count:** el número de pasajeros en el recorrido es una característica.</span><span class="sxs-lookup"><span data-stu-id="95858-133">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    - <span data-ttu-id="95858-134">**trip_time_in_secs:** la cantidad de tiempo que tardó el viaje.</span><span class="sxs-lookup"><span data-stu-id="95858-134">**trip_time_in_secs:** The amount of time the trip took.</span></span>
    - <span data-ttu-id="95858-135">**trip_distance:** la distancia del viaje es una característica.</span><span class="sxs-lookup"><span data-stu-id="95858-135">**trip_distance:** The distance of the trip is a feature.</span></span>
    - <span data-ttu-id="95858-136">**payment_type:** el método de pago (efectivo o tarjeta de crédito) es una característica.</span><span class="sxs-lookup"><span data-stu-id="95858-136">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    - <span data-ttu-id="95858-137">**fare_amount:** la tarifa de taxi total pagada es la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="95858-137">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="95858-138">`label` es la columna que quiere predecir.</span><span class="sxs-lookup"><span data-stu-id="95858-138">The `label` is the column you want to predict.</span></span> <span data-ttu-id="95858-139">Al realizar una tarea de regresión, el objetivo es predecir un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="95858-139">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="95858-140">En este escenario de predicción de precio, se predice el coste de un viaje de taxi.</span><span class="sxs-lookup"><span data-stu-id="95858-140">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="95858-141">Por lo tanto, **fare_amount** es la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="95858-141">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="95858-142">Los valores de `features` identificados son las entradas que se proporcionan al modelo para predecir `label`.</span><span class="sxs-lookup"><span data-stu-id="95858-142">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="95858-143">En este caso, el resto de columnas se usan como entradas o características para predecir el importe de la tarifa.</span><span class="sxs-lookup"><span data-stu-id="95858-143">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="95858-144">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="95858-144">Choose a scenario</span></span>

<span data-ttu-id="95858-145">Para entrenar el modelo, deberá seleccionarlo en la lista de escenarios de aprendizaje automático disponibles proporcionada por el Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="95858-145">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="95858-146">En este caso, el escenario es `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="95858-146">In this case, the scenario is `Price Prediction`.</span></span>

1. <span data-ttu-id="95858-147">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *TaxiFarePrediction* y seleccione **Agregar** > **Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="95858-147">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="95858-148">En el paso del escenario de la herramienta Generador de modelos, seleccione el escenario *Predicción de precio*.</span><span class="sxs-lookup"><span data-stu-id="95858-148">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="95858-149">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="95858-149">Load the data</span></span>

<span data-ttu-id="95858-150">El Generador de modelos acepta datos de dos orígenes, una base de datos de SQL Server o un archivo local en formato .csv o .tsv.</span><span class="sxs-lookup"><span data-stu-id="95858-150">Model Builder accepts data from two sources, a SQL Server database or a local file in csv or tsv format.</span></span>

1. <span data-ttu-id="95858-151">En el paso de datos de la herramienta Generador de modelos, seleccione *Archivo* en la lista desplegable origen de datos.</span><span class="sxs-lookup"><span data-stu-id="95858-151">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="95858-152">Seleccione el botón junto al cuadro de texto *Seleccionar un archivo* y use el Explorador de archivos para examinar y seleccionar *taxi-fare-test.csv* en el directorio *Datos*.</span><span class="sxs-lookup"><span data-stu-id="95858-152">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="95858-153">Elija *fare_amount* en la lista desplegable *Etiqueta o columna para la predicción* y vaya al paso de entrenamiento de la herramienta Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="95858-153">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="95858-154">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="95858-154">Train the model</span></span>

<span data-ttu-id="95858-155">La tarea de aprendizaje automático que se usa para entrenar el modelo de predicción de precio en este tutorial es la regresión.</span><span class="sxs-lookup"><span data-stu-id="95858-155">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="95858-156">Durante el proceso de entrenamiento de modelos, el Generador de modelos entrena modelos independientes usando diferentes opciones y algoritmos de regresión para encontrar el modelo con mejor rendimiento para el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="95858-156">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="95858-157">El tiempo necesario para el entrenamiento del modelo es proporcional a la cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="95858-157">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="95858-158">El generador de modelos selecciona automáticamente un valor predeterminado para **Tiempo de entrenamiento (segundos)** en función del tamaño del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="95858-158">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="95858-159">Deje el valor predeterminado como está para *Tiempo de entrenamiento (segundos)* , a menos que prefiera entrenar durante más tiempo.</span><span class="sxs-lookup"><span data-stu-id="95858-159">Leave the default value as is for *Time to train (seconds)* unless you prefer to train for a longer time.</span></span>
2. <span data-ttu-id="95858-160">Seleccione *Iniciar entrenamiento*.</span><span class="sxs-lookup"><span data-stu-id="95858-160">Select *Start Training*.</span></span>

<span data-ttu-id="95858-161">Durante el proceso de entrenamiento, los datos de progreso se muestran en la sección `Progress` del paso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="95858-161">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="95858-162">En Estado se muestra el grado de finalización del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="95858-162">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="95858-163">En Mejor precisión se muestra la precisión del modelo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="95858-163">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="95858-164">Una mayor precisión significa que el modelo realiza una predicción más correcta de los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="95858-164">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="95858-165">En Mejor algoritmo se muestra el nombre del algoritmo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="95858-165">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="95858-166">En Último algoritmo se muestra el nombre del algoritmo que ha usado más recientemente el Generador de modelos para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="95858-166">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="95858-167">Una vez completado el entrenamiento, vaya al paso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="95858-167">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="95858-168">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="95858-168">Evaluate the model</span></span>

<span data-ttu-id="95858-169">El resultado del paso de entrenamiento será un modelo que tenga el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="95858-169">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="95858-170">En el paso de evaluación de la herramienta Generador de modelos, la sección de salida contendrá el algoritmo usado por el modelo con el mejor rendimiento en la entrada *Mejor modelo* junto con las métricas en *Modelo de mayor calidad (RSquared)* .</span><span class="sxs-lookup"><span data-stu-id="95858-170">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="95858-171">Además de una tabla resumen que contiene los cinco mejores modelos y sus métricas.</span><span class="sxs-lookup"><span data-stu-id="95858-171">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="95858-172">Si no está satisfecho con las métricas de precisión, una forma sencilla de intentar mejorar la precisión del modelo es aumentar la cantidad de tiempo para entrenar el modelo o usar más datos.</span><span class="sxs-lookup"><span data-stu-id="95858-172">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="95858-173">En caso contrario, vaya al paso de código.</span><span class="sxs-lookup"><span data-stu-id="95858-173">Otherwise, navigate to the code step.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="95858-174">Incorporación del código para hacer predicciones</span><span class="sxs-lookup"><span data-stu-id="95858-174">Add the code to make predictions</span></span>

<span data-ttu-id="95858-175">Se crearán dos proyectos como resultado del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="95858-175">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="95858-176">TaxiFarePredictionML.ConsoleApp: Una aplicación de consola de .NET Core que contiene el entrenamiento del modelo y el código de consumo.</span><span class="sxs-lookup"><span data-stu-id="95858-176">TaxiFarePredictionML.ConsoleApp: A .NET Core Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="95858-177">TaxiFarePredictionML.Model: Una biblioteca de clases .NET Standard que contienen los modelos de datos que definen el esquema de entrada y salida de los datos del modelo, así como la versión persistente del modelo con mejor rendimiento durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="95858-177">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="95858-178">En el paso de código de la herramienta Generador de modelos, seleccione **Agregar proyectos** para agregar a la solución los proyectos generados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="95858-178">In the code step of the Model Builder tool, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="95858-179">Haga clic con el botón derecho en el proyecto *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="95858-179">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="95858-180">A continuación, **Agregar > Referencia**.</span><span class="sxs-lookup"><span data-stu-id="95858-180">Then, **Add > Reference**.</span></span> <span data-ttu-id="95858-181">Elija el nodo **Proyectos > Solución** y, en la lista, marque el proyecto *TaxiFarePredictionML.Model* y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="95858-181">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>
1. <span data-ttu-id="95858-182">Abra el archivo *Program.cs* en el proyecto *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="95858-182">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
1. <span data-ttu-id="95858-183">Agregue las siguientes instrucciones USING para hacer referencia al paquete de NuGet *Microsoft.ML* y al proyecto *TaxiFarePredictionML.Model*:</span><span class="sxs-lookup"><span data-stu-id="95858-183">Add the following using statements to reference the *Microsoft.ML* NuGet package and *TaxiFarePredictionML.Model* project:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

1. <span data-ttu-id="95858-184">Agregue el método `ConsumeModel` a la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="95858-184">Add the `ConsumeModel` method to the `Program` class.</span></span>

    ```csharp
    static ModelOutput ConsumeModel(ModelInput input)
    {
        // 1. Load the model
        MLContext mlContext = new MLContext();
        ITransformer mlModel = mlContext.Model.Load("MLModel.zip", out var modelInputSchema);

        // 2. Create PredictionEngine
        var predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // 3. Use PredictionEngine to use model on input data
        ModelOutput result = predictionEngine.Predict(input);

        // 4. Return prediction result
        return result;
    }
    ```

    <span data-ttu-id="95858-185">`ConsumeModel` cargará el modelo entrenado, creará un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para el modelo y lo usará para realizar predicciones según los datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="95858-185">The `ConsumeModel` will load the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model and use it to make predictions on new data.</span></span>

1. <span data-ttu-id="95858-186">Para hacer una predicción según los datos nuevos con el modelo, cree una instancia de la clase `ModelInput` y use el método `ConsumeModel`.</span><span class="sxs-lookup"><span data-stu-id="95858-186">To make a prediction on new data using the model, create a new instance of the `ModelInput` class and use the `ConsumeModel` method.</span></span> <span data-ttu-id="95858-187">Observe que el importe de la tarifa no forma parte de la entrada.</span><span class="sxs-lookup"><span data-stu-id="95858-187">Notice that the fare amount is not part of the input.</span></span> <span data-ttu-id="95858-188">Esto se debe a que el modelo generará la predicción para él.</span><span class="sxs-lookup"><span data-stu-id="95858-188">This is because the model will generate the prediction for it.</span></span> <span data-ttu-id="95858-189">Agregue el siguiente código al método `Main` y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95858-189">Add the following code to the `Main` method and run the application</span></span>

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_time_in_secs = 1271,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };

    // Make prediction
    ModelOutput prediction = ConsumeModel(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

    <span data-ttu-id="95858-190">La salida generada por el programa debe ser similar al siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="95858-190">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="95858-191">Si tiene que hacer referencia a los proyectos generados en un momento posterior dentro de otra solución, puede encontrarlos en el directorio `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="95858-191">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="95858-192">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="95858-192">Next Steps</span></span>

<span data-ttu-id="95858-193">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="95858-193">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="95858-194">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="95858-194">Prepare and understand the data</span></span>
> - <span data-ttu-id="95858-195">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="95858-195">Choose a scenario</span></span>
> - <span data-ttu-id="95858-196">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="95858-196">Load the data</span></span>
> - <span data-ttu-id="95858-197">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="95858-197">Train the model</span></span>
> - <span data-ttu-id="95858-198">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="95858-198">Evaluate the model</span></span>
> - <span data-ttu-id="95858-199">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="95858-199">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="95858-200">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="95858-200">Additional Resources</span></span>

<span data-ttu-id="95858-201">Para más información sobre los temas mencionados en este tutorial, visite estos recursos:</span><span class="sxs-lookup"><span data-stu-id="95858-201">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="95858-202">Escenarios del Generador de modelos</span><span class="sxs-lookup"><span data-stu-id="95858-202">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="95858-203">Regresión</span><span class="sxs-lookup"><span data-stu-id="95858-203">Regression</span></span>](../resources/glossary.md#regression)
- [<span data-ttu-id="95858-204">Métricas de regresión del modelo</span><span class="sxs-lookup"><span data-stu-id="95858-204">Regression Model Metrics</span></span>](../resources/metrics.md#metrics-for-regression)
- [<span data-ttu-id="95858-205">Conjunto de datos NYC TLC Taxi Trip</span><span class="sxs-lookup"><span data-stu-id="95858-205">NYC TLC Taxi Trip data set</span></span>](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)

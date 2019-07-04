---
title: Predicción de precios mediante regresión con el Generador de modelos
description: En este tutorial se muestra cómo compilar un modelo de regresión con el Generador de modelos de ML.NET para predecir precios, en concreto, las tarifas de taxi de Nueva York.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: db9788e3065a0f2f21d712b2d4826efea2d8a829
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410583"
---
# <a name="predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="f1bf5-103">Predicción de precios mediante regresión con el Generador de modelos</span><span class="sxs-lookup"><span data-stu-id="f1bf5-103">Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="f1bf5-104">Obtenga información sobre cómo usar el Generador de modelos de ML.NET para crear un [modelo de regresión](../resources/glossary.md#regression) para predecir precios.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-104">Learn how to use ML.NET Model Builder to build a [regression model](../resources/glossary.md#regression) to predict prices.</span></span>  <span data-ttu-id="f1bf5-105">La aplicación de consola de .NET que desarrolla en este tutorial predice las tarifas de taxi en función de los datos históricos de tarifas de taxi de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="f1bf5-106">La plantilla de predicción de precios del Generador de modelos puede usarse para cualquier escenario que requiera la predicción de un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="f1bf5-107">Algunos escenarios de ejemplo son: predicción del precio de la vivienda, predicción de la demanda y previsión de ventas.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="f1bf5-108">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="f1bf5-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f1bf5-109">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="f1bf5-109">Prepare and understand the data</span></span>
> * <span data-ttu-id="f1bf5-110">Elegir un escenario</span><span class="sxs-lookup"><span data-stu-id="f1bf5-110">Choose a scenario</span></span>
> * <span data-ttu-id="f1bf5-111">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="f1bf5-111">Load the data</span></span>
> * <span data-ttu-id="f1bf5-112">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="f1bf5-112">Train the model</span></span>
> * <span data-ttu-id="f1bf5-113">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="f1bf5-113">Evaluate the model</span></span>
> * <span data-ttu-id="f1bf5-114">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="f1bf5-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="f1bf5-115">El Generador de modelos se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="f1bf5-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f1bf5-116">Pre-requisites</span></span>

<span data-ttu-id="f1bf5-117">Para obtener una lista de los requisitos previos e instrucciones de instalación, visite la [Guía de instalación del Generador de modelos](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="f1bf5-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f1bf5-118">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="f1bf5-118">Create a console application</span></span>

1. <span data-ttu-id="f1bf5-119">Cree una **aplicación de consola de .NET Core** denominada "TaxiFarePrediction".</span><span class="sxs-lookup"><span data-stu-id="f1bf5-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

1. <span data-ttu-id="f1bf5-120">Instale el paquete NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="f1bf5-120">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="f1bf5-121">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *TaxiFarePrediction* y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-121">In **Solution Explorer**, right-click the *TaxiFarePrediction* project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f1bf5-122">Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione el paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-122">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="f1bf5-123">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-123">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="f1bf5-124">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="f1bf5-124">Prepare and understand the data</span></span>

1. <span data-ttu-id="f1bf5-125">Cree un directorio denominado *Datos* en el proyecto para almacenarlos archivos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-125">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="f1bf5-126">Descargue el conjunto de datos [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) y guárdelo en la carpeta *Datos* que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-126">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) data set and save it to the *Data* folder you created at the previous step.</span></span> <span data-ttu-id="f1bf5-127">Este conjunto de datos se usa para entrenar y evaluar el modelo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-127">This data set is used to train and evaluate the machine learning model.</span></span> <span data-ttu-id="f1bf5-128">Este conjunto de datos procede originalmente del [conjunto de datos NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="f1bf5-128">This data set is originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="f1bf5-129">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *taxi-fare-train.csv* y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-129">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="f1bf5-130">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-130">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="f1bf5-131">Cada fila del conjunto de datos `taxi-fare-train.csv` contiene los detalles de los viajes realizados por un taxi.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-131">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span> 

1. <span data-ttu-id="f1bf5-132">Abra el conjunto de datos **train.csv de taxi y tarifas**.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-132">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="f1bf5-133">El conjunto de datos proporcionado contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1bf5-133">The provided data set contains the following columns:</span></span>

    * <span data-ttu-id="f1bf5-134">**vendor_id:** el identificador del taxista es una característica.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-134">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    * <span data-ttu-id="f1bf5-135">**rate_code:** el tipo de tarifa del viaje en taxi es una característica.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-135">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    * <span data-ttu-id="f1bf5-136">**passenger_count:** el número de pasajeros en el recorrido es una característica.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-136">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    * <span data-ttu-id="f1bf5-137">**trip_time_in_secs:** la cantidad de tiempo que tardó el viaje.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-137">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="f1bf5-138">Por ejemplo, si quiere calcular la tarifa del viaje antes de que termine</span><span class="sxs-lookup"><span data-stu-id="f1bf5-138">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="f1bf5-139">y aún no conoce la duración del viaje,</span><span class="sxs-lookup"><span data-stu-id="f1bf5-139">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="f1bf5-140">el tiempo del viaje no es una característica, por lo que deberá excluir esta columna del modelo.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-140">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    * <span data-ttu-id="f1bf5-141">**trip_distance:** la distancia del viaje es una característica.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-141">**trip_distance:** The distance of the trip is a feature.</span></span>
    * <span data-ttu-id="f1bf5-142">**payment_type:** el método de pago (efectivo o tarjeta de crédito) es una característica.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-142">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    * <span data-ttu-id="f1bf5-143">**fare_amount:** la tarifa de taxi total pagada es la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-143">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="f1bf5-144">`label` es la columna que quiere predecir.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-144">The `label` is the column you want to predict.</span></span> <span data-ttu-id="f1bf5-145">Al realizar una tarea de regresión, el objetivo es predecir un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-145">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="f1bf5-146">En este escenario de predicción de precio, se predice el coste de un viaje de taxi.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-146">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="f1bf5-147">Por lo tanto, **fare_amount** es la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-147">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="f1bf5-148">Los valores de `features` identificados son las entradas que se proporcionan al modelo para predecir `label`.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-148">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="f1bf5-149">En este caso, el resto de columnas se usan como entradas o características para predecir el importe de la tarifa.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-149">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="f1bf5-150">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="f1bf5-150">Choose a scenario</span></span>

<span data-ttu-id="f1bf5-151">Para entrenar el modelo, deberá seleccionarlo en la lista de escenarios de aprendizaje automático disponibles proporcionada por el Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-151">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="f1bf5-152">En este caso, el escenario es `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-152">In this case, the scenario is `Price Prediction`.</span></span> <span data-ttu-id="f1bf5-153">Para obtener una lista más amplia, visite el [artículo de información general del Generador de modelos](../automate-training-with-model-builder.md#scenarios).</span><span class="sxs-lookup"><span data-stu-id="f1bf5-153">For a more extensive list visit the [Model Builder overview article](../automate-training-with-model-builder.md#scenarios).</span></span>

1. <span data-ttu-id="f1bf5-154">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *TaxiFarePrediction* y seleccione **Agregar** > **Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-154">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="f1bf5-155">En el paso del escenario de la herramienta Generador de modelos, seleccione el escenario *Predicción de precio*.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-155">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="f1bf5-156">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="f1bf5-156">Load the data</span></span>

<span data-ttu-id="f1bf5-157">El Generador de modelos acepta datos de dos orígenes, una base de datos de SQL Server o un archivo local csv o tsv.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-157">Model Builder accepts data from two sources, a SQL Server database or a local file csv or tsv file.</span></span> <span data-ttu-id="f1bf5-158">Para obtener más información sobre los requisitos de formato de datos, visite el siguiente [vínculo](../how-to-guides/install-model-builder.md#limitations).</span><span class="sxs-lookup"><span data-stu-id="f1bf5-158">For more information on data format requirements, visit the following [link](../how-to-guides/install-model-builder.md#limitations).</span></span>

1. <span data-ttu-id="f1bf5-159">En el paso de datos de la herramienta Generador de modelos, seleccione *Archivo* en la lista desplegable origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-159">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="f1bf5-160">Seleccione el botón junto al cuadro de texto *Seleccionar un archivo* y use el Explorador de archivos para examinar y seleccionar *taxi-fare-test.csv* en el directorio *Datos*.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-160">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="f1bf5-161">Elija *fare_amount* en la lista desplegable *Etiqueta o columna para la predicción* y vaya al paso de entrenamiento de la herramienta Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-161">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="f1bf5-162">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="f1bf5-162">Train the model</span></span>

<span data-ttu-id="f1bf5-163">La tarea de aprendizaje automático que se usa para entrenar el modelo de predicción de precio en este tutorial es la regresión.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-163">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="f1bf5-164">Durante el proceso de entrenamiento de modelos, el Generador de modelos entrena modelos independientes usando diferentes opciones y algoritmos de regresión para encontrar el modelo con mejor rendimiento para el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-164">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="f1bf5-165">El tiempo necesario para el entrenamiento del modelo es proporcional a la cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-165">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="f1bf5-166">Use este gráfico como guía para seleccionar un valor adecuado para el campo `Time to train (seconds)`:</span><span class="sxs-lookup"><span data-stu-id="f1bf5-166">Use this chart as guidance to select an adequate value for the `Time to train (seconds)` field:</span></span>

<span data-ttu-id="f1bf5-167">\*Tamaño del conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="f1bf5-167">\*Dataset Size</span></span>  | <span data-ttu-id="f1bf5-168">Tipo de conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="f1bf5-168">Dataset Type</span></span>       | <span data-ttu-id="f1bf5-169">Prom. Tiempo de entrenamiento\*</span><span class="sxs-lookup"><span data-stu-id="f1bf5-169">Avg. Time to train\*</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="f1bf5-170">0 - 10 MB</span><span class="sxs-lookup"><span data-stu-id="f1bf5-170">0 - 10 Mb</span></span>     | <span data-ttu-id="f1bf5-171">Numérico y texto</span><span class="sxs-lookup"><span data-stu-id="f1bf5-171">Numeric and Text</span></span>   | <span data-ttu-id="f1bf5-172">10 s</span><span class="sxs-lookup"><span data-stu-id="f1bf5-172">10 sec</span></span>
<span data-ttu-id="f1bf5-173">10 - 100 MB</span><span class="sxs-lookup"><span data-stu-id="f1bf5-173">10 - 100 Mb</span></span>   | <span data-ttu-id="f1bf5-174">Numérico y texto</span><span class="sxs-lookup"><span data-stu-id="f1bf5-174">Numeric and Text</span></span>   | <span data-ttu-id="f1bf5-175">10 min</span><span class="sxs-lookup"><span data-stu-id="f1bf5-175">10 min</span></span>
<span data-ttu-id="f1bf5-176">100 - 500 MB</span><span class="sxs-lookup"><span data-stu-id="f1bf5-176">100 - 500 Mb</span></span>  | <span data-ttu-id="f1bf5-177">Numérico y texto</span><span class="sxs-lookup"><span data-stu-id="f1bf5-177">Numeric and Text</span></span>   | <span data-ttu-id="f1bf5-178">30 min</span><span class="sxs-lookup"><span data-stu-id="f1bf5-178">30 min</span></span>
<span data-ttu-id="f1bf5-179">500 - 1 GB</span><span class="sxs-lookup"><span data-stu-id="f1bf5-179">500 - 1 Gb</span></span>    | <span data-ttu-id="f1bf5-180">Numérico y texto</span><span class="sxs-lookup"><span data-stu-id="f1bf5-180">Numeric and Text</span></span>   | <span data-ttu-id="f1bf5-181">60 min</span><span class="sxs-lookup"><span data-stu-id="f1bf5-181">60 min</span></span>
<span data-ttu-id="f1bf5-182">1 GB o más</span><span class="sxs-lookup"><span data-stu-id="f1bf5-182">1 Gb+</span></span>         | <span data-ttu-id="f1bf5-183">Numérico y texto</span><span class="sxs-lookup"><span data-stu-id="f1bf5-183">Numeric and Text</span></span>   | <span data-ttu-id="f1bf5-184">Más de 3 horas</span><span class="sxs-lookup"><span data-stu-id="f1bf5-184">3 hour+</span></span>

1. <span data-ttu-id="f1bf5-185">Dado que el archivo de datos de entrenamiento es mayor de 10 MB, use 600 segundos (10 minutos) como valor en *Tiempo para entrenar (segundos)* .</span><span class="sxs-lookup"><span data-stu-id="f1bf5-185">Because the training data file is more than 10MB, use 600 seconds (10 minutes) as the value for *Time to train (seconds)*.</span></span>
2. <span data-ttu-id="f1bf5-186">Seleccione *Iniciar entrenamiento*.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-186">Select *Start Training*.</span></span>

<span data-ttu-id="f1bf5-187">Durante el proceso de entrenamiento, los datos de progreso se muestran en la sección `Progress` del paso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-187">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="f1bf5-188">En Estado se muestra el grado de finalización del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-188">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="f1bf5-189">En Mejor precisión se muestra la precisión del modelo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-189">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="f1bf5-190">Una mayor precisión significa que el modelo realiza una predicción más correcta de los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-190">Higher accuracy means the model predicted more correctly on test data.</span></span> 
- <span data-ttu-id="f1bf5-191">En Mejor algoritmo se muestra el nombre del algoritmo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-191">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="f1bf5-192">En Último algoritmo se muestra el nombre del algoritmo que ha usado más recientemente el Generador de modelos para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-192">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="f1bf5-193">Una vez completado el entrenamiento, vaya al paso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-193">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="f1bf5-194">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="f1bf5-194">Evaluate the model</span></span>

<span data-ttu-id="f1bf5-195">El resultado del paso de entrenamiento será un modelo que tenga el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-195">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="f1bf5-196">En el paso de evaluación de la herramienta Generador de modelos, la sección de salida contendrá el algoritmo usado por el modelo con el mejor rendimiento en la entrada *Mejor modelo* junto con las métricas en *Modelo de mayor calidad (RSquared)* .</span><span class="sxs-lookup"><span data-stu-id="f1bf5-196">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="f1bf5-197">Además de una tabla resumen que contiene los cinco mejores modelos y sus métricas.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-197">Additionally, a summary table containing top five models and their metrics.</span></span> <span data-ttu-id="f1bf5-198">Visite el vínculo siguiente para obtener más información sobre las [métricas de evaluación de modelos](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).</span><span class="sxs-lookup"><span data-stu-id="f1bf5-198">Visit the following link to learn more about [evaluating model metrics](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).</span></span>

<span data-ttu-id="f1bf5-199">Si no está satisfecho con las métricas de precisión, una forma sencilla de intentar mejorar la precisión del modelo es aumentar la cantidad de tiempo para entrenar el modelo o usar más datos.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-199">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="f1bf5-200">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="f1bf5-200">Use the model for predictions</span></span>

<span data-ttu-id="f1bf5-201">Se crearán dos proyectos como resultado del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-201">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="f1bf5-202">TaxiFarePredictionML.ConsoleApp: Una aplicación de consola de .NET que contiene el entrenamiento del modelo y el código de consumo.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-202">TaxiFarePredictionML.ConsoleApp: A .NET Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="f1bf5-203">TaxiFarePredictionML.Model: Una biblioteca de clases .NET Standard que contienen los modelos de datos que definen el esquema de entrada y salida de los datos del modelo, así como la versión persistente del modelo con mejor rendimiento durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-203">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="f1bf5-204">En la sección de código de la herramienta Generador de modelos, seleccione **Proyectos agregados** para agregar los proyectos a la solución.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-204">In the code section of the Model Builder tool, select **Added Projects** to add the projects to the solution.</span></span>
1. <span data-ttu-id="f1bf5-205">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-205">In solution explorer, right-click the *TaxiFarePrediction* project.</span></span> <span data-ttu-id="f1bf5-206">A continuación, seleccione **Agregar > Elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-206">Then, select **Add > Existing Item**.</span></span> <span data-ttu-id="f1bf5-207">Para la lista desplegable de tipos de archivo, seleccione `All Files`, vaya hasta el directorio del proyecto *TaxiFarePredictionML.Model* y seleccione el archivo `MLModel.zip`.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-207">For file type drop down, select `All Files`, navigate to the *TaxiFarePredictionML.Model* project directory and select the `MLModel.zip` file.</span></span> <span data-ttu-id="f1bf5-208">A continuación, haga clic con el botón derecho en el archivo agregado recientemente `MLModel.zip` y seleccione *Propiedades*.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-208">Then right-click the recently added `MLModel.zip` file and select *Properties*.</span></span> <span data-ttu-id="f1bf5-209">Para la opción Copiar en el directorio de resultados, seleccione *Copiar si es más reciente* en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-209">For the Copy to Output Directory option, select *Copy if Newer* from the dropdown.</span></span>
1. <span data-ttu-id="f1bf5-210">Haga clic con el botón derecho en el proyecto *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-210">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="f1bf5-211">A continuación, **Agregar > Referencia**.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-211">Then, **Add > Reference**.</span></span> <span data-ttu-id="f1bf5-212">Elija el nodo **Proyectos > Solución** y, en la lista, marque el proyecto *TaxiFarePredictionML.Model* y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-212">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>

4. <span data-ttu-id="f1bf5-213">Abra el archivo *Program.cs* en el proyecto *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-213">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
5. <span data-ttu-id="f1bf5-214">Agregue las siguientes instrucciones using:</span><span class="sxs-lookup"><span data-stu-id="f1bf5-214">Add the following using statements:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

6. <span data-ttu-id="f1bf5-215">Agregue el método `ConsumeModel` a la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-215">Add the `ConsumeModel` method to the `Program` class.</span></span> <span data-ttu-id="f1bf5-216">`ConsumeModel` creará un `PredictionEngine` según el modelo generado por el Generador de modelos para realizar predicciones sobre nuevos datos y los imprimirá en la consola.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-216">The `ConsumeModel` will create a `PredictionEngine` based on the model generated by Model Builder to make predictions on new data and print them out to the console.</span></span>

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

7. <span data-ttu-id="f1bf5-217">Agregue el siguiente código al método `Main` y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-217">Add the following code to the `Main` method and run the application.</span></span>

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

    <span data-ttu-id="f1bf5-218">La salida generada por el programa debe ser similar al siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="f1bf5-218">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="f1bf5-219">Si tiene que hacer referencia a los proyectos generados en un momento posterior dentro de otra solución, puede encontrarlos en el directorio `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-219">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f1bf5-220">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f1bf5-220">Next Steps</span></span>

<span data-ttu-id="f1bf5-221">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="f1bf5-221">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f1bf5-222">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="f1bf5-222">Prepare and understand the data</span></span>
> * <span data-ttu-id="f1bf5-223">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="f1bf5-223">Choose a scenario</span></span>
> * <span data-ttu-id="f1bf5-224">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="f1bf5-224">Load the data</span></span>
> * <span data-ttu-id="f1bf5-225">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="f1bf5-225">Train the model</span></span>
> * <span data-ttu-id="f1bf5-226">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="f1bf5-226">Evaluate the model</span></span>
> * <span data-ttu-id="f1bf5-227">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="f1bf5-227">Use the model for predictions</span></span>

<span data-ttu-id="f1bf5-228">Vaya a cualquiera de los siguientes artículos de procedimientos para aprender a implementar el modelo.</span><span class="sxs-lookup"><span data-stu-id="f1bf5-228">Advance to either of the following how-to articles to learn how to deploy your model.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f1bf5-229">Implementación de un modelo en Azure Functions</span><span class="sxs-lookup"><span data-stu-id="f1bf5-229">Deploy a model to Azure Functions</span></span>](../how-to-guides/serve-model-serverless-azure-functions-ml-net.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="f1bf5-230">Implementación de un modelo en una API Web</span><span class="sxs-lookup"><span data-stu-id="f1bf5-230">Deploy a model to a Web API</span></span>](../how-to-guides/serve-model-web-api-ml-net.md)

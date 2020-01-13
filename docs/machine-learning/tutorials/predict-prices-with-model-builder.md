---
title: 'Tutorial: Predicción de precios mediante regresión con el Generador de modelos'
description: En este tutorial se muestra cómo compilar un modelo de regresión con el Generador de modelos de ML.NET para predecir precios, en concreto, las tarifas de taxi de Nueva York.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 254f3c4c05a2c18f6182fc5f18d93114e20ed953
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344988"
---
# <a name="tutorial-predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="a9cfd-103">Tutorial: Predicción de precios mediante regresión con el Generador de modelos</span><span class="sxs-lookup"><span data-stu-id="a9cfd-103">Tutorial: Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="a9cfd-104">Obtenga información sobre cómo usar el Generador de modelos de ML.NET con el fin de compilar un modelo de regresión para predecir precios.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-104">Learn how to use ML.NET Model Builder to build a regression model to predict prices.</span></span>  <span data-ttu-id="a9cfd-105">La aplicación de consola de .NET que desarrolla en este tutorial predice las tarifas de taxi en función de los datos históricos de tarifas de taxi de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="a9cfd-106">La plantilla de predicción de precios del Generador de modelos puede usarse para cualquier escenario que requiera la predicción de un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="a9cfd-107">Algunos escenarios de ejemplo son: predicción del precio de la vivienda, predicción de la demanda y previsión de ventas.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="a9cfd-108">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="a9cfd-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="a9cfd-109">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="a9cfd-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="a9cfd-110">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="a9cfd-110">Choose a scenario</span></span>
> - <span data-ttu-id="a9cfd-111">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="a9cfd-111">Load the data</span></span>
> - <span data-ttu-id="a9cfd-112">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="a9cfd-112">Train the model</span></span>
> - <span data-ttu-id="a9cfd-113">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="a9cfd-113">Evaluate the model</span></span>
> - <span data-ttu-id="a9cfd-114">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="a9cfd-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="a9cfd-115">De momento, el Generador de modelos se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="a9cfd-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a9cfd-116">Pre-requisites</span></span>

<span data-ttu-id="a9cfd-117">Para obtener una lista de los requisitos previos e instrucciones de instalación, visite la [Guía de instalación del Generador de modelos](../how-to-guides/install-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="a9cfd-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="a9cfd-118">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="a9cfd-118">Create a console application</span></span>

1. <span data-ttu-id="a9cfd-119">Cree una **aplicación de consola .NET Core de C#** denominada "TaxiFarePrediction".</span><span class="sxs-lookup"><span data-stu-id="a9cfd-119">Create a **C# .NET Core Console Application** called "TaxiFarePrediction".</span></span> <span data-ttu-id="a9cfd-120">Asegúrese de que **Colocar la solución y el proyecto en el mismo directorio** está **desactivado** (VS 2019) o que **Crear directorio para la solución** está **activado** (VS 2017).</span><span class="sxs-lookup"><span data-stu-id="a9cfd-120">Make sure **Place solution and project in the same directory** is **unchecked** (VS 2019), or **Create directory for solution** is **checked** (VS 2017).</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="a9cfd-121">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="a9cfd-121">Prepare and understand the data</span></span>

1. <span data-ttu-id="a9cfd-122">Cree un directorio denominado *Datos* en el proyecto para almacenarlos archivos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-122">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="a9cfd-123">El conjunto de datos que se usa para entrenar y evaluar el modelo de Machine Learning procede originalmente del conjunto de datos NYC TLC Taxi Trip.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-123">The data set used to train and evaluate the machine learning model is originally from the NYC TLC Taxi Trip data set.</span></span>

    1. <span data-ttu-id="a9cfd-124">Para descargar el conjunto de datos, vaya al [vínculo de descarga de taxi-fare-train.csv](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span><span class="sxs-lookup"><span data-stu-id="a9cfd-124">To download the data set, navigate to the [taxi-fare-train.csv download link](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span></span>

    1. <span data-ttu-id="a9cfd-125">Cuando se cargue la página, haga clic con el botón derecho en cualquier parte de la página y seleccione **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-125">When the page loads, right-click anywhere on the page and select **Save as**.</span></span>

    1. <span data-ttu-id="a9cfd-126">Use el **cuadro de diálogo Guardar como** para guardar el archivo en la carpeta *Data* que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-126">Use the **Save As Dialog** to save the file in the *Data* folder you created at the previous step.</span></span>

1. <span data-ttu-id="a9cfd-127">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo *taxi-fare-train.csv* y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-127">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="a9cfd-128">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-128">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="a9cfd-129">Cada fila del conjunto de datos `taxi-fare-train.csv` contiene los detalles de los viajes realizados por un taxi.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-129">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="a9cfd-130">Abra el conjunto de datos **train.csv de taxi y tarifas**.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-130">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="a9cfd-131">El conjunto de datos proporcionado contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9cfd-131">The provided data set contains the following columns:</span></span>

    - <span data-ttu-id="a9cfd-132">**vendor_id:** el identificador del taxista es una característica.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-132">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    - <span data-ttu-id="a9cfd-133">**rate_code:** el tipo de tarifa del viaje en taxi es una característica.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-133">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    - <span data-ttu-id="a9cfd-134">**passenger_count:** el número de pasajeros en el recorrido es una característica.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-134">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    - <span data-ttu-id="a9cfd-135">**trip_time_in_secs:** la cantidad de tiempo que tardó el viaje.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-135">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="a9cfd-136">Por ejemplo, si quiere calcular la tarifa del viaje antes de que termine</span><span class="sxs-lookup"><span data-stu-id="a9cfd-136">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="a9cfd-137">y aún no conoce la duración del viaje,</span><span class="sxs-lookup"><span data-stu-id="a9cfd-137">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="a9cfd-138">el tiempo del viaje no es una característica, por lo que deberá excluir esta columna del modelo.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-138">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    - <span data-ttu-id="a9cfd-139">**trip_distance:** la distancia del viaje es una característica.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-139">**trip_distance:** The distance of the trip is a feature.</span></span>
    - <span data-ttu-id="a9cfd-140">**payment_type:** el método de pago (efectivo o tarjeta de crédito) es una característica.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-140">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    - <span data-ttu-id="a9cfd-141">**fare_amount:** la tarifa de taxi total pagada es la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-141">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="a9cfd-142">`label` es la columna que quiere predecir.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-142">The `label` is the column you want to predict.</span></span> <span data-ttu-id="a9cfd-143">Al realizar una tarea de regresión, el objetivo es predecir un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-143">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="a9cfd-144">En este escenario de predicción de precio, se predice el coste de un viaje de taxi.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-144">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="a9cfd-145">Por lo tanto, **fare_amount** es la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-145">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="a9cfd-146">Los valores de `features` identificados son las entradas que se proporcionan al modelo para predecir `label`.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-146">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="a9cfd-147">En este cas, el resto de las columnas, con la excepción de **trip_time_in_secs**, se usan como características o entradas para predecir el importe de la tarifa.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-147">In this case, the rest of the columns with the exception of **trip_time_in_secs** are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="a9cfd-148">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="a9cfd-148">Choose a scenario</span></span>

<span data-ttu-id="a9cfd-149">Para entrenar el modelo, deberá seleccionarlo en la lista de escenarios de aprendizaje automático disponibles proporcionada por el Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-149">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="a9cfd-150">En este caso, el escenario es `Price Prediction`.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-150">In this case, the scenario is `Price Prediction`.</span></span>

1. <span data-ttu-id="a9cfd-151">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *TaxiFarePrediction* y seleccione **Agregar** > **Machine Learning**.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-151">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="a9cfd-152">En el paso del escenario de la herramienta Generador de modelos, seleccione el escenario *Predicción de precio*.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-152">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="a9cfd-153">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="a9cfd-153">Load the data</span></span>

<span data-ttu-id="a9cfd-154">El Generador de modelos acepta datos de dos orígenes, una base de datos de SQL Server o un archivo local en formato .csv o .tsv.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-154">Model Builder accepts data from two sources, a SQL Server database or a local file in csv or tsv format.</span></span>

1. <span data-ttu-id="a9cfd-155">En el paso de datos de la herramienta Generador de modelos, seleccione *Archivo* en la lista desplegable origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-155">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="a9cfd-156">Seleccione el botón junto al cuadro de texto *Seleccionar un archivo* y use el Explorador de archivos para examinar y seleccionar *taxi-fare-test.csv* en el directorio *Datos*.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-156">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="a9cfd-157">Elija *fare_amount* en el menú desplegable *Column to Predict (Label)* (Columna para la predicción [etiqueta]).</span><span class="sxs-lookup"><span data-stu-id="a9cfd-157">Choose *fare_amount* in the *Column to Predict (Label)* dropdown.</span></span>
1. <span data-ttu-id="a9cfd-158">Expanda la lista desplegable *Input Columns (Features)* (Columnas de entrada [características]) y desactive la columna *trip_time_in_secs* para excluirla como característica durante el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-158">Expand the *Input Columns (Features)* dropdown and uncheck the *trip_time_in_secs* column to exclude it as a feature during training.</span></span>  <span data-ttu-id="a9cfd-159">Vaya al paso de entrenamiento de la herramienta Generador de modelos.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-159">Navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="a9cfd-160">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="a9cfd-160">Train the model</span></span>

<span data-ttu-id="a9cfd-161">La tarea de aprendizaje automático que se usa para entrenar el modelo de predicción de precio en este tutorial es la regresión.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-161">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="a9cfd-162">Durante el proceso de entrenamiento de modelos, el Generador de modelos entrena modelos independientes usando diferentes opciones y algoritmos de regresión para encontrar el modelo con mejor rendimiento para el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-162">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="a9cfd-163">El tiempo necesario para el entrenamiento del modelo es proporcional a la cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-163">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="a9cfd-164">El generador de modelos selecciona automáticamente un valor predeterminado para **Tiempo de entrenamiento (segundos)** en función del tamaño del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-164">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="a9cfd-165">Deje el valor predeterminado como está para *Tiempo de entrenamiento (segundos)* , a menos que prefiera entrenar durante más tiempo.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-165">Leave the default value as is for *Time to train (seconds)* unless you prefer to train for a longer time.</span></span>
2. <span data-ttu-id="a9cfd-166">Seleccione *Iniciar entrenamiento*.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-166">Select *Start Training*.</span></span>

<span data-ttu-id="a9cfd-167">Durante el proceso de entrenamiento, los datos de progreso se muestran en la sección `Progress` del paso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-167">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="a9cfd-168">En Estado se muestra el grado de finalización del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-168">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="a9cfd-169">En Mejor precisión se muestra la precisión del modelo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-169">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="a9cfd-170">Una mayor precisión significa que el modelo realiza una predicción más correcta de los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-170">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="a9cfd-171">En Mejor algoritmo se muestra el nombre del algoritmo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-171">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="a9cfd-172">En Último algoritmo se muestra el nombre del algoritmo que ha usado más recientemente el Generador de modelos para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-172">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="a9cfd-173">Una vez completado el entrenamiento, vaya al paso de evaluación.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-173">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="a9cfd-174">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="a9cfd-174">Evaluate the model</span></span>

<span data-ttu-id="a9cfd-175">El resultado del paso de entrenamiento será un modelo que tenga el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-175">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="a9cfd-176">En el paso de evaluación de la herramienta Generador de modelos, la sección de salida contendrá el algoritmo usado por el modelo con el mejor rendimiento en la entrada *Mejor modelo* junto con las métricas en *Modelo de mayor calidad (RSquared)* .</span><span class="sxs-lookup"><span data-stu-id="a9cfd-176">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="a9cfd-177">Además de una tabla resumen que contiene los cinco mejores modelos y sus métricas.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-177">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="a9cfd-178">Si no está satisfecho con las métricas de precisión, una forma sencilla de intentar mejorar la precisión del modelo es aumentar la cantidad de tiempo para entrenar el modelo o usar más datos.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-178">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="a9cfd-179">En caso contrario, vaya al paso de código.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-179">Otherwise, navigate to the code step.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="a9cfd-180">Incorporación del código para hacer predicciones</span><span class="sxs-lookup"><span data-stu-id="a9cfd-180">Add the code to make predictions</span></span>

<span data-ttu-id="a9cfd-181">Se crearán dos proyectos como resultado del proceso de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-181">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="a9cfd-182">TaxiFarePredictionML.ConsoleApp: Una aplicación de consola de .NET Core que contiene el entrenamiento del modelo y el código de consumo de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-182">TaxiFarePredictionML.ConsoleApp: A .NET Core Console application that contains the model training and sample consumption code.</span></span>
- <span data-ttu-id="a9cfd-183">TaxiFarePredictionML.Model: Una biblioteca de clase de .NET Standard que contiene los modelos de datos que definen el esquema de los datos de modelo de entrada y salida, la versión guardada del modelo con mejor rendimiento durante el entrenamiento y una clase auxiliar llamada `ConsumeModel` para hacer predicciones.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-183">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data, the saved version of the best performing model during training and a helper class called `ConsumeModel` to make predictions.</span></span>

1. <span data-ttu-id="a9cfd-184">En el paso de código de la herramienta Generador de modelos, seleccione **Agregar proyectos** para agregar a la solución los proyectos generados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-184">In the code step of the Model Builder tool, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="a9cfd-185">Abra el archivo *Program.cs* en el proyecto *TaxiFarePrediction*.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-185">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
1. <span data-ttu-id="a9cfd-186">Agregue la instrucción using siguiente para hacer referencia al proyecto *TaxiFarePredictionML.Model*:</span><span class="sxs-lookup"><span data-stu-id="a9cfd-186">Add the following using statement to reference the *TaxiFarePredictionML.Model* project:</span></span>

    ```csharp
    using System;
    using TaxiFarePredictionML.Model;
    ```

1. <span data-ttu-id="a9cfd-187">Para hacer una predicción según los datos nuevos con el modelo, cree una instancia nueva de la clase `ModelInput` dentro del método `Main` de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-187">To make a prediction on new data using the model, create a new instance of the `ModelInput` class inside the `Main` method of your application.</span></span> <span data-ttu-id="a9cfd-188">Observe que el importe de la tarifa no forma parte de la entrada.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-188">Notice that the fare amount is not part of the input.</span></span> <span data-ttu-id="a9cfd-189">Esto se debe a que el modelo generará la predicción para él.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-189">This is because the model will generate the prediction for it.</span></span>

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };
    ```

1. <span data-ttu-id="a9cfd-190">Use el método `Predict` de la clase `ConsumeModel`.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-190">Use the `Predict` method from the `ConsumeModel` class.</span></span> <span data-ttu-id="a9cfd-191">El método `Predict` carga el modelo entrenado, crea un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para el modelo y lo usa para realizar predicciones según los datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-191">The `Predict` method loads the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model and uses it to make predictions on new data.</span></span>

    ```csharp
    // Make prediction
    ModelOutput prediction = ConsumeModel.Predict(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

1. <span data-ttu-id="a9cfd-192">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-192">Run the application.</span></span>

    <span data-ttu-id="a9cfd-193">La salida generada por el programa debe ser similar al siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="a9cfd-193">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 14.96086
    ```

<span data-ttu-id="a9cfd-194">Si tiene que hacer referencia a los proyectos generados en un momento posterior dentro de otra solución, puede encontrarlos en el directorio `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-194">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a9cfd-195">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a9cfd-195">Next Steps</span></span>

<span data-ttu-id="a9cfd-196">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="a9cfd-196">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="a9cfd-197">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="a9cfd-197">Prepare and understand the data</span></span>
> - <span data-ttu-id="a9cfd-198">Elección de un escenario</span><span class="sxs-lookup"><span data-stu-id="a9cfd-198">Choose a scenario</span></span>
> - <span data-ttu-id="a9cfd-199">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="a9cfd-199">Load the data</span></span>
> - <span data-ttu-id="a9cfd-200">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="a9cfd-200">Train the model</span></span>
> - <span data-ttu-id="a9cfd-201">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="a9cfd-201">Evaluate the model</span></span>
> - <span data-ttu-id="a9cfd-202">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="a9cfd-202">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a9cfd-203">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a9cfd-203">Additional Resources</span></span>

<span data-ttu-id="a9cfd-204">Para más información sobre los temas mencionados en este tutorial, visite estos recursos:</span><span class="sxs-lookup"><span data-stu-id="a9cfd-204">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="a9cfd-205">Escenarios del Generador de modelos</span><span class="sxs-lookup"><span data-stu-id="a9cfd-205">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="a9cfd-206">Regresión</span><span class="sxs-lookup"><span data-stu-id="a9cfd-206">Regression</span></span>](../resources/glossary.md#regression)
- [<span data-ttu-id="a9cfd-207">Métricas de regresión del modelo</span><span class="sxs-lookup"><span data-stu-id="a9cfd-207">Regression Model Metrics</span></span>](../resources/metrics.md#evaluation-metrics-for-regression-and-recommendation)
- [<span data-ttu-id="a9cfd-208">Conjunto de datos NYC TLC Taxi Trip</span><span class="sxs-lookup"><span data-stu-id="a9cfd-208">NYC TLC Taxi Trip data set</span></span>](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

---
title: 'Tutorial: Predicción de precios mediante regresión'
description: En este tutorial se muestra cómo compilar un modelo de regresión con ML.NET para predecir precios, en concreto, las tarifas de taxi de Nueva York.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: 0a8ab9ca07d2d83f41b40a3f5782e8e7e201976f
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803240"
---
# <a name="tutorial-predict-prices-using-regression-with-mlnet"></a><span data-ttu-id="b6d53-103">Tutorial: Predicción de precios mediante regresión con ML.NET</span><span class="sxs-lookup"><span data-stu-id="b6d53-103">Tutorial: Predict prices using regression with ML.NET</span></span>

<span data-ttu-id="b6d53-104">En este tutorial se muestra cómo compilar un [modelo de regresión](../resources/glossary.md#regression) con ML.NET para predecir precios, en concreto, las tarifas de taxi de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="b6d53-104">This tutorial illustrates how to build a [regression model](../resources/glossary.md#regression) using ML.NET to predict prices, specifically, New York City taxi fares.</span></span>

<span data-ttu-id="b6d53-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="b6d53-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="b6d53-106">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="b6d53-106">Prepare and understand the data</span></span>
> * <span data-ttu-id="b6d53-107">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="b6d53-107">Load and transform the data</span></span>
> * <span data-ttu-id="b6d53-108">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="b6d53-108">Choose a learning algorithm</span></span>
> * <span data-ttu-id="b6d53-109">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="b6d53-109">Train the model</span></span>
> * <span data-ttu-id="b6d53-110">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="b6d53-110">Evaluate the model</span></span>
> * <span data-ttu-id="b6d53-111">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="b6d53-111">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b6d53-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b6d53-112">Prerequisites</span></span>

* <span data-ttu-id="b6d53-113">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="b6d53-113">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="b6d53-114">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="b6d53-114">Create a console application</span></span>

1. <span data-ttu-id="b6d53-115">Cree una **aplicación de consola de .NET Core** denominada "TaxiFarePrediction".</span><span class="sxs-lookup"><span data-stu-id="b6d53-115">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

1. <span data-ttu-id="b6d53-116">Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos y los archivos de modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-116">Create a directory named *Data* in your project to store the data set and model files.</span></span>

1. <span data-ttu-id="b6d53-117">Instale el paquete NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="b6d53-117">Install the **Microsoft.ML** NuGet Package:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="b6d53-118">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="b6d53-118">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="b6d53-119">Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione el paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="b6d53-119">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="b6d53-120">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="b6d53-120">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="b6d53-121">Haga lo mismo con el paquete NuGet **Microsoft.ML.FastTree**.</span><span class="sxs-lookup"><span data-stu-id="b6d53-121">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="b6d53-122">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="b6d53-122">Prepare and understand the data</span></span>

1. <span data-ttu-id="b6d53-123">Descargue los conjuntos de datos [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) y [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) y guárdelos en la carpeta *Datos* que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="b6d53-123">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="b6d53-124">Usaremos estos conjuntos de datos para entrenar el modelo de aprendizaje automático y, después, evaluar su precisión.</span><span class="sxs-lookup"><span data-stu-id="b6d53-124">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="b6d53-125">Estos conjuntos de datos proceden originalmente del [conjunto de datos NYC TLC Taxi Trip](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page).</span><span class="sxs-lookup"><span data-stu-id="b6d53-125">These data sets are originally from the [NYC TLC Taxi Trip data set](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page).</span></span>

1. <span data-ttu-id="b6d53-126">En el **Explorador de soluciones**, haga clic con el botón derecho en cada uno de los archivos \*.csv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b6d53-126">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="b6d53-127">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="b6d53-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="b6d53-128">Abra el conjunto de datos **taxi-fare-train.csv** y consulte los encabezados de columna de la primera fila.</span><span class="sxs-lookup"><span data-stu-id="b6d53-128">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="b6d53-129">Eche un vistazo a cada una de las columnas.</span><span class="sxs-lookup"><span data-stu-id="b6d53-129">Take a look at each of the columns.</span></span> <span data-ttu-id="b6d53-130">Estudie los datos y decida qué columnas son **características** y cuál es la **etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="b6d53-130">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="b6d53-131">`label` es la columna que quiere predecir.</span><span class="sxs-lookup"><span data-stu-id="b6d53-131">The `label` is the column you want to predict.</span></span> <span data-ttu-id="b6d53-132">Las `Features` identificadas son las entradas que proporciona al modelo para predecir la `Label`.</span><span class="sxs-lookup"><span data-stu-id="b6d53-132">The identified `Features`are the inputs you give the model to predict the `Label`.</span></span>

<span data-ttu-id="b6d53-133">El conjunto de datos proporcionado contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6d53-133">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="b6d53-134">**vendor_id:** el identificador del taxista es una característica.</span><span class="sxs-lookup"><span data-stu-id="b6d53-134">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="b6d53-135">**rate_code:** el tipo de tarifa del viaje en taxi es una característica.</span><span class="sxs-lookup"><span data-stu-id="b6d53-135">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="b6d53-136">**passenger_count:** el número de pasajeros en el recorrido es una característica.</span><span class="sxs-lookup"><span data-stu-id="b6d53-136">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="b6d53-137">**trip_time_in_secs:** la cantidad de tiempo que tardó el viaje.</span><span class="sxs-lookup"><span data-stu-id="b6d53-137">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="b6d53-138">Por ejemplo, si quiere calcular la tarifa del viaje antes de que termine</span><span class="sxs-lookup"><span data-stu-id="b6d53-138">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="b6d53-139">y aún no conoce la duración del viaje,</span><span class="sxs-lookup"><span data-stu-id="b6d53-139">At that moment, you don't know how long the trip would take.</span></span> <span data-ttu-id="b6d53-140">el tiempo del viaje no es una característica, por lo que deberá excluir esta columna del modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-140">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="b6d53-141">**trip_distance:** la distancia del viaje es una característica.</span><span class="sxs-lookup"><span data-stu-id="b6d53-141">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="b6d53-142">**payment_type:** el método de pago (efectivo o tarjeta de crédito) es una característica.</span><span class="sxs-lookup"><span data-stu-id="b6d53-142">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="b6d53-143">**fare_amount:** la tarifa de taxi total pagada es la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="b6d53-143">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="b6d53-144">Crear clases de datos</span><span class="sxs-lookup"><span data-stu-id="b6d53-144">Create data classes</span></span>

<span data-ttu-id="b6d53-145">Cree clases para los datos de entrada y las predicciones:</span><span class="sxs-lookup"><span data-stu-id="b6d53-145">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="b6d53-146">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b6d53-146">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="b6d53-147">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="b6d53-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="b6d53-148">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b6d53-148">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="b6d53-149">Agregue las siguientes directivas `using` al nuevo archivo:</span><span class="sxs-lookup"><span data-stu-id="b6d53-149">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="b6d53-150">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `TaxiTrip` y `TaxiTripFarePrediction`, al archivo *TaxiTrip.cs*:</span><span class="sxs-lookup"><span data-stu-id="b6d53-150">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="b6d53-151">`TaxiTrip` es la clase de datos de entrada y tiene definiciones para cada una de las columnas del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-151">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="b6d53-152">Use el atributo <xref:Microsoft.ML.Data.LoadColumnAttribute> para especificar los índices de las columnas de origen en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-152">Use the <xref:Microsoft.ML.Data.LoadColumnAttribute> attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="b6d53-153">La clase `TaxiTripFarePrediction` representa los resultados predichos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-153">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="b6d53-154">Tiene un único campo flotante, `FareAmount`, con un atributo `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> aplicado.</span><span class="sxs-lookup"><span data-stu-id="b6d53-154">It has a single float field, `FareAmount`, with a `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> attribute applied.</span></span> <span data-ttu-id="b6d53-155">En el caso de la tarea de regresión, la columna **Score** contiene valores de etiqueta predichos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-155">In case of the regression task, the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="b6d53-156">Use el tipo `float` para representar los valores de punto flotante en las clases de entrada y predicción de datos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-156">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

### <a name="define-data-and-model-paths"></a><span data-ttu-id="b6d53-157">Definir rutas de acceso de datos y modelos</span><span class="sxs-lookup"><span data-stu-id="b6d53-157">Define data and model paths</span></span>

<span data-ttu-id="b6d53-158">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="b6d53-158">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="b6d53-159">Deberá crear tres campos que contengan las rutas de acceso a los archivos con los conjuntos de datos y el archivo para guardar el modelo:</span><span class="sxs-lookup"><span data-stu-id="b6d53-159">You need to create three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="b6d53-160">`_trainDataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-160">`_trainDataPath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="b6d53-161">`_testDataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-161">`_testDataPath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="b6d53-162">`_modelPath` contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="b6d53-162">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="b6d53-163">Agregue el código siguiente justo encima del método `Main` para especificar esas rutas de acceso y la variable `_textLoader`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-163">Add the following code right above the `Main` method to specify those paths and for the `_textLoader` variable:</span></span>

[!code-csharp[InitializePaths](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="b6d53-164">Todas las operaciones de ML.NET se inician en la [clase MLContext](xref:Microsoft.ML.MLContext).</span><span class="sxs-lookup"><span data-stu-id="b6d53-164">All ML.NET operations start in the [MLContext class](xref:Microsoft.ML.MLContext).</span></span> <span data-ttu-id="b6d53-165">La inicialización de `mlContext` crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-165">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="b6d53-166">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="b6d53-166">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="b6d53-167">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="b6d53-167">Initialize variables in Main</span></span>

<span data-ttu-id="b6d53-168">Reemplace la línea `Console.WriteLine("Hello World!")` del método `Main` por el siguiente código para declarar e inicializar la variable `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-168">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

[!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="b6d53-169">Agregue lo siguiente como la siguiente línea de código en el método `Main` para llamar al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-169">Add the following as the next line of code in the `Main` method to call the `Train` method:</span></span>

[!code-csharp[Train](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#5 "Train your model")]

<span data-ttu-id="b6d53-170">El método `Train()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6d53-170">The `Train()` method executes the following tasks:</span></span>

* <span data-ttu-id="b6d53-171">Carga los datos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-171">Loads the data.</span></span>
* <span data-ttu-id="b6d53-172">Extrae y transforma los datos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-172">Extracts and transforms the data.</span></span>
* <span data-ttu-id="b6d53-173">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-173">Trains the model.</span></span>
* <span data-ttu-id="b6d53-174">Devuelve el modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-174">Returns the model.</span></span>

<span data-ttu-id="b6d53-175">El método `Train` entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-175">The `Train` method trains the model.</span></span> <span data-ttu-id="b6d53-176">Cree ese método justo debajo de `Main` utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d53-176">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

## <a name="load-and-transform-data"></a><span data-ttu-id="b6d53-177">Cargar y transformar datos</span><span class="sxs-lookup"><span data-stu-id="b6d53-177">Load and transform data</span></span>

<span data-ttu-id="b6d53-178">ML.NET usa la [clase IDataView](xref:Microsoft.ML.IDataView) como una forma flexible y eficaz de describir datos tabulares de texto o numéricos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-178">ML.NET uses the [IDataView class](xref:Microsoft.ML.IDataView) as a flexible, efficient way of describing numeric or text tabular data.</span></span> <span data-ttu-id="b6d53-179">`IDataView` puede cargar archivos de texto o en tiempo real (por ejemplo, una base de datos SQL o archivos de registro).</span><span class="sxs-lookup"><span data-stu-id="b6d53-179">`IDataView` can load either text files or in real time (for example, SQL database or log files).</span></span> <span data-ttu-id="b6d53-180">Agregue el código siguiente a la primera línea del método `Train()`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-180">Add the following code as the first line of the `Train()` method:</span></span>

[!code-csharp[LoadTrainData](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#6 "loading training dataset")]

<span data-ttu-id="b6d53-181">Como quiere predecir la tarifa de carreras de taxi, la columna `FareAmount` es la `Label` que va a predecir (la salida del modelo).</span><span class="sxs-lookup"><span data-stu-id="b6d53-181">As you want to predict the taxi trip fare, the `FareAmount` column is the `Label` that you will predict (the output of the model).</span></span> <span data-ttu-id="b6d53-182">Para ello, use la clase de transformación `CopyColumnsEstimator` para copiar `FareAmount` y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d53-182">Use the `CopyColumnsEstimator` transformation class to copy `FareAmount`, and add the following code:</span></span>

[!code-csharp[CopyColumnsEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#7 "Use the CopyColumnsEstimator")]

<span data-ttu-id="b6d53-183">El algoritmo que entrena el modelo requiere características **numéricas**, por lo que debe transformar los datos de categorías (`VendorId`, `RateCode` y `PaymentType`) en números (`VendorIdEncoded`, `RateCodeEncoded` y `PaymentTypeEncoded`).</span><span class="sxs-lookup"><span data-stu-id="b6d53-183">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers (`VendorIdEncoded`, `RateCodeEncoded`, and `PaymentTypeEncoded`).</span></span> <span data-ttu-id="b6d53-184">Para ello, use la clase de transformación [OneHotEncodingTransformer](xref:Microsoft.ML.Transforms.OneHotEncodingTransformer), que asigna diferentes valores de clave numéricos a los distintos valores de cada una de las columnas y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d53-184">To do that, use the [OneHotEncodingTransformer](xref:Microsoft.ML.Transforms.OneHotEncodingTransformer) transformation class, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

[!code-csharp[OneHotEncodingEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#8 "Use the OneHotEncodingEstimator")]

<span data-ttu-id="b6d53-185">En el último paso para la preparación de los datos, se combinan todas las columnas de característica en la columna **Características** mediante la clase de transformación `mlContext.Transforms.Concatenate`.</span><span class="sxs-lookup"><span data-stu-id="b6d53-185">The last step in data preparation combines all of the feature columns into the **Features** column using the `mlContext.Transforms.Concatenate` transformation class.</span></span> <span data-ttu-id="b6d53-186">De forma predeterminada, un algoritmo de aprendizaje solo procesa las características de la columna **Features**.</span><span class="sxs-lookup"><span data-stu-id="b6d53-186">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="b6d53-187">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d53-187">Add the following code:</span></span>

[!code-csharp[ColumnConcatenatingEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="b6d53-188">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="b6d53-188">Choose a learning algorithm</span></span>

<span data-ttu-id="b6d53-189">Este problema consiste en predecir la tarifa de una carrera de taxi en la ciudad de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="b6d53-189">This problem is about predicting a taxi trip fare in New York City.</span></span> <span data-ttu-id="b6d53-190">A primera vista, puede parecer que simplemente depende de la distancia recorrida.</span><span class="sxs-lookup"><span data-stu-id="b6d53-190">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="b6d53-191">Sin embargo, los taxistas de Nueva York cobran distintas cantidades por otros factores, como llevar pasajeros adicionales o pagar con tarjeta de crédito en lugar de efectivo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-191">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span> <span data-ttu-id="b6d53-192">Quiere predecir el valor de precio, que es un valor real, en función de los demás factores del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-192">You want to predict the price value, which is a real value, based on the other factors in the dataset.</span></span> <span data-ttu-id="b6d53-193">Para ello, se elige una tarea de aprendizaje automático de [regresión](../resources/glossary.md#regression).</span><span class="sxs-lookup"><span data-stu-id="b6d53-193">To do that, you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

<span data-ttu-id="b6d53-194">Anexe la tarea de aprendizaje automático [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer) a las definiciones de transformación de datos al agregar esto como siguiente línea de código de `Train()`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-194">Append the [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer) machine learning task to the data transformation definitions by adding the following as the next line of code in `Train()`:</span></span>

[!code-csharp[FastTreeRegressionTrainer](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="b6d53-195">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="b6d53-195">Train the model</span></span>

<span data-ttu-id="b6d53-196">Ajuste el modelo a la `dataview` de entrenamiento y devuelva el modelo entrenado agregando la siguiente línea de código en el método `Train()`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-196">Fit the model to the training `dataview` and return the trained model by adding the following line of code in the `Train()` method:</span></span>

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#11 "Train the model")]

<span data-ttu-id="b6d53-197">El método [Fit()](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) entrena el modelo al transformar el conjunto de datos y aplicar el aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="b6d53-197">The [Fit()](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="b6d53-198">Devuelva el modelo entrenado con la siguiente línea de código en el método `Train()`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-198">Return the trained model with the following line of code in the `Train()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#12 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="b6d53-199">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="b6d53-199">Evaluate the model</span></span>

<span data-ttu-id="b6d53-200">Luego evalúe el rendimiento del modelo con los datos de prueba de control de calidad y validación.</span><span class="sxs-lookup"><span data-stu-id="b6d53-200">Next, evaluate your model performance with your test data for quality assurance and validation.</span></span> <span data-ttu-id="b6d53-201">Cree el método `Evaluate()`, justo después de `Train()`, con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d53-201">Create the `Evaluate()` method, just after `Train()`, with the following code:</span></span>

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="b6d53-202">El método `Evaluate` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6d53-202">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="b6d53-203">Carga el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="b6d53-203">Loads the test dataset.</span></span>
* <span data-ttu-id="b6d53-204">Crea el evaluador de regresión.</span><span class="sxs-lookup"><span data-stu-id="b6d53-204">Creates the regression evaluator.</span></span>
* <span data-ttu-id="b6d53-205">Evalúa el modelo y crea las métricas.</span><span class="sxs-lookup"><span data-stu-id="b6d53-205">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="b6d53-206">Muestra las métricas.</span><span class="sxs-lookup"><span data-stu-id="b6d53-206">Displays the metrics.</span></span>

<span data-ttu-id="b6d53-207">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Train`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d53-207">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#14 "Call the Evaluate method")]

<span data-ttu-id="b6d53-208">Cargue el conjunto de datos de prueba con el método [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A).</span><span class="sxs-lookup"><span data-stu-id="b6d53-208">Load the test dataset using the [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) method.</span></span> <span data-ttu-id="b6d53-209">Evalúe el modelo con este conjunto de datos como control de calidad al agregar el código siguiente en el método `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-209">Evaluate the model using this dataset as a quality check by adding the following code in the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#15 "Load the test dataset")]

<span data-ttu-id="b6d53-210">Luego transforme los datos de `Test` al agregar el código siguiente a `Evaluate()`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-210">Next, transform the `Test` data by adding the following code to `Evaluate()`:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#16 "Predict using the Transformer")]

<span data-ttu-id="b6d53-211">El método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) realiza predicciones para las filas de entrada del conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="b6d53-211">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for the test dataset input rows.</span></span>

<span data-ttu-id="b6d53-212">El método `RegressionContext.Evaluate` calcula las métricas de calidad para `PredictionModel` mediante el conjunto de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="b6d53-212">The `RegressionContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="b6d53-213">Devuelve un objeto <xref:Microsoft.ML.Data.RegressionMetrics> que contiene las métricas totales calculadas por evaluadores de regresión.</span><span class="sxs-lookup"><span data-stu-id="b6d53-213">It returns a <xref:Microsoft.ML.Data.RegressionMetrics> object that contains the overall metrics computed by regression evaluators.</span></span>

<span data-ttu-id="b6d53-214">Para mostrar estos elementos a fin de determinar la calidad del modelo, debe obtener primero las métricas.</span><span class="sxs-lookup"><span data-stu-id="b6d53-214">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="b6d53-215">Agregue el siguiente código como la siguiente línea en el método `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-215">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#17 "Compute Metrics")]

<span data-ttu-id="b6d53-216">Una vez que se ha establecido la predicción, el método [Evaluate()](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) valora el modelo, que compara los valores predichos con las `Labels` reales del conjunto de datos de prueba y devuelve métricas sobre el rendimiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-216">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="b6d53-217">Agregue el código siguiente para evaluar el modelo y generar las métricas de evaluación:</span><span class="sxs-lookup"><span data-stu-id="b6d53-217">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

<span data-ttu-id="b6d53-218">[RSquared](../resources/glossary.md#coefficient-of-determination) es otra métrica de evaluación de modelos de regresión.</span><span class="sxs-lookup"><span data-stu-id="b6d53-218">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="b6d53-219">RSquared muestra valores comprendidos entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="b6d53-219">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="b6d53-220">Cuanto más se acerque el valor a 1, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-220">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="b6d53-221">Agregue el código siguiente al método `Evaluate` para mostrar el valor de RSquared:</span><span class="sxs-lookup"><span data-stu-id="b6d53-221">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#18 "Display the RSquared metric.")]

<span data-ttu-id="b6d53-222">[RMS](../resources/glossary.md#root-of-mean-squared-error-rmse) es una de las métricas de evaluación del modelo de regresión.</span><span class="sxs-lookup"><span data-stu-id="b6d53-222">[RMS](../resources/glossary.md#root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="b6d53-223">Cuanto menor sea su valor, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-223">The lower it is, the better the model is.</span></span> <span data-ttu-id="b6d53-224">Agregue el código siguiente al método `Evaluate` para mostrar el valor de RMS:</span><span class="sxs-lookup"><span data-stu-id="b6d53-224">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="b6d53-225">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="b6d53-225">Use the model for predictions</span></span>

<span data-ttu-id="b6d53-226">Cree el método `TestSinglePrediction`, justo después del método `Evaluate`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d53-226">Create the `TestSinglePrediction` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void TestSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="b6d53-227">El método `TestSinglePrediction` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6d53-227">The `TestSinglePrediction` method executes the following tasks:</span></span>

* <span data-ttu-id="b6d53-228">Crea un único comentario de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="b6d53-228">Creates a single comment of test data.</span></span>
* <span data-ttu-id="b6d53-229">Predice la tarifa según los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="b6d53-229">Predicts fare amount based on test data.</span></span>
* <span data-ttu-id="b6d53-230">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="b6d53-230">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="b6d53-231">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="b6d53-231">Displays the predicted results.</span></span>

<span data-ttu-id="b6d53-232">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6d53-232">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallTestSinglePrediction](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#20 "Call the TestSinglePrediction method")]

<span data-ttu-id="b6d53-233">Use `PredictionEngine` para predecir la tarifa al agregar el código siguiente a `TestSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-233">Use the `PredictionEngine` to predict the fare by adding the following code to `TestSinglePrediction()`:</span></span>

[!code-csharp[MakePredictionEngine](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#22 "Create the PredictionFunction")]

<span data-ttu-id="b6d53-234">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-234">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="b6d53-235">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-235">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="b6d53-236">Es aceptable usarlo en entornos de un solo subproceso o prototipo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-236">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="b6d53-237">Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b6d53-237">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="b6d53-238">Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="b6d53-238">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="b6d53-239">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="b6d53-239">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="b6d53-240">En este tutorial se utiliza un viaje de prueba en esta clase.</span><span class="sxs-lookup"><span data-stu-id="b6d53-240">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="b6d53-241">Más adelante, puede agregar otros escenarios para experimentar con el modelo.</span><span class="sxs-lookup"><span data-stu-id="b6d53-241">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="b6d53-242">Agregue un viaje para probar la predicción de costo del modelo entrenado en el método `TestSinglePrediction()` mediante la creación de una instancia de `TaxiTrip`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-242">Add a trip to test the trained model's prediction of cost in the `TestSinglePrediction()` method by creating an instance of `TaxiTrip`:</span></span>

[!code-csharp[PredictionData](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#23 "Create test data for single prediction")]

<span data-ttu-id="b6d53-243">Luego, prediga el importe del servicio según una instancia única de los datos de carreras de taxi y páselo a la clase `PredictionEngine` agregando lo siguiente como próximas líneas de código en el método `TestSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-243">Next, predict the fare based on a single instance of the taxi trip data and pass it to the `PredictionEngine` by adding the following as the next lines of code in the `TestSinglePrediction()` method:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#24 "Create a prediction of taxi fare")]

<span data-ttu-id="b6d53-244">La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción sobre una única instancia de datos.</span><span class="sxs-lookup"><span data-stu-id="b6d53-244">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single instance of data.</span></span>

<span data-ttu-id="b6d53-245">Para mostrar la tarifa prevista del viaje especificado, agregue el código siguiente al método `TestSinglePrediction`:</span><span class="sxs-lookup"><span data-stu-id="b6d53-245">To display the predicted fare of the specified trip, add the following code into the `TestSinglePrediction` method:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#25 "Display the prediction.")]

<span data-ttu-id="b6d53-246">Ejecute el programa para ver la tarifa de taxi predicha para su caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="b6d53-246">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="b6d53-247">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="b6d53-247">Congratulations!</span></span> <span data-ttu-id="b6d53-248">Ya ha creado correctamente un modelo de aprendizaje automático para predecir tarifas de viajes en taxi, ha evaluado su precisión y lo ha usado para hacer predicciones.</span><span class="sxs-lookup"><span data-stu-id="b6d53-248">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="b6d53-249">Puede encontrar el código fuente de este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) de GitHub.</span><span class="sxs-lookup"><span data-stu-id="b6d53-249">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b6d53-250">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b6d53-250">Next steps</span></span>

<span data-ttu-id="b6d53-251">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="b6d53-251">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="b6d53-252">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="b6d53-252">Prepare and understand the data</span></span>
> * <span data-ttu-id="b6d53-253">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="b6d53-253">Create a learning pipeline</span></span>
> * <span data-ttu-id="b6d53-254">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="b6d53-254">Load and transform the data</span></span>
> * <span data-ttu-id="b6d53-255">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="b6d53-255">Choose a learning algorithm</span></span>
> * <span data-ttu-id="b6d53-256">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="b6d53-256">Train the model</span></span>
> * <span data-ttu-id="b6d53-257">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="b6d53-257">Evaluate the model</span></span>
> * <span data-ttu-id="b6d53-258">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="b6d53-258">Use the model for predictions</span></span>

<span data-ttu-id="b6d53-259">Siga con el siguiente tutorial para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b6d53-259">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b6d53-260">Agrupación en clústeres de iris</span><span class="sxs-lookup"><span data-stu-id="b6d53-260">Iris clustering</span></span>](iris-clustering.md)

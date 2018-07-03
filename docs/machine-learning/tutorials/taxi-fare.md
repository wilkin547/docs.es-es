---
title: Uso de ML.NET para predecir las tarifas de taxi de Nueva York (regresión)
description: Obtenga información acerca de cómo usar ML.NET en un escenario de regresión.
author: aditidugar
ms.author: johalex
ms.date: 06/05/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 048ed1d38408c1ba4901c554cae33d5552c9e303
ms.sourcegitcommit: 5b0802832fb9ad684d34e69b8644a16a5b7c4810
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2018
ms.locfileid: "34860708"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a><span data-ttu-id="3ac34-103">Tutorial: Uso de ML.NET para predecir las tarifas de taxi de Nueva York (regresión)</span><span class="sxs-lookup"><span data-stu-id="3ac34-103">Tutorial: Use ML.NET to predict New York taxi fares (regression)</span></span>

> [!NOTE]
> <span data-ttu-id="3ac34-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="3ac34-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="3ac34-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="3ac34-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="3ac34-106">En este tutorial se muestra cómo utilizar ML.NET para generar un [modelo de regresión](../resources/glossary.md#regression) para predecir las tarifas de taxi de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="3ac34-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting New York City taxi fares.</span></span>

<span data-ttu-id="3ac34-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="3ac34-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="3ac34-108">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="3ac34-108">Understand the problem</span></span>
> * <span data-ttu-id="3ac34-109">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="3ac34-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="3ac34-110">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="3ac34-110">Prepare and understand your data</span></span>
> * <span data-ttu-id="3ac34-111">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="3ac34-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="3ac34-112">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="3ac34-112">Load and transform your data</span></span>
> * <span data-ttu-id="3ac34-113">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="3ac34-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="3ac34-114">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="3ac34-114">Train the model</span></span>
> * <span data-ttu-id="3ac34-115">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="3ac34-115">Evaluate the model</span></span>
> * <span data-ttu-id="3ac34-116">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="3ac34-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ac34-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3ac34-117">Prerequisites</span></span>

* <span data-ttu-id="3ac34-118">[Visual Studio 2017 15.6 o posterior](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="3ac34-118">[Visual Studio 2017 15.6 or later](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="3ac34-119">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="3ac34-119">Understand the problem</span></span>

<span data-ttu-id="3ac34-120">Este problema se centra en **predecir la tarifa de un viaje en taxi en Nueva York**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-120">This problem is centered around **predicting the fare of a taxi trip in New York City**.</span></span> <span data-ttu-id="3ac34-121">A primera vista, puede parecer que simplemente depende de la distancia recorrida.</span><span class="sxs-lookup"><span data-stu-id="3ac34-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="3ac34-122">Sin embargo, los taxistas de Nueva York cobran distintas cantidades por otros factores, como llevar pasajeros adicionales o pagar con tarjeta de crédito en lugar de efectivo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="3ac34-123">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="3ac34-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="3ac34-124">Para predecir la tarifa del taxi, primero seleccione la tarea de aprendizaje automático adecuada.</span><span class="sxs-lookup"><span data-stu-id="3ac34-124">To predict the taxi fare, you first select the appropriate machine learning task.</span></span> <span data-ttu-id="3ac34-125">Está buscando predecir un valor real (un doble que representa el precio) en función de los otros factores del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="3ac34-125">You are looking to predict a real value (a double that represents price) based on the other factors in the dataset.</span></span> <span data-ttu-id="3ac34-126">Elige una tarea de [**regresión**](../resources/glossary.md#regression).</span><span class="sxs-lookup"><span data-stu-id="3ac34-126">You choose a [**regression**](../resources/glossary.md#regression) task.</span></span>

<span data-ttu-id="3ac34-127">El proceso de entrenamiento del modelo identifica qué factores del conjunto de datos son más influyentes al predecir el precio de la tarifa final.</span><span class="sxs-lookup"><span data-stu-id="3ac34-127">The process of training the model identifies which factors in the dataset are most influential when predicting the final fare price.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="3ac34-128">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="3ac34-128">Create a console application</span></span>

1. <span data-ttu-id="3ac34-129">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="3ac34-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="3ac34-130">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="3ac34-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="3ac34-131">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="3ac34-132">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="3ac34-133">En el cuadro de texto **Nombre**, escriba "TaxiFarePrediction" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

2. <span data-ttu-id="3ac34-134">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="3ac34-134">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="3ac34-135">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-135">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="3ac34-136">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="3ac34-136">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="3ac34-137">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="3ac34-137">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="3ac34-138">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-138">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="3ac34-139">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-139">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="3ac34-140">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="3ac34-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-and-understand-your-data"></a><span data-ttu-id="3ac34-141">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="3ac34-141">Prepare and understand your data</span></span>

1. <span data-ttu-id="3ac34-142">Descargue los conjuntos de datos [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) y [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) y guárdelos en la carpeta *Datos* creada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3ac34-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="3ac34-143">El conjunto de datos de tarifas de taxi entrena el modelo de aprendizaje automático y puede usarse para evaluar su grado de precisión.</span><span class="sxs-lookup"><span data-stu-id="3ac34-143">The Taxi Trip data set trains the machine learning model and can be used to evaluate how accurate your model is.</span></span> <span data-ttu-id="3ac34-144">Estos conjuntos de datos proceden originalmente del [conjunto de datos NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="3ac34-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

2. <span data-ttu-id="3ac34-145">En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.csv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-145">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="3ac34-146">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** a **Siempre**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Always**.</span></span>

3. <span data-ttu-id="3ac34-147">Abra el conjunto de datos **taxi-fare-train.csv** en el editor de código y fíjese en los encabezados de columna de la primera fila.</span><span class="sxs-lookup"><span data-stu-id="3ac34-147">Open the **taxi-fare-train.csv** data set in the code editor and look at column headers in the first row.</span></span> <span data-ttu-id="3ac34-148">Eche un vistazo a cada una de las columnas.</span><span class="sxs-lookup"><span data-stu-id="3ac34-148">Take a look at each of the columns.</span></span> <span data-ttu-id="3ac34-149">Comprenda los datos y decida qué columnas son **características** y cuál es la **etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-149">Understand the data and decide which columns are **features** and which is the **label**.</span></span>

<span data-ttu-id="3ac34-150">La **etiqueta** es el identificador de la columna que está intentando predecir.</span><span class="sxs-lookup"><span data-stu-id="3ac34-150">The **label** is the identifier of the column you are trying to predict.</span></span> <span data-ttu-id="3ac34-151">Las **características** identificadas se usan para predecir la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="3ac34-151">The identified **features** are used to predict the label.</span></span>

* <span data-ttu-id="3ac34-152">**vendor_id:** el identificador del taxista es una característica.</span><span class="sxs-lookup"><span data-stu-id="3ac34-152">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="3ac34-153">**rate_code:** el tipo de tarifa del viaje en taxi es una característica.</span><span class="sxs-lookup"><span data-stu-id="3ac34-153">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="3ac34-154">**passenger_count:** el número de pasajeros en el recorrido es una característica.</span><span class="sxs-lookup"><span data-stu-id="3ac34-154">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="3ac34-155">**trip_time_in_secs:** la cantidad de tiempo que tardó el viaje.</span><span class="sxs-lookup"><span data-stu-id="3ac34-155">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="3ac34-156">No sabrá cuánto tiempo tarda el recorrido hasta que se haya completado.</span><span class="sxs-lookup"><span data-stu-id="3ac34-156">You won't know how long the trip takes until after it is completed.</span></span> <span data-ttu-id="3ac34-157">Excluya esta columna del modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-157">You exclude this column from the model.</span></span>
* <span data-ttu-id="3ac34-158">**trip_distance:** la distancia del viaje es una característica.</span><span class="sxs-lookup"><span data-stu-id="3ac34-158">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="3ac34-159">**payment_type:** el método de pago (efectivo o tarjeta de crédito) es una característica.</span><span class="sxs-lookup"><span data-stu-id="3ac34-159">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="3ac34-160">**fare_amount:** la tarifa de taxi total pagada es la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="3ac34-160">**fare_amount:** The total taxi fare paid is the label.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="3ac34-161">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="3ac34-161">Create classes and define paths</span></span>

<span data-ttu-id="3ac34-162">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="3ac34-162">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="3ac34-163">Debe crear tres variables globales para contener la ruta de acceso a los archivos descargados recientemente y para guardar el modelo:</span><span class="sxs-lookup"><span data-stu-id="3ac34-163">You need to create three global variables to hold the paths to the recently downloaded files and to save the model:</span></span>

* <span data-ttu-id="3ac34-164">`_datapath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-164">`_datapath` has the path to the data set used to train the model.</span></span>
* <span data-ttu-id="3ac34-165">`_testdatapath` tiene la ruta de acceso al conjunto de datos utilizado para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-165">`_testdatapath` has the path to the data set used to evaluate the model.</span></span>
* <span data-ttu-id="3ac34-166">`_modelpath` tiene la ruta de acceso donde se almacena el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="3ac34-166">`_modelpath` has the path where the trained model is stored.</span></span>

<span data-ttu-id="3ac34-167">Agregue el código siguiente a la línea por encima de `Main` para especificar los archivos descargados recientemente:</span><span class="sxs-lookup"><span data-stu-id="3ac34-167">Add the following code to the line right above `Main` to specify the recently downloaded files:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="3ac34-168">A continuación, cree las clases para los datos de entrada y las predicciones:</span><span class="sxs-lookup"><span data-stu-id="3ac34-168">Next, create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="3ac34-169">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-169">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="3ac34-170">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="3ac34-170">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="3ac34-171">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-171">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="3ac34-172">Agregue las siguientes instrucciones `using` al archivo nuevo:</span><span class="sxs-lookup"><span data-stu-id="3ac34-172">Add the following `using` statements to the new file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="3ac34-173">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `TaxiTrip` y `TaxiTripFarePrediction`, al archivo *TaxiTrip.cs*:</span><span class="sxs-lookup"><span data-stu-id="3ac34-173">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="3ac34-174">`TaxiTrip` es la clase de conjunto de datos de entrada y tiene definiciones para cada una de las columnas del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="3ac34-174">`TaxiTrip` is the input data set class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="3ac34-175">La clase `TaxiTripFarePrediction` se usa para la predicción una vez entrenado el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-175">The `TaxiTripFarePrediction` class is used for prediction after the model has been trained.</span></span> <span data-ttu-id="3ac34-176">Tiene un único float (`FareAmount`) y un atributo `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) aplicado.</span><span class="sxs-lookup"><span data-stu-id="3ac34-176">It has a single float (`FareAmount`) and a `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute applied.</span></span>

<span data-ttu-id="3ac34-177">Ahora, vuelva al archivo **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-177">Now go back to the **Program.cs** file.</span></span> <span data-ttu-id="3ac34-178">En `Main`, reemplace `Console.WriteLine("Hello World!")` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ac34-178">In `Main`, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

<span data-ttu-id="3ac34-179">El método `Train` entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-179">The `Train` method trains your model.</span></span> <span data-ttu-id="3ac34-180">Cree esa función justo debajo de `Main`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ac34-180">Create that function just below `Main`, using the following code:</span></span>

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="3ac34-181">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="3ac34-181">Create a learning pipeline</span></span>

<span data-ttu-id="3ac34-182">La canalización de aprendizaje carga todos los datos y algoritmos necesarios para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-182">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="3ac34-183">Agregue el código siguiente al método `Train()`:</span><span class="sxs-lookup"><span data-stu-id="3ac34-183">Add the following code into the `Train()` method:</span></span>

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-your-data"></a><span data-ttu-id="3ac34-184">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="3ac34-184">Load and transform your data</span></span>

<span data-ttu-id="3ac34-185">A continuación, cargue los datos en la canalización.</span><span class="sxs-lookup"><span data-stu-id="3ac34-185">Next, load your data into the pipeline.</span></span> <span data-ttu-id="3ac34-186">Apunte al `_datapath` creado inicialmente y especifique el delimitador del archivo .csv (,).</span><span class="sxs-lookup"><span data-stu-id="3ac34-186">Point to the `_datapath` created initially and specify the delimiter of the .csv file (,).</span></span> <span data-ttu-id="3ac34-187">Agregue el código siguiente al método `Train()` debajo del último paso:</span><span class="sxs-lookup"><span data-stu-id="3ac34-187">Add the following code into the `Train()` method underneath the last step:</span></span>

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(separator:','));
```

<span data-ttu-id="3ac34-188">Se hará referencia a las columnas sin el carácter de subrayado en el código que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="3ac34-188">You'll refer to the columns without the underscores in the code you're creating.</span></span> <span data-ttu-id="3ac34-189">Copie la columna `FareAmount` en una nueva columna denominada "Etiqueta" mediante la función `ColumnCopier()`.</span><span class="sxs-lookup"><span data-stu-id="3ac34-189">Copy the `FareAmount` column into a new column called "Label" using the `ColumnCopier()` function.</span></span> <span data-ttu-id="3ac34-190">Esta columna es la **Etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-190">This column is the **Label**.</span></span>

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

<span data-ttu-id="3ac34-191">Lleve a cabo cierta **ingeniería de características** para transformar los datos a fin de que se puedan utilizar eficazmente para el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="3ac34-191">Conduct some **feature engineering** to transform the data so that it can be used effectively for machine learning.</span></span> <span data-ttu-id="3ac34-192">El algoritmo que entrena el modelo requiere características **numéricas**, transforme los datos de categorías (`VendorId`, `RateCode` y `PaymentType`) en números.</span><span class="sxs-lookup"><span data-stu-id="3ac34-192">The algorithm that trains the model requires **numeric** features, you transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) into numbers.</span></span> <span data-ttu-id="3ac34-193">La función `CategoricalOneHotVectorizer()` asigna una clave numérica a los valores de cada una de estas columnas.</span><span class="sxs-lookup"><span data-stu-id="3ac34-193">The `CategoricalOneHotVectorizer()` function assigns a numeric key to the values in each of these columns.</span></span> <span data-ttu-id="3ac34-194">Transforme los datos mediante la adición de este código:</span><span class="sxs-lookup"><span data-stu-id="3ac34-194">Transform your data by adding this code:</span></span>

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

<span data-ttu-id="3ac34-195">El último paso de preparación de datos combina todas las **características** en un vector usando la función `ColumnConcatenator()`.</span><span class="sxs-lookup"><span data-stu-id="3ac34-195">The last step in data preparation combines all of your **features** into one vector using the `ColumnConcatenator()` function.</span></span> <span data-ttu-id="3ac34-196">Este paso necesario ayuda al algoritmo a procesar fácilmente sus características.</span><span class="sxs-lookup"><span data-stu-id="3ac34-196">This necessary step helps the algorithm easily process your features.</span></span> <span data-ttu-id="3ac34-197">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ac34-197">Add the following code:</span></span>

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

<span data-ttu-id="3ac34-198">Tenga en cuenta que la columna `trip_time_in_secs` no está incluida.</span><span class="sxs-lookup"><span data-stu-id="3ac34-198">Notice that the `trip_time_in_secs` column isn't included.</span></span> <span data-ttu-id="3ac34-199">Ya ha determinado que no es una característica útil de predicción.</span><span class="sxs-lookup"><span data-stu-id="3ac34-199">You already determined that it isn't a useful prediction feature.</span></span>

> [!NOTE]
> <span data-ttu-id="3ac34-200">Estos pasos deben agregarse a la canalización en el orden especificado anteriormente para su correcta ejecución.</span><span class="sxs-lookup"><span data-stu-id="3ac34-200">These steps must be added to Pipeline in the order specified above for successful execution.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="3ac34-201">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="3ac34-201">Choose a learning algorithm</span></span>

<span data-ttu-id="3ac34-202">Después de agregar los datos a la canalización y transformarlos en el formato de entrada correcto, seleccione un algoritmo de aprendizaje (**aprendiz**).</span><span class="sxs-lookup"><span data-stu-id="3ac34-202">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="3ac34-203">El algoritmo de aprendizaje entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-203">The learning algorithm trains the model.</span></span> <span data-ttu-id="3ac34-204">Eligió una **tarea de regresión** para este problema, por lo que agregó un aprendiz llamado `FastTreeRegressor()` a la canalización que utiliza la **potenciación de gradiente**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-204">You chose a **regression task** for this problem, so you add a learner called `FastTreeRegressor()` to the pipeline that utilizes **gradient boosting**.</span></span>

<span data-ttu-id="3ac34-205">La potenciación de gradiente es una técnica para los problemas de regresión de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="3ac34-205">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="3ac34-206">Crea cada árbol de regresión de forma escalonada.</span><span class="sxs-lookup"><span data-stu-id="3ac34-206">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="3ac34-207">Utiliza una función de pérdida predefinida para medir el error en cada paso y corregirlo en el siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ac34-207">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="3ac34-208">El resultado es un modelo de predicción que es realmente un conjunto de modelos de predicción más débiles.</span><span class="sxs-lookup"><span data-stu-id="3ac34-208">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="3ac34-209">Para obtener más información sobre la potenciación de gradiente, consulte [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regresión de árbol de decisión potenciado).</span><span class="sxs-lookup"><span data-stu-id="3ac34-209">For more information about gradient boosting, see [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="3ac34-210">Agregue el código siguiente al método `Train()` después del código de procesamiento de datos que agregó en el último paso:</span><span class="sxs-lookup"><span data-stu-id="3ac34-210">Add the following code into the `Train()` method following the data processing code added in the last step:</span></span>

```csharp
pipeline.Add(new FastTreeRegressor());
```

<span data-ttu-id="3ac34-211">Agregó todos los pasos anteriores a la canalización como instrucciones individuales, pero C# tiene una útil sintaxis de inicialización de recopilación que simplifica la creación e inicialización de la canalización.</span><span class="sxs-lookup"><span data-stu-id="3ac34-211">You added all the preceding steps to the pipeline as individual statements, but C# has a handy collection initialization syntax that makes it simpler to create and initialize the pipeline.</span></span> <span data-ttu-id="3ac34-212">Reemplace el código que ha agregado hasta ahora al método `Train()` por el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="3ac34-212">Replace the code you added so far to the `Train()` method with the following code:</span></span>

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a><span data-ttu-id="3ac34-213">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="3ac34-213">Train the model</span></span>

<span data-ttu-id="3ac34-214">El último paso es entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-214">The final step is to train the model.</span></span> <span data-ttu-id="3ac34-215">Hasta este punto, no se ha ejecutado nada en la canalización.</span><span class="sxs-lookup"><span data-stu-id="3ac34-215">Until this point, nothing in the pipeline has been executed.</span></span> <span data-ttu-id="3ac34-216">La función `pipeline.Train<T_Input, T_Output>()` toma el tipo de clase `TaxiTrip` predefinido y genera un tipo `TaxiTripFarePrediction`.</span><span class="sxs-lookup"><span data-stu-id="3ac34-216">The `pipeline.Train<T_Input, T_Output>()` function takes in the pre-defined `TaxiTrip` class type and outputs a `TaxiTripFarePrediction` type.</span></span> <span data-ttu-id="3ac34-217">Agregue este último fragmento de código a la función `Train()`:</span><span class="sxs-lookup"><span data-stu-id="3ac34-217">Add this final piece of code into the `Train()` function:</span></span>

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

<span data-ttu-id="3ac34-218">Y listo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-218">And that's it!</span></span> <span data-ttu-id="3ac34-219">Ha entrenado correctamente un modelo de aprendizaje automático que puede predecir tarifas de taxi en Nueva York.</span><span class="sxs-lookup"><span data-stu-id="3ac34-219">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="3ac34-220">Ahora eche un vistazo para valorar el grado de precisión de su modelo y aprender a utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-220">Now take a look to understand how accurate your model is and learn how to consume it.</span></span>

## <a name="save-the-model"></a><span data-ttu-id="3ac34-221">Guardado del modelo</span><span class="sxs-lookup"><span data-stu-id="3ac34-221">Save the model</span></span>

<span data-ttu-id="3ac34-222">Antes de ir al siguiente paso, guarde el modelo en un archivo .zip agregando el código siguiente al final de su función `Train()`:</span><span class="sxs-lookup"><span data-stu-id="3ac34-222">Before you go onto the next step, save your model to a .zip file by adding the following code at the end of your `Train()` function:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

<span data-ttu-id="3ac34-223">La adición de la instrucción `await` a la llamada `model.WriteAsync()` implica que el método `Train()` debe cambiarse a un método asincrónico que devuelva un `Task`.</span><span class="sxs-lookup"><span data-stu-id="3ac34-223">Adding the `await` statement to the `model.WriteAsync()` call means that the `Train()` method must be changed to an async method that returns a `Task`.</span></span> <span data-ttu-id="3ac34-224">Modifique la firma del `Train` tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ac34-224">Modify the signature of `Train` as shown in the following code:</span></span>

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

<span data-ttu-id="3ac34-225">El cambio del tipo de valor devuelto del método `Train` implica que tiene que agregar `await` al código que llama a `Train` en el método `Main` tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ac34-225">Changing the return type of the `Train` method means you have to add an `await` to the code that calls `Train` in the `Main` method as shown in the following code:</span></span>

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

<span data-ttu-id="3ac34-226">La adición de `await` en su método `Main` implica que el método `Main` debe tener un modificador `async` y devolver un `Task`:</span><span class="sxs-lookup"><span data-stu-id="3ac34-226">Adding an `await` in your `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

<span data-ttu-id="3ac34-227">También tiene que agregar la siguiente instrucción using en la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="3ac34-227">You also need to add the following using statement at the top of the file:</span></span>

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

<span data-ttu-id="3ac34-228">Debido a que el método `async Main` es una característica nueva en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior.</span><span class="sxs-lookup"><span data-stu-id="3ac34-228">Because the `async Main` method is a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="3ac34-229">Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-229">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="3ac34-230">Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-230">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="3ac34-231">En la lista desplegable, seleccione **C# 7.1** (o una versión superior).</span><span class="sxs-lookup"><span data-stu-id="3ac34-231">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="3ac34-232">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-232">Select the **OK** button.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="3ac34-233">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="3ac34-233">Evaluate the model</span></span>

<span data-ttu-id="3ac34-234">La evaluación es el proceso que sirve para comprobar cómo funciona el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-234">Evaluation is the process of checking how well the model works.</span></span> <span data-ttu-id="3ac34-235">Es importante que su modelo haga buenas predicciones sobre los datos que no utilizó cuando se entrenó.</span><span class="sxs-lookup"><span data-stu-id="3ac34-235">It's important that your model makes good predictions on data that it didn't use when it was trained.</span></span> <span data-ttu-id="3ac34-236">Una forma de hacerlo es dividiendo los datos en conjuntos de datos de entrenamiento y prueba, tal y como hizo en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3ac34-236">One way to do this is by splitting the data into train and test datasets, as you did in this tutorial.</span></span> <span data-ttu-id="3ac34-237">Ahora que ha entrenado el modelo en los datos de entrenamiento, puede ver qué tal funciona en los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="3ac34-237">Now that you've trained the model on the train data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="3ac34-238">Vuelva a su función `Main` y agregue el siguiente código debajo de la llamada al método `Train()`:</span><span class="sxs-lookup"><span data-stu-id="3ac34-238">Go back to your `Main` function and add the following code beneath the call to the `Train()`method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

<span data-ttu-id="3ac34-239">La función `Evaluate()` evalúa el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-239">The `Evaluate()` function evaluates your model.</span></span> <span data-ttu-id="3ac34-240">Cree esa función debajo de `Train()`.</span><span class="sxs-lookup"><span data-stu-id="3ac34-240">Create that function below `Train()`.</span></span> <span data-ttu-id="3ac34-241">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ac34-241">Add the following code:</span></span>

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

<span data-ttu-id="3ac34-242">Cargue los datos de prueba mediante la función `TextLoader()`.</span><span class="sxs-lookup"><span data-stu-id="3ac34-242">Load the test data using the `TextLoader()` function.</span></span> <span data-ttu-id="3ac34-243">Agregue el código siguiente al método `Evaluate()`:</span><span class="sxs-lookup"><span data-stu-id="3ac34-243">Add the following code into the `Evaluate()` method:</span></span>

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

<span data-ttu-id="3ac34-244">Agregue el código siguiente para evaluar el modelo y generar las métricas para él:</span><span class="sxs-lookup"><span data-stu-id="3ac34-244">Add the following code to evaluate the model and produce the metrics for it:</span></span>

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

<span data-ttu-id="3ac34-245">RMS es una métrica para evaluar los problemas de regresión.</span><span class="sxs-lookup"><span data-stu-id="3ac34-245">RMS is one metric for evaluating regression problems.</span></span> <span data-ttu-id="3ac34-246">Cuanto menor sea, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-246">The lower it is, the better your model.</span></span> <span data-ttu-id="3ac34-247">Agregue el código siguiente a la función `Evaluate()` para imprimir el RMS para el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-247">Add the following code into the `Evaluate()` function to print the RMS for your model.</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

<span data-ttu-id="3ac34-248">RSquared es otra métrica para evaluar los problemas de regresión.</span><span class="sxs-lookup"><span data-stu-id="3ac34-248">RSquared is another metric for evaluating regression problems.</span></span> <span data-ttu-id="3ac34-249">RSquared será un valor comprendido entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="3ac34-249">RSquared will be a value between 0 and 1.</span></span> <span data-ttu-id="3ac34-250">Cuanto más se acerque a 1, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-250">The closer you are to 1, the better your model.</span></span> <span data-ttu-id="3ac34-251">Agregue el código siguiente a la función `Evaluate()` para imprimir el valor de RSquared para el modelo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-251">Add the following code into the `Evaluate()` function to print the RSquared value for your model.</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="3ac34-252">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="3ac34-252">Use the model for predictions</span></span>

<span data-ttu-id="3ac34-253">A continuación, cree una clase para hospedar escenarios de prueba que puede usar para asegurarse de que el modelo funciona correctamente:</span><span class="sxs-lookup"><span data-stu-id="3ac34-253">Next, create a class to house test scenarios that you can use to make sure your model is working correctly:</span></span>

1. <span data-ttu-id="3ac34-254">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-254">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="3ac34-255">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TestTrips.cs*.</span><span class="sxs-lookup"><span data-stu-id="3ac34-255">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestTrips.cs*.</span></span> <span data-ttu-id="3ac34-256">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3ac34-256">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="3ac34-257">Modifique la clase para que sea estática, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ac34-257">Modify the class to be static like in the following example:</span></span>

[!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

<span data-ttu-id="3ac34-258">En este tutorial se utiliza un viaje de prueba en esta clase.</span><span class="sxs-lookup"><span data-stu-id="3ac34-258">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="3ac34-259">Más adelante, puede agregar otros escenarios para experimentar con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3ac34-259">Later you can add other scenarios to experiment with this sample.</span></span> <span data-ttu-id="3ac34-260">Agregue el código siguiente a la clase `TestTrips`:</span><span class="sxs-lookup"><span data-stu-id="3ac34-260">Add the following code into the `TestTrips` class:</span></span>

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

<span data-ttu-id="3ac34-261">La tarifa real de este viaje es 29,5, pero utilice 0 como marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="3ac34-261">This trip's actual fare is 29.5, but use 0 as a placeholder.</span></span> <span data-ttu-id="3ac34-262">El algoritmo de aprendizaje automático predecirá el importe del servicio.</span><span class="sxs-lookup"><span data-stu-id="3ac34-262">The machine learning algorithm will predict the fare.</span></span>

<span data-ttu-id="3ac34-263">Agregue el código siguiente a la función `Main`.</span><span class="sxs-lookup"><span data-stu-id="3ac34-263">Add the following code in your `Main` function.</span></span> <span data-ttu-id="3ac34-264">Prueba su modelo usando los datos `TestTrip`:</span><span class="sxs-lookup"><span data-stu-id="3ac34-264">It tests out your model using the `TestTrip` data:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

<span data-ttu-id="3ac34-265">Ejecute el programa para ver la tarifa de taxi predicha para su caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="3ac34-265">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="3ac34-266">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="3ac34-266">Congratulations!</span></span> <span data-ttu-id="3ac34-267">Ya ha creado correctamente un modelo de aprendizaje automático para predecir tarifas de taxi, ha evaluado su precisión y lo ha probado.</span><span class="sxs-lookup"><span data-stu-id="3ac34-267">You've now successfully built a machine learning model for predicting taxi fares, evaluated its accuracy, and tested it.</span></span> <span data-ttu-id="3ac34-268">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="3ac34-268">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ac34-269">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3ac34-269">Next steps</span></span>

<span data-ttu-id="3ac34-270">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="3ac34-270">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="3ac34-271">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="3ac34-271">Understand the problem</span></span>
> * <span data-ttu-id="3ac34-272">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="3ac34-272">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="3ac34-273">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="3ac34-273">Prepare and understand your data</span></span>
> * <span data-ttu-id="3ac34-274">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="3ac34-274">Create a learning pipeline</span></span>
> * <span data-ttu-id="3ac34-275">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="3ac34-275">Load and transform your data</span></span>
> * <span data-ttu-id="3ac34-276">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="3ac34-276">Choose a learning algorithm</span></span>
> * <span data-ttu-id="3ac34-277">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="3ac34-277">Train the model</span></span>
> * <span data-ttu-id="3ac34-278">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="3ac34-278">Evaluate the model</span></span>
> * <span data-ttu-id="3ac34-279">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="3ac34-279">Use the model for predictions</span></span>

<span data-ttu-id="3ac34-280">Visite nuestro repositorio de GitHub para obtener más información y encontrar más ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3ac34-280">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3ac34-281">Repositorio de GitHub de dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="3ac34-281">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)

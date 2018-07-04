---
title: Uso de ML.NET para predecir las tarifas de taxi de Nueva York (regresión)
description: Obtenga información acerca de cómo usar ML.NET en un escenario de regresión.
author: aditidugar
ms.author: johalex
ms.date: 06/18/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9706dad0a8e32651496e0404be4501c2c70e9d75
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948636"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a><span data-ttu-id="491c2-103">Tutorial: Uso de ML.NET para predecir las tarifas de taxi de Nueva York (regresión)</span><span class="sxs-lookup"><span data-stu-id="491c2-103">Tutorial: Use ML.NET to predict New York taxi fares (regression)</span></span>

> [!NOTE]
> <span data-ttu-id="491c2-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="491c2-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="491c2-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="491c2-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="491c2-106">En este tutorial se muestra cómo utilizar ML.NET para generar un [modelo de regresión](../resources/glossary.md#regression) para predecir las tarifas de taxi de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="491c2-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting New York City taxi fares.</span></span>

<span data-ttu-id="491c2-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="491c2-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="491c2-108">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="491c2-108">Understand the problem</span></span>
> * <span data-ttu-id="491c2-109">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="491c2-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="491c2-110">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="491c2-110">Prepare and understand the data</span></span>
> * <span data-ttu-id="491c2-111">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="491c2-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="491c2-112">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="491c2-112">Load and transform the data</span></span>
> * <span data-ttu-id="491c2-113">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="491c2-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="491c2-114">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="491c2-114">Train the model</span></span>
> * <span data-ttu-id="491c2-115">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="491c2-115">Evaluate the model</span></span>
> * <span data-ttu-id="491c2-116">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="491c2-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="491c2-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="491c2-117">Prerequisites</span></span>

* <span data-ttu-id="491c2-118">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="491c2-118">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="491c2-119">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="491c2-119">Understand the problem</span></span>

<span data-ttu-id="491c2-120">Este problema se centra en **predecir la tarifa de un viaje en taxi en Nueva York**.</span><span class="sxs-lookup"><span data-stu-id="491c2-120">This problem is centered around **predicting the fare of a taxi trip in New York City**.</span></span> <span data-ttu-id="491c2-121">A primera vista, puede parecer que simplemente depende de la distancia recorrida.</span><span class="sxs-lookup"><span data-stu-id="491c2-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="491c2-122">Sin embargo, los taxistas de Nueva York cobran distintas cantidades por otros factores, como llevar pasajeros adicionales o pagar con tarjeta de crédito en lugar de efectivo.</span><span class="sxs-lookup"><span data-stu-id="491c2-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="491c2-123">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="491c2-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="491c2-124">Para predecir la tarifa del taxi, primero seleccione la tarea de aprendizaje automático adecuada.</span><span class="sxs-lookup"><span data-stu-id="491c2-124">To predict the taxi fare, you first select the appropriate machine learning task.</span></span> <span data-ttu-id="491c2-125">Está buscando predecir un valor real (un doble que representa el precio) en función de los otros factores del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="491c2-125">You are looking to predict a real value (a double that represents price) based on the other factors in the dataset.</span></span> <span data-ttu-id="491c2-126">Elige una tarea de [**regresión**](../resources/glossary.md#regression).</span><span class="sxs-lookup"><span data-stu-id="491c2-126">You choose a [**regression**](../resources/glossary.md#regression) task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="491c2-127">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="491c2-127">Create a console application</span></span>

1. <span data-ttu-id="491c2-128">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="491c2-128">Open Visual Studio 2017.</span></span> <span data-ttu-id="491c2-129">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="491c2-129">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="491c2-130">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="491c2-130">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="491c2-131">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="491c2-131">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="491c2-132">En el cuadro de texto **Nombre**, escriba "TaxiFarePrediction" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="491c2-132">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

2. <span data-ttu-id="491c2-133">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:</span><span class="sxs-lookup"><span data-stu-id="491c2-133">Create a directory named *Data* in your project to save the data set files:</span></span>

    <span data-ttu-id="491c2-134">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="491c2-134">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="491c2-135">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="491c2-135">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="491c2-136">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="491c2-136">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="491c2-137">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="491c2-137">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="491c2-138">Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="491c2-138">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="491c2-139">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="491c2-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="491c2-140">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="491c2-140">Prepare and understand the data</span></span>

1. <span data-ttu-id="491c2-141">Descargue los conjuntos de datos [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) y [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) y guárdelos en la carpeta *Datos* que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="491c2-141">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="491c2-142">Usaremos estos conjuntos de datos para entrenar el modelo de aprendizaje automático y, después, evaluar su precisión.</span><span class="sxs-lookup"><span data-stu-id="491c2-142">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="491c2-143">Estos conjuntos de datos proceden originalmente del [conjunto de datos NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="491c2-143">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

2. <span data-ttu-id="491c2-144">En el **Explorador de soluciones**, haga clic con el botón derecho en cada uno de los archivos \*.csv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="491c2-144">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="491c2-145">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** a **Siempre**.</span><span class="sxs-lookup"><span data-stu-id="491c2-145">Under **Advanced**, change the value of **Copy to Output Directory** to **Always**.</span></span>

3. <span data-ttu-id="491c2-146">Abra el conjunto de datos **taxi-fare-train.csv** y consulte los encabezados de columna de la primera fila.</span><span class="sxs-lookup"><span data-stu-id="491c2-146">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="491c2-147">Eche un vistazo a cada una de las columnas.</span><span class="sxs-lookup"><span data-stu-id="491c2-147">Take a look at each of the columns.</span></span> <span data-ttu-id="491c2-148">Estudie los datos y decida qué columnas son **características** y cuál es la **etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="491c2-148">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="491c2-149">La **etiqueta** es el identificador de la columna que quiere predecir.</span><span class="sxs-lookup"><span data-stu-id="491c2-149">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="491c2-150">Las **características** identificadas se usan para predecir la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="491c2-150">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="491c2-151">El conjunto de datos proporcionado contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="491c2-151">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="491c2-152">**vendor_id:** el identificador del taxista es una característica.</span><span class="sxs-lookup"><span data-stu-id="491c2-152">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="491c2-153">**rate_code:** el tipo de tarifa del viaje en taxi es una característica.</span><span class="sxs-lookup"><span data-stu-id="491c2-153">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="491c2-154">**passenger_count:** el número de pasajeros en el recorrido es una característica.</span><span class="sxs-lookup"><span data-stu-id="491c2-154">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="491c2-155">**trip_time_in_secs:** la cantidad de tiempo que tardó el viaje.</span><span class="sxs-lookup"><span data-stu-id="491c2-155">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="491c2-156">Por ejemplo, si quiere calcular la tarifa del viaje antes de que termine</span><span class="sxs-lookup"><span data-stu-id="491c2-156">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="491c2-157">y aún no conoce la duración del viaje,</span><span class="sxs-lookup"><span data-stu-id="491c2-157">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="491c2-158">el tiempo del viaje no es una característica, por lo que deberá excluir esta columna del modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-158">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="491c2-159">**trip_distance:** la distancia del viaje es una característica.</span><span class="sxs-lookup"><span data-stu-id="491c2-159">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="491c2-160">**payment_type:** el método de pago (efectivo o tarjeta de crédito) es una característica.</span><span class="sxs-lookup"><span data-stu-id="491c2-160">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="491c2-161">**fare_amount:** la tarifa de taxi total pagada es la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="491c2-161">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="491c2-162">Crear clases de datos</span><span class="sxs-lookup"><span data-stu-id="491c2-162">Create data classes</span></span>

<span data-ttu-id="491c2-163">Cree clases para los datos de entrada y las predicciones:</span><span class="sxs-lookup"><span data-stu-id="491c2-163">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="491c2-164">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="491c2-164">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="491c2-165">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="491c2-165">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="491c2-166">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="491c2-166">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="491c2-167">Agregue las siguientes directivas `using` al nuevo archivo:</span><span class="sxs-lookup"><span data-stu-id="491c2-167">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="491c2-168">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `TaxiTrip` y `TaxiTripFarePrediction`, al archivo *TaxiTrip.cs*:</span><span class="sxs-lookup"><span data-stu-id="491c2-168">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="491c2-169">`TaxiTrip` es la clase de datos de entrada y tiene definiciones para cada una de las columnas del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="491c2-169">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="491c2-170">Use el atributo [Columna](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) para especificar los índices de las columnas de origen en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="491c2-170">Use the [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="491c2-171">La clase `TaxiTripFarePrediction` se usa para representar los resultados previstos.</span><span class="sxs-lookup"><span data-stu-id="491c2-171">The `TaxiTripFarePrediction` class is used to represent predicted results.</span></span> <span data-ttu-id="491c2-172">Tiene un único campo flotante (`FareAmount`) con un atributo `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) aplicado.</span><span class="sxs-lookup"><span data-stu-id="491c2-172">It has a single float (`FareAmount`) field with a `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute applied.</span></span> <span data-ttu-id="491c2-173">La columna **Puntuación** es la columna especial de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="491c2-173">The **Score** column is the special column in ML.NET.</span></span> <span data-ttu-id="491c2-174">El modelo generará valores de predicción en esa columna.</span><span class="sxs-lookup"><span data-stu-id="491c2-174">The model outputs predicted values into that column.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="491c2-175">Definir rutas de acceso de datos y modelos</span><span class="sxs-lookup"><span data-stu-id="491c2-175">Define data and model paths</span></span>

<span data-ttu-id="491c2-176">Vuelva al archivo *Program.cs* y agregue tres campos para contener las rutas de acceso a los archivos con conjuntos de datos y el archivo en el que guardar el modelo:</span><span class="sxs-lookup"><span data-stu-id="491c2-176">Go back to the *Program.cs* file and add three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="491c2-177">`_datapath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-177">`_datapath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="491c2-178">`_testdatapath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-178">`_testdatapath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="491c2-179">`_modelpath` contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="491c2-179">`_modelpath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="491c2-180">Agregue el código siguiente justo encima del método `Main` para especificar las rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="491c2-180">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="491c2-181">Para que el código anterior se compile, agregue las directivas `using` siguientes a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="491c2-181">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsingsForPaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Using statements for path definitions")]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="491c2-182">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="491c2-182">Create a learning pipeline</span></span>

<span data-ttu-id="491c2-183">Agregue las directivas `using` adicionales siguientes a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="491c2-183">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="491c2-184">En `Main`, reemplace `Console.WriteLine("Hello World!")` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="491c2-184">In `Main`, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

<span data-ttu-id="491c2-185">El método `Train` entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-185">The `Train` method trains the model.</span></span> <span data-ttu-id="491c2-186">Cree ese método justo debajo de `Main` utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="491c2-186">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

<span data-ttu-id="491c2-187">La canalización de aprendizaje carga todos los datos y algoritmos necesarios para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-187">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="491c2-188">Agregue el código siguiente al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="491c2-188">Add the following code into the `Train` method:</span></span>

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-data"></a><span data-ttu-id="491c2-189">Cargar y transformar datos</span><span class="sxs-lookup"><span data-stu-id="491c2-189">Load and transform data</span></span>

<span data-ttu-id="491c2-190">El primer paso que realiza la canalización de aprendizaje es cargar datos desde el conjunto de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="491c2-190">The first step that the learning pipeline performs is loading data from the training data set.</span></span> <span data-ttu-id="491c2-191">En nuestro caso, el conjunto de datos de entrenamiento se almacena en el archivo de texto con una ruta de acceso definida por el campo `_datapath`.</span><span class="sxs-lookup"><span data-stu-id="491c2-191">In our case, training data set is stored in the text file with a path defined by the `_datapath` field.</span></span> <span data-ttu-id="491c2-192">Ese archivo contiene el encabezado con los nombres de columna, por lo que se debe omitir la primera fila al cargar los datos.</span><span class="sxs-lookup"><span data-stu-id="491c2-192">That file contains the header with the column names, so the first row should be ignored while loading data.</span></span> <span data-ttu-id="491c2-193">En el archivo, las columnas se separan mediante una coma (",").</span><span class="sxs-lookup"><span data-stu-id="491c2-193">Columns in the file are separated by the comma (",").</span></span> <span data-ttu-id="491c2-194">Agregue el código siguiente al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="491c2-194">Add the following code into the `Train` method:</span></span>

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(useHeader: true, separator: ','));
```

<span data-ttu-id="491c2-195">En los pasos siguientes se hace referencia a las columnas con los nombres definidos en la clase `TaxiTrip`.</span><span class="sxs-lookup"><span data-stu-id="491c2-195">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="491c2-196">Cuando el modelo se entrena y evalúa, los valores de la columna **Etiqueta** se consideran valores correctos para predecir.</span><span class="sxs-lookup"><span data-stu-id="491c2-196">When the model is trained and evaluated, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="491c2-197">Para predecir la tarifa del viaje en taxi, debe copiar la columna `FareAmount` en la columna **Etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="491c2-197">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="491c2-198">Para ello, use <xref:Microsoft.ML.Transforms.ColumnCopier> y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="491c2-198">To do that, use <xref:Microsoft.ML.Transforms.ColumnCopier> and add the following code:</span></span>

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

<span data-ttu-id="491c2-199">El algoritmo que entrena el modelo requiere características **numéricas**, por lo que debe transformar los datos de categorías (`VendorId`, `RateCode` y `PaymentType`) en números.</span><span class="sxs-lookup"><span data-stu-id="491c2-199">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers.</span></span> <span data-ttu-id="491c2-200">Para ello, use <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer>, que asigna valores clave numéricos diferentes a los distintos valores de cada una de las columnas, y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="491c2-200">To do that, use <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer>, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

<span data-ttu-id="491c2-201">En el último paso para la preparación de los datos, se combinan todas las columnas de característica en la columna **Características** mediante la clase de transformación <xref:Microsoft.ML.Transforms.ColumnConcatenator>.</span><span class="sxs-lookup"><span data-stu-id="491c2-201">The last step in data preparation combines all of the feature columns into the **Features** column using the <xref:Microsoft.ML.Transforms.ColumnConcatenator> transformation class.</span></span> <span data-ttu-id="491c2-202">Este paso es necesario, ya que un aprendiz solo procesará las características de la columna **Características**.</span><span class="sxs-lookup"><span data-stu-id="491c2-202">This step is necessary as a learner processes only features from the **Features** column.</span></span> <span data-ttu-id="491c2-203">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="491c2-203">Add the following code:</span></span>

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

<span data-ttu-id="491c2-204">Tenga en cuenta que la columna `TripTime`, que corresponde a la columna `trip_time_in_secs` en el archivo con el conjunto de datos, no se incluye.</span><span class="sxs-lookup"><span data-stu-id="491c2-204">Notice that the `TripTime` column, which corresponds to the `trip_time_in_secs` column in the data set file, isn't included.</span></span> <span data-ttu-id="491c2-205">Ya ha determinado que no es una característica útil de predicción.</span><span class="sxs-lookup"><span data-stu-id="491c2-205">You already determined that it isn't a useful prediction feature.</span></span>

> [!NOTE]
> <span data-ttu-id="491c2-206">Estos pasos deben agregarse a la canalización en el orden especificado anteriormente para su correcta ejecución.</span><span class="sxs-lookup"><span data-stu-id="491c2-206">These steps must be added to the pipeline in the order specified above for successful execution.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="491c2-207">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="491c2-207">Choose a learning algorithm</span></span>

<span data-ttu-id="491c2-208">Después de agregar los datos a la canalización y transformarlos en el formato de entrada correcto, seleccione un algoritmo de aprendizaje (**aprendiz**).</span><span class="sxs-lookup"><span data-stu-id="491c2-208">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="491c2-209">El aprendiz entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-209">The learner trains the model.</span></span> <span data-ttu-id="491c2-210">Como ha elegido una **tarea de regresión** para este problema, deberá agregar un aprendiz de <xref:Microsoft.ML.Trainers.FastTreeRegressor>, uno de los aprendices de regresión que proporciona ML.NET.</span><span class="sxs-lookup"><span data-stu-id="491c2-210">You chose a **regression task** for this problem, so you add a <xref:Microsoft.ML.Trainers.FastTreeRegressor> learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="491c2-211">El aprendiz <xref:Microsoft.ML.Trainers.FastTreeRegressor> usa la potenciación de gradiente.</span><span class="sxs-lookup"><span data-stu-id="491c2-211"><xref:Microsoft.ML.Trainers.FastTreeRegressor> learner utilizes gradient boosting.</span></span> <span data-ttu-id="491c2-212">La potenciación de gradiente es una técnica para los problemas de regresión de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="491c2-212">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="491c2-213">Crea cada árbol de regresión de forma escalonada.</span><span class="sxs-lookup"><span data-stu-id="491c2-213">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="491c2-214">Utiliza una función de pérdida predefinida para medir el error en cada paso y corregirlo en el siguiente.</span><span class="sxs-lookup"><span data-stu-id="491c2-214">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="491c2-215">El resultado es un modelo de predicción que es realmente un conjunto de modelos de predicción más débiles.</span><span class="sxs-lookup"><span data-stu-id="491c2-215">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="491c2-216">Para obtener más información sobre la potenciación de gradiente, consulte [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regresión de árbol de decisión potenciado).</span><span class="sxs-lookup"><span data-stu-id="491c2-216">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="491c2-217">Agregue el código siguiente al método `Train` después del código de procesamiento de datos que ha agregado en el paso anterior:</span><span class="sxs-lookup"><span data-stu-id="491c2-217">Add the following code into the `Train` method following the data processing code added in the previous step:</span></span>

```csharp
pipeline.Add(new FastTreeRegressor());
```

<span data-ttu-id="491c2-218">Agregó todos los pasos anteriores a la canalización como instrucciones individuales, pero C# tiene una útil sintaxis de inicialización de recopilación que simplifica la creación e inicialización de la canalización.</span><span class="sxs-lookup"><span data-stu-id="491c2-218">You added all the preceding steps to the pipeline as individual statements, but C# has a handy collection initialization syntax that makes it simpler to create and initialize the pipeline.</span></span> <span data-ttu-id="491c2-219">Reemplace el código que ha agregado hasta ahora al método `Train` por el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="491c2-219">Replace the code you added so far to the `Train` method with the following code:</span></span>

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a><span data-ttu-id="491c2-220">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="491c2-220">Train the model</span></span>

<span data-ttu-id="491c2-221">El último paso es entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-221">The final step is to train the model.</span></span> <span data-ttu-id="491c2-222">Hasta este punto, no se ha ejecutado nada en la canalización.</span><span class="sxs-lookup"><span data-stu-id="491c2-222">Until this point, nothing in the pipeline has been executed.</span></span> <span data-ttu-id="491c2-223">El método `pipeline.Train<TInput, TOutput>` genera el modelo que usa una instancia del tipo `TInput` para generar una instancia del tipo `TOutput`.</span><span class="sxs-lookup"><span data-stu-id="491c2-223">The `pipeline.Train<TInput, TOutput>` method produces the model that takes in an instance of the `TInput` type and outputs an instance of the `TOutput` type.</span></span> <span data-ttu-id="491c2-224">Agregue el código siguiente al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="491c2-224">Add the following code into the `Train` method:</span></span>

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

<span data-ttu-id="491c2-225">Y listo.</span><span class="sxs-lookup"><span data-stu-id="491c2-225">And that's it!</span></span> <span data-ttu-id="491c2-226">Ha entrenado correctamente un modelo de aprendizaje automático que puede predecir tarifas de taxi en Nueva York.</span><span class="sxs-lookup"><span data-stu-id="491c2-226">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="491c2-227">Ahora, eche un vistazo para medir la precisión del modelo y aprender a usarlo para predecir los valores de tarifas de viajes en taxi.</span><span class="sxs-lookup"><span data-stu-id="491c2-227">Now let's take a look to understand how accurate the model is and learn how to use it to predict taxi fare values.</span></span>

### <a name="save-the-model"></a><span data-ttu-id="491c2-228">Guardado del modelo</span><span class="sxs-lookup"><span data-stu-id="491c2-228">Save the model</span></span>

<span data-ttu-id="491c2-229">Antes de ir al paso siguiente, guarde el modelo en un archivo .zip agregando el código siguiente al final del método `Train`:</span><span class="sxs-lookup"><span data-stu-id="491c2-229">Before you go onto the next step, save the model to a .zip file by adding the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

<span data-ttu-id="491c2-230">La adición de la instrucción `await` a la llamada `model.WriteAsync` implica que el método `Train` debe cambiarse a un método asincrónico que devuelva una tarea.</span><span class="sxs-lookup"><span data-stu-id="491c2-230">Adding the `await` statement to the `model.WriteAsync` call means that the `Train` method must be changed to an async method that returns a task.</span></span> <span data-ttu-id="491c2-231">Modifique la firma del `Train` tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="491c2-231">Modify the signature of `Train` as shown in the following code:</span></span>

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

<span data-ttu-id="491c2-232">El cambio del tipo de valor devuelto del método `Train` implica que tiene que agregar `await` al código que llama a `Train` en el método `Main` tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="491c2-232">Changing the return type of the `Train` method means you have to add an `await` to the code that calls `Train` in the `Main` method as shown in the following code:</span></span>

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

<span data-ttu-id="491c2-233">El uso de `await` en el método `Main` implica que el método `Main` debe tener un modificador `async` y devolver un `Task`:</span><span class="sxs-lookup"><span data-stu-id="491c2-233">Using `await` in the `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

<span data-ttu-id="491c2-234">También tiene que agregar la siguiente directiva `using` a la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="491c2-234">You also need to add the following `using` directive at the top of the file:</span></span>

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

<span data-ttu-id="491c2-235">Debido a que el método `async Main` es una característica agregada en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior.</span><span class="sxs-lookup"><span data-stu-id="491c2-235">Because the `async Main` method is the feature added in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span> <span data-ttu-id="491c2-236">Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="491c2-236">To do that, right-click the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="491c2-237">Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="491c2-237">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="491c2-238">En la lista desplegable, seleccione **C# 7.1** (o una versión superior).</span><span class="sxs-lookup"><span data-stu-id="491c2-238">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="491c2-239">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="491c2-239">Select the **OK** button.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="491c2-240">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="491c2-240">Evaluate the model</span></span>

<span data-ttu-id="491c2-241">La evaluación es el proceso que sirve para comprobar cómo predice valores de etiqueta el modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-241">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="491c2-242">Es importante que el modelo haga buenas predicciones sobre los datos que no se han usado para entrenarlo.</span><span class="sxs-lookup"><span data-stu-id="491c2-242">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="491c2-243">Una forma de hacerlo es dividiendo los datos en conjuntos de datos de entrenamiento y prueba, tal como ha hecho en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="491c2-243">One way to do this is to split the data into train and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="491c2-244">Ahora que ha entrenado el modelo en los datos de entrenamiento, puede ver qué tal funciona en los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="491c2-244">Now that you've trained the model on the train data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="491c2-245">Vuelva al método `Main` y agregue el código siguiente debajo de la llamada al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="491c2-245">Go back to the `Main` method and add the following code beneath the call to the `Train`method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

<span data-ttu-id="491c2-246">El método `Evaluate` evaluará el modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-246">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="491c2-247">Para crear este método, agregue el código siguiente debajo del método `Train`:</span><span class="sxs-lookup"><span data-stu-id="491c2-247">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

<span data-ttu-id="491c2-248">Agregue el código siguiente al método `Evaluate` para configurar la carga de los datos de prueba:</span><span class="sxs-lookup"><span data-stu-id="491c2-248">Add the following code into the `Evaluate` method to setup loading of the test data:</span></span>

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

<span data-ttu-id="491c2-249">Agregue el código siguiente para evaluar el modelo y generar las métricas de evaluación:</span><span class="sxs-lookup"><span data-stu-id="491c2-249">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

<span data-ttu-id="491c2-250">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) es una de las métricas de evaluación del modelo de regresión.</span><span class="sxs-lookup"><span data-stu-id="491c2-250">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="491c2-251">Cuanto menor sea su valor, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-251">The lower it is, the better the model is.</span></span> <span data-ttu-id="491c2-252">Agregue el código siguiente al método `Evaluate` para mostrar el valor de RMS:</span><span class="sxs-lookup"><span data-stu-id="491c2-252">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

<span data-ttu-id="491c2-253">[RSquared](../resources/glossary.md#coefficient-of-determination) es otra métrica de evaluación de modelos de regresión.</span><span class="sxs-lookup"><span data-stu-id="491c2-253">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="491c2-254">RSquared muestra valores comprendidos entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="491c2-254">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="491c2-255">Cuanto más se acerque el valor a 1, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-255">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="491c2-256">Agregue el código siguiente al método `Evaluate` para mostrar el valor de RSquared:</span><span class="sxs-lookup"><span data-stu-id="491c2-256">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="491c2-257">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="491c2-257">Use the model for predictions</span></span>

<span data-ttu-id="491c2-258">A continuación, cree una clase para hospedar escenarios de prueba que pueda usar para asegurarse de que el modelo funcione correctamente:</span><span class="sxs-lookup"><span data-stu-id="491c2-258">Next, create a class to house test scenarios that you can use to make sure the model is working correctly:</span></span>

1. <span data-ttu-id="491c2-259">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="491c2-259">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="491c2-260">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TestTrips.cs*.</span><span class="sxs-lookup"><span data-stu-id="491c2-260">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestTrips.cs*.</span></span> <span data-ttu-id="491c2-261">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="491c2-261">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="491c2-262">Modifique la clase para que sea estática, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="491c2-262">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

<span data-ttu-id="491c2-263">En este tutorial se utiliza un viaje de prueba en esta clase.</span><span class="sxs-lookup"><span data-stu-id="491c2-263">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="491c2-264">Más adelante, puede agregar otros escenarios para experimentar con el modelo.</span><span class="sxs-lookup"><span data-stu-id="491c2-264">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="491c2-265">Agregue el código siguiente a la clase `TestTrips`:</span><span class="sxs-lookup"><span data-stu-id="491c2-265">Add the following code into the `TestTrips` class:</span></span>

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

<span data-ttu-id="491c2-266">La tarifa real del viaje es de 29,5.</span><span class="sxs-lookup"><span data-stu-id="491c2-266">This trip's actual fare is 29.5.</span></span> <span data-ttu-id="491c2-267">Puesto que el modelo predecirá la tarifa, use 0 como marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="491c2-267">Use 0 as a placeholder, as the model will predict the fare.</span></span>

<span data-ttu-id="491c2-268">Para predecir la tarifa del viaje especificado, vuelva al archivo *Program.cs* y agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="491c2-268">To predict the fare of the specified trip, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

<span data-ttu-id="491c2-269">Ejecute el programa para ver la tarifa de taxi predicha para su caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="491c2-269">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="491c2-270">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="491c2-270">Congratulations!</span></span> <span data-ttu-id="491c2-271">Ya ha creado correctamente un modelo de aprendizaje automático para predecir tarifas de viajes en taxi, ha evaluado su precisión y lo ha usado para hacer predicciones.</span><span class="sxs-lookup"><span data-stu-id="491c2-271">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="491c2-272">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).</span><span class="sxs-lookup"><span data-stu-id="491c2-272">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="491c2-273">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="491c2-273">Next steps</span></span>

<span data-ttu-id="491c2-274">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="491c2-274">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="491c2-275">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="491c2-275">Understand the problem</span></span>
> * <span data-ttu-id="491c2-276">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="491c2-276">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="491c2-277">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="491c2-277">Prepare and understand the data</span></span>
> * <span data-ttu-id="491c2-278">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="491c2-278">Create a learning pipeline</span></span>
> * <span data-ttu-id="491c2-279">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="491c2-279">Load and transform the data</span></span>
> * <span data-ttu-id="491c2-280">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="491c2-280">Choose a learning algorithm</span></span>
> * <span data-ttu-id="491c2-281">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="491c2-281">Train the model</span></span>
> * <span data-ttu-id="491c2-282">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="491c2-282">Evaluate the model</span></span>
> * <span data-ttu-id="491c2-283">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="491c2-283">Use the model for predictions</span></span>

<span data-ttu-id="491c2-284">Visite nuestro repositorio de GitHub para obtener más información y encontrar más ejemplos.</span><span class="sxs-lookup"><span data-stu-id="491c2-284">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="491c2-285">Repositorio de GitHub de dotnet/machinelearning</span><span class="sxs-lookup"><span data-stu-id="491c2-285">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)

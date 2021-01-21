---
title: 'Tutorial: Detección de anomalías en las llamadas telefónicas'
description: Aprenda a crear una aplicación de detección de anomalías para los datos de series temporales. En este tutorial se va a crear una aplicación de consola de .NET Core mediante C# en Visual Studio 2019.
ms.date: 12/04/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: f001cb912bb695a7edb0917f3306ca9bfbe311ac
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98187787"
---
# <a name="tutorial-detect-anomalies-in-time-series-with-mlnet"></a><span data-ttu-id="2d151-104">Tutorial: Detección de anomalías en series temporales con ML.NET</span><span class="sxs-lookup"><span data-stu-id="2d151-104">Tutorial: Detect anomalies in time series with ML.NET</span></span>

<span data-ttu-id="2d151-105">Aprenda a crear una aplicación de detección de anomalías para los datos de series temporales.</span><span class="sxs-lookup"><span data-stu-id="2d151-105">Learn how to build an anomaly detection application for time series data.</span></span> <span data-ttu-id="2d151-106">En este tutorial se va a crear una aplicación de consola de .NET Core mediante C# en Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="2d151-106">This tutorial creates a .NET Core console application using C# in Visual Studio 2019.</span></span>

<span data-ttu-id="2d151-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="2d151-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="2d151-108">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="2d151-108">Load the data</span></span>
> * <span data-ttu-id="2d151-109">Detectar el período para una serie temporal</span><span class="sxs-lookup"><span data-stu-id="2d151-109">Detect period for a time series</span></span>
> * <span data-ttu-id="2d151-110">Detectar anomalías para una serie temporal periódica</span><span class="sxs-lookup"><span data-stu-id="2d151-110">Detect anomaly for a periodical time series</span></span>

<span data-ttu-id="2d151-111">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="2d151-111">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d151-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2d151-112">Prerequisites</span></span>

* <span data-ttu-id="2d151-113">[Visual Studio 2019, versión 16.7.8 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="2d151-113">[Visual Studio 2019 version 16.7.8 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="2d151-114">[Conjunto de datos phone-calls.csv](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrEntireDetection/Data/phone-calls.csv).</span><span class="sxs-lookup"><span data-stu-id="2d151-114">[The phone-calls.csv dataset](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrEntireDetection/Data/phone-calls.csv).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="2d151-115">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="2d151-115">Create a console application</span></span>

1. <span data-ttu-id="2d151-116">Cree una **aplicación de consola de .NET Core en C#** denominada "ProductSalesAnomalyDetection".</span><span class="sxs-lookup"><span data-stu-id="2d151-116">Create a **C# .NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="2d151-117">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="2d151-117">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="2d151-118">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="2d151-118">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="2d151-119">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="2d151-119">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="2d151-120">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML** y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="2d151-120">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML** and select the **Install** button.</span></span> <span data-ttu-id="2d151-121">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="2d151-121">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="2d151-122">Repita estos pasos para **Microsoft.ML.TimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="2d151-122">Repeat these steps for **Microsoft.ML.TimeSeries**.</span></span>

4. <span data-ttu-id="2d151-123">Agregue las instrucciones `using` siguientes en la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="2d151-123">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="2d151-124">Descarga de los datos</span><span class="sxs-lookup"><span data-stu-id="2d151-124">Download your data</span></span>

1. <span data-ttu-id="2d151-125">Descargue el conjunto de datos y guárdelo en la carpeta *Datos* que creó anteriormente:</span><span class="sxs-lookup"><span data-stu-id="2d151-125">Download the dataset and save it to the *Data* folder you previously created:</span></span>

    <span data-ttu-id="2d151-126">Haga clic con el botón derecho en [*phone-calls.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrEntireDetection/Data/phone-calls.csv) y seleccione "Guardar vínculo (o destino) como...".</span><span class="sxs-lookup"><span data-stu-id="2d151-126">Right click on [*phone-calls.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrEntireDetection/Data/phone-calls.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="2d151-127">Asegúrese de que guarda el archivo \*.csv en la carpeta *Datos* o, después de guardarlo en otro lugar, mueva el archivo \*.csv a la carpeta *Datos*.</span><span class="sxs-lookup"><span data-stu-id="2d151-127">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="2d151-128">En el Explorador de soluciones, haga clic con el botón derecho en el archivo \*.csv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2d151-128">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="2d151-129">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="2d151-129">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="2d151-130">La siguiente tabla es una vista previa de datos del archivo \*.csv:</span><span class="sxs-lookup"><span data-stu-id="2d151-130">The following table is a data preview from your \*.csv file:</span></span>

| <span data-ttu-id="2d151-131">timestamp</span><span class="sxs-lookup"><span data-stu-id="2d151-131">timestamp</span></span>  | <span data-ttu-id="2d151-132">value</span><span class="sxs-lookup"><span data-stu-id="2d151-132">value</span></span> |
|--------|--------------|
| <span data-ttu-id="2d151-133">2018/9/3</span><span class="sxs-lookup"><span data-stu-id="2d151-133">2018/9/3</span></span>  | <span data-ttu-id="2d151-134">36.69670857</span><span class="sxs-lookup"><span data-stu-id="2d151-134">36.69670857</span></span>  |
| <span data-ttu-id="2d151-135">2018/9/4</span><span class="sxs-lookup"><span data-stu-id="2d151-135">2018/9/4</span></span>  | <span data-ttu-id="2d151-136">35.74160571</span><span class="sxs-lookup"><span data-stu-id="2d151-136">35.74160571</span></span>  |
| <span data-ttu-id="2d151-137">.....</span><span class="sxs-lookup"><span data-stu-id="2d151-137">.....</span></span>  | <span data-ttu-id="2d151-138">.....</span><span class="sxs-lookup"><span data-stu-id="2d151-138">.....</span></span>  |
| <span data-ttu-id="2d151-139">2018/10/3</span><span class="sxs-lookup"><span data-stu-id="2d151-139">2018/10/3</span></span>  | <span data-ttu-id="2d151-140">34.49893429</span><span class="sxs-lookup"><span data-stu-id="2d151-140">34.49893429</span></span>  |
| <span data-ttu-id="2d151-141">...</span><span class="sxs-lookup"><span data-stu-id="2d151-141">...</span></span>    | <span data-ttu-id="2d151-142">....</span><span class="sxs-lookup"><span data-stu-id="2d151-142">....</span></span>   |

<span data-ttu-id="2d151-143">Este archivo representa una serie temporal.</span><span class="sxs-lookup"><span data-stu-id="2d151-143">This file represents a time-series.</span></span> <span data-ttu-id="2d151-144">Cada fila del archivo es un punto de datos.</span><span class="sxs-lookup"><span data-stu-id="2d151-144">Each row in the file is a data point.</span></span> <span data-ttu-id="2d151-145">Cada punto de datos tiene dos atributos, es decir, `timestamp` y `value`, para representar el número de llamadas telefónicas de cada día.</span><span class="sxs-lookup"><span data-stu-id="2d151-145">Each data point has two attributes, namely, `timestamp` and `value`, to represent the number of phone calls at each day.</span></span> <span data-ttu-id="2d151-146">El número de llamadas telefónicas se marca como no confidencial.</span><span class="sxs-lookup"><span data-stu-id="2d151-146">The number of phone calls is transformed to de-sensitivity.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="2d151-147">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="2d151-147">Create classes and define paths</span></span>

<span data-ttu-id="2d151-148">A continuación, defina las estructuras de datos de la clase de entrada y de predicción.</span><span class="sxs-lookup"><span data-stu-id="2d151-148">Next, define your input and prediction class data structures.</span></span>

<span data-ttu-id="2d151-149">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="2d151-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="2d151-150">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2d151-150">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="2d151-151">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *s*.</span><span class="sxs-lookup"><span data-stu-id="2d151-151">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *PhoneCallsData.cs*.</span></span> <span data-ttu-id="2d151-152">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2d151-152">Then, select the **Add** button.</span></span>

   <span data-ttu-id="2d151-153">El archivo *PhoneCallsData.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="2d151-153">The *PhoneCallsData.cs* file opens in the code editor.</span></span>

3. <span data-ttu-id="2d151-154">Agregue la siguiente instrucción `using` al principio de *PhoneCallsData.cs*:</span><span class="sxs-lookup"><span data-stu-id="2d151-154">Add the following `using` statement to the top of *PhoneCallsData.cs*:</span></span>

   ```csharp
   using Microsoft.ML.Data;
   ```

4. <span data-ttu-id="2d151-155">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `PhoneCallsData` y `PhoneCallsPrediction`, al archivo *PhoneCallsData.cs*:</span><span class="sxs-lookup"><span data-stu-id="2d151-155">Remove the existing class definition and add the following code, which has two classes `PhoneCallsData` and `PhoneCallsPrediction`, to the *PhoneCallsData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](./snippets/phone-calls-anomaly-detection/csharp/PhoneCallsData.cs#DeclareTypes "Declare data record types")]

    <span data-ttu-id="2d151-156">`PhoneCallsData` especifica una clase de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="2d151-156">`PhoneCallsData` specifies an input data class.</span></span> <span data-ttu-id="2d151-157">El atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) especifica qué columnas (por índice de columna) del conjunto de datos se deben cargar.</span><span class="sxs-lookup"><span data-stu-id="2d151-157">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> <span data-ttu-id="2d151-158">Tiene dos atributos `timestamp` y `value` que se corresponden con los mismos atributos en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="2d151-158">It has two attributes `timestamp` and `value` that correspond to the same attributes in the data file.</span></span>

    <span data-ttu-id="2d151-159">`PhoneCallsPrediction` especifica la clase de datos de predicción.</span><span class="sxs-lookup"><span data-stu-id="2d151-159">`PhoneCallsPrediction` specifies the prediction data class.</span></span> <span data-ttu-id="2d151-160">Para el detector de SR-CNN, la predicción depende del [modo de detección](xref:Microsoft.ML.TimeSeries.SrCnnDetectMode) especificado.</span><span class="sxs-lookup"><span data-stu-id="2d151-160">For SR-CNN detector, the prediction depends on the [detect mode](xref:Microsoft.ML.TimeSeries.SrCnnDetectMode) specified.</span></span> <span data-ttu-id="2d151-161">En este ejemplo, se selecciona el modo `AnomalyAndMargin`.</span><span class="sxs-lookup"><span data-stu-id="2d151-161">In this sample, we select the `AnomalyAndMargin` mode.</span></span> <span data-ttu-id="2d151-162">La salida contiene siete columnas.</span><span class="sxs-lookup"><span data-stu-id="2d151-162">The output contains seven columns.</span></span> <span data-ttu-id="2d151-163">En la mayoría de los casos, `IsAnomaly`, `ExpectedValue`, `UpperBoundary` y `LowerBoundary` son lo suficientemente informativas.</span><span class="sxs-lookup"><span data-stu-id="2d151-163">In most cases, `IsAnomaly`, `ExpectedValue`, `UpperBoundary`, and `LowerBoundary` are informative enough.</span></span> <span data-ttu-id="2d151-164">Indican si un punto es una anomalía, el valor esperado del punto y la región del límite inferior y superior del punto.</span><span class="sxs-lookup"><span data-stu-id="2d151-164">They tell you if a point is an anomaly, the expected value of the point and the lower / upper boundary region of the point.</span></span>

5. <span data-ttu-id="2d151-165">Agregue el código siguiente a la línea inmediatamente por encima del método `Main` para especificar la ruta de acceso al archivo de datos:</span><span class="sxs-lookup"><span data-stu-id="2d151-165">Add the following code to the line right above the `Main` method to specify the path to your data file:</span></span>

    [!code-csharp[Declare global variables](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a><span data-ttu-id="2d151-166">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="2d151-166">Initialize variables in Main</span></span>

1. <span data-ttu-id="2d151-167">Reemplace la línea `Console.WriteLine("Hello World!")` del método `Main` por el siguiente código para declarar e inicializar la variable `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="2d151-167">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

    [!code-csharp[CreateMLContext](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    <span data-ttu-id="2d151-168">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="2d151-168">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="2d151-169">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="2d151-169">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="load-the-data"></a><span data-ttu-id="2d151-170">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="2d151-170">Load the data</span></span>

<span data-ttu-id="2d151-171">Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="2d151-171">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="2d151-172">`IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto).</span><span class="sxs-lookup"><span data-stu-id="2d151-172">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="2d151-173">Los datos se pueden cargar desde un archivo de texto o u otros orígenes (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="2d151-173">Data can be loaded from a text file or from other sources (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="2d151-174">Agregue el siguiente código como la siguiente línea del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="2d151-174">Add the following code as the next line of the `Main` method:</span></span>

    [!code-csharp[LoadData](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="2d151-175">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo.</span><span class="sxs-lookup"><span data-stu-id="2d151-175">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="2d151-176">Toma las variables de ruta de acceso de datos y devuelve `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="2d151-176">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="time-series-anomaly-detection"></a><span data-ttu-id="2d151-177">Detección de anomalías en una serie temporal</span><span class="sxs-lookup"><span data-stu-id="2d151-177">Time series anomaly detection</span></span>

<span data-ttu-id="2d151-178">La detección de anomalías en una serie temporal es el proceso de detectar valores atípicos de datos de series temporales, puntos en determinada serie temporal de entrada donde el comportamiento no es lo que se esperaba o es "extraño".</span><span class="sxs-lookup"><span data-stu-id="2d151-178">Time series anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span> <span data-ttu-id="2d151-179">Estas anomalías son normalmente indicativas de algunos eventos de interés en el dominio del problema: un ciberataque en las cuentas de usuario, una interrupción del suministro eléctrico, una ráfaga de solicitudes por segundo en un servidor, una fuga de memoria, etc.</span><span class="sxs-lookup"><span data-stu-id="2d151-179">These anomalies are typically indicative of some events of interest in the problem domain: a cyber-attack on user accounts, power outage, bursting RPS on a server, memory leak, etc.</span></span>

<span data-ttu-id="2d151-180">Para buscar anomalías en una serie temporal, primero debe determinar el período de la serie.</span><span class="sxs-lookup"><span data-stu-id="2d151-180">To find anomaly on time series, you should first determine the period of the series.</span></span> <span data-ttu-id="2d151-181">Después, la serie temporal se puede descomponer en varios componentes como `Y = T + S + R`, donde `Y` es la serie original, `T` es el componente de tendencia, `S` es el componente estacional y `R` es el componente residual de la serie.</span><span class="sxs-lookup"><span data-stu-id="2d151-181">Then, the time series can be decomposed into several components as `Y = T + S + R`, where `Y` is the original series, `T` is the trend component, `S` is the seasonal component, and `R` is the residual component of the series.</span></span> <span data-ttu-id="2d151-182">Este paso se denomina [descomposición](https://en.wikipedia.org/wiki/Decomposition_of_time_series).</span><span class="sxs-lookup"><span data-stu-id="2d151-182">This step is called [decomposition](https://en.wikipedia.org/wiki/Decomposition_of_time_series).</span></span> <span data-ttu-id="2d151-183">Por último, se realiza la detección en el componente residual para encontrar las anomalías.</span><span class="sxs-lookup"><span data-stu-id="2d151-183">Finally, detection is performed on the residual component to find the anomalies.</span></span> <span data-ttu-id="2d151-184">En ML.NET, el algoritmo SR-CNN es un algoritmo avanzado nuevo que se basa en la red neuronal residual (SR) y la red neuronal de circunvolución (CNN) para detectar anomalías en la serie temporal.</span><span class="sxs-lookup"><span data-stu-id="2d151-184">In ML.NET, The SR-CNN algorithm is an advanced and novel algorithm that is based on Spectral Residual (SR) and Convolutional Neural Network(CNN) to detect anomaly on time-series.</span></span> <span data-ttu-id="2d151-185">Para obtener más información sobre este algoritmo, consulte [Servicio de detección de anomalías en una serie temporal en Microsoft](https://arxiv.org/pdf/1906.03821.pdf).</span><span class="sxs-lookup"><span data-stu-id="2d151-185">For more information on this algorithm, see [Time-Series Anomaly Detection Service at Microsoft](https://arxiv.org/pdf/1906.03821.pdf).</span></span>

<span data-ttu-id="2d151-186">En este tutorial, verá que estos procedimientos se pueden llevar a cabo con dos funciones.</span><span class="sxs-lookup"><span data-stu-id="2d151-186">In this tutorial, you will see that these procedures can be completed using two functions.</span></span>

## <a name="detect-period"></a><span data-ttu-id="2d151-187">Detección del período</span><span class="sxs-lookup"><span data-stu-id="2d151-187">Detect Period</span></span>

<span data-ttu-id="2d151-188">En el primer paso, se invoca la función `DetectSeasonality` para determinar el período de la serie.</span><span class="sxs-lookup"><span data-stu-id="2d151-188">In the first step, we invoke the `DetectSeasonality` function to determine the period of the series.</span></span>

### <a name="create-the-detectperiod-method"></a><span data-ttu-id="2d151-189">Creación del método DetectPeriod</span><span class="sxs-lookup"><span data-stu-id="2d151-189">Create the DetectPeriod method</span></span>

1. <span data-ttu-id="2d151-190">Cree el método `DetectPeriod`, justo debajo del método `Main`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d151-190">Create the `DetectPeriod` method, just below the `Main` method, using the following code:</span></span>

    ```csharp
    static void DetectPeriod(MLContext mlContext, IDataView phoneCalls)
    {

    }
    ```

2. <span data-ttu-id="2d151-191">Utilice la función <xref:Microsoft.ML.TimeSeriesCatalog.DetectSeasonality%2A> para detectar el período.</span><span class="sxs-lookup"><span data-stu-id="2d151-191">Use the <xref:Microsoft.ML.TimeSeriesCatalog.DetectSeasonality%2A> function to detect period.</span></span> <span data-ttu-id="2d151-192">Agréguelo a un método `DetectPeriod` en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="2d151-192">Add it to the `DetectPeriod` method with the following code:</span></span>

    [!code-csharp[DetectSeasonality](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectSeasonality)]

3. <span data-ttu-id="2d151-193">Muestre el valor del período agregando lo que se indica a continuación como la siguiente línea de código en el método `DetectPeriod`:</span><span class="sxs-lookup"><span data-stu-id="2d151-193">Display the period value by adding the following as the next line of code in the `DetectPeriod` method:</span></span>

    [!code-csharp[DisplayPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayPeriod)]

4. <span data-ttu-id="2d151-194">Agregue la llamada siguiente al método `DetectPeriod` en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="2d151-194">Add the following call to the `DetectPeriod` method in the `Main` method:</span></span>

    [!code-csharp[CallDetectPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectPeriod)]

### <a name="period-detection-results"></a><span data-ttu-id="2d151-195">Resultados de la detección del período</span><span class="sxs-lookup"><span data-stu-id="2d151-195">Period detection results</span></span>

<span data-ttu-id="2d151-196">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d151-196">Run the application.</span></span> <span data-ttu-id="2d151-197">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="2d151-197">Your results should be similar to the following.</span></span>

```console
Period of the series is: 7.
```

## <a name="detect-anomaly"></a><span data-ttu-id="2d151-198">Detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="2d151-198">Detect Anomaly</span></span>

<span data-ttu-id="2d151-199">En este paso, usará el método <xref:Microsoft.ML.TimeSeriesCatalog.DetectEntireAnomalyBySrCnn%2A> para buscar anomalías.</span><span class="sxs-lookup"><span data-stu-id="2d151-199">In this step, you use the <xref:Microsoft.ML.TimeSeriesCatalog.DetectEntireAnomalyBySrCnn%2A> method to find anomalies.</span></span>

### <a name="create-the-detectanomaly-method"></a><span data-ttu-id="2d151-200">Creación del método DetectAnomaly</span><span class="sxs-lookup"><span data-stu-id="2d151-200">Create the DetectAnomaly method</span></span>

1. <span data-ttu-id="2d151-201">Cree el método `DetectAnomaly`, justo debajo del método `DetectPeriod`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d151-201">Create the `DetectAnomaly` method, just below the `DetectPeriod` method, using the following code:</span></span>

    ```csharp
    static void DetectAnomaly(MLContext mlContext, IDataView phoneCalls, int period)
    {

    }
    ```

2. <span data-ttu-id="2d151-202">Configure el método <xref:Microsoft.ML.TimeSeries.SrCnnEntireAnomalyDetectorOptions> en el método `DetectAnomaly` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d151-202">Set up <xref:Microsoft.ML.TimeSeries.SrCnnEntireAnomalyDetectorOptions> in the `DetectAnomaly` method with the following code:</span></span>

    [!code-csharp[SetupSrCnnParameters](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#SetupSrCnnParameters)]

3. <span data-ttu-id="2d151-203">Detecte anomalías mediante el algoritmo SR-CNN agregando la siguiente línea de código en el método `DetectAnomaly`:</span><span class="sxs-lookup"><span data-stu-id="2d151-203">Detect anomaly by SR-CNN algorithm by adding the following line of code in the `DetectAnomaly` method:</span></span>

    [!code-csharp[DetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectAnomaly)]

4. <span data-ttu-id="2d151-204">Convierta la vista de datos de salida en un `IEnumerable` fuertemente tipado para mostrar fácilmente mediante el método [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) con este código:</span><span class="sxs-lookup"><span data-stu-id="2d151-204">Convert the output data view into a strongly typed `IEnumerable` for easier display using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

    [!code-csharp[CreateEnumerableForResult](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateEnumerableForResult)]

5. <span data-ttu-id="2d151-205">Cree un encabezado de visualización con el siguiente código como la siguiente línea en el método `DetectAnomaly`:</span><span class="sxs-lookup"><span data-stu-id="2d151-205">Create a display header with the following code as the next line in the `DetectAnomaly` method:</span></span>

    [!code-csharp[DisplayHeader](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayHeader)]

    <span data-ttu-id="2d151-206">Se mostrará la siguiente información en los resultados de detección de puntos de cambio:</span><span class="sxs-lookup"><span data-stu-id="2d151-206">You'll display the following information in your change point detection results:</span></span>

    * <span data-ttu-id="2d151-207">`Index` es el índice de cada punto.</span><span class="sxs-lookup"><span data-stu-id="2d151-207">`Index` is the index of each point.</span></span>
    * <span data-ttu-id="2d151-208">`Anomaly` es el indicador de si cada punto se detecta como anomalía.</span><span class="sxs-lookup"><span data-stu-id="2d151-208">`Anomaly` is the indicator of whether each point is detected as anomaly.</span></span>
    * <span data-ttu-id="2d151-209">`ExpectedValue` es el valor estimado de cada punto.</span><span class="sxs-lookup"><span data-stu-id="2d151-209">`ExpectedValue` is the estimated value of each point.</span></span>
    * <span data-ttu-id="2d151-210">`LowerBoundary` es el valor más bajo de que cada punto no sea una anomalía.</span><span class="sxs-lookup"><span data-stu-id="2d151-210">`LowerBoundary` is the lowest value each point can be to be not anomaly.</span></span>
    * <span data-ttu-id="2d151-211">`UpperBoundary` es el valor más alto de que cada punto no sea una anomalía.</span><span class="sxs-lookup"><span data-stu-id="2d151-211">`UpperBoundary` is the highest value each point can be to be not anomaly.</span></span>

6. <span data-ttu-id="2d151-212">Itere en `predictions` `IEnumerable` y muestre los resultados con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="2d151-212">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

    [!code-csharp[DisplayAnomalyDetectionResults](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayAnomalyDetectionResults)]

7. <span data-ttu-id="2d151-213">Agregue la llamada siguiente al método `DetectAnomaly` en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="2d151-213">Add the following call to the `DetectAnomaly` method in the `Main` method:</span></span>

    [!code-csharp[CallDetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectAnomaly)]

## <a name="anomaly-detection-results"></a><span data-ttu-id="2d151-214">Resultados de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="2d151-214">Anomaly detection results</span></span>

<span data-ttu-id="2d151-215">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d151-215">Run the application.</span></span> <span data-ttu-id="2d151-216">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="2d151-216">Your results should be similar to the following.</span></span> <span data-ttu-id="2d151-217">Durante el procesamiento, se muestran mensajes.</span><span class="sxs-lookup"><span data-stu-id="2d151-217">During processing, messages are displayed.</span></span> <span data-ttu-id="2d151-218">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2d151-218">You may see warnings or processing messages.</span></span> <span data-ttu-id="2d151-219">Algunos de los mensajes se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="2d151-219">Some messages have been removed from the following results for clarity.</span></span>

```console
Detect period of the series
Period of the series is: 7.
Detect anomaly points in the series
Index   Data    Anomaly AnomalyScore    Mag     ExpectedValue   BoundaryUnit    UpperBoundary   LowerBoundary
0,0,36.841787256739266,41.14206982401966,32.541504689458876
1,0,35.67303618137362,39.97331874865401,31.372753614093227
2,0,34.710132999891826,39.029491313022824,30.390774686760828
3,0,33.44765248883495,37.786086547816545,29.10921842985335
4,0,28.937110922276364,33.25646923540736,24.61775260914537
5,0,5.143895892785781,9.444178460066171,0.843613325505391
6,0,5.163325228419392,9.463607795699783,0.8630426611390014
7,0,36.76414836240396,41.06443092968435,32.46386579512357
8,0,35.77908590657007,40.07936847385046,31.478803339289676
9,0,34.547259536635245,38.847542103915636,30.246976969354854
10,0,33.55193524820608,37.871293561337076,29.23257693507508
11,0,29.091800129624648,33.392082696905035,24.79151756234426
12,0,5.154836630338823,9.455119197619213,0.8545540630584334
13,0,5.234332502492464,9.534615069772855,0.934049935212073
14,0,36.54992549471526,40.85020806199565,32.24964292743487
15,0,35.79526470980883,40.095547277089224,31.494982142528443
16,0,34.34099013096804,38.64127269824843,30.040707563687647
17,0,33.61201516582131,37.9122977331017,29.31173259854092
18,0,29.223563320561812,33.5238458878422,24.923280753281425
19,0,5.170512168851533,9.470794736131923,0.8702296015711433
20,0,5.2614938889462834,9.561776456226674,0.9612113216658926
21,0,36.37103858487317,40.67132115215356,32.07075601759278
22,0,35.813544599026855,40.113827166307246,31.513262031746464
23,0,34.05600492733225,38.356287494612644,29.755722360051863
24,0,33.65828319077884,37.95856575805923,29.358000623498448
25,0,29.381125690882463,33.681408258162854,25.080843123602072
26,0,5.261543539820418,9.561826107100808,0.9612609725400283
27,0,5.4873712582971805,9.787653825577571,1.1870886910167897
28,1,36.504694001629254,40.804976568909645,32.20441143434886  <-- alert is on, detected anomaly
...
```

<span data-ttu-id="2d151-220">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="2d151-220">Congratulations!</span></span> <span data-ttu-id="2d151-221">Ya ha creado correctamente los modelos de aprendizaje automático para detectar períodos y anomalías en series periódicas.</span><span class="sxs-lookup"><span data-stu-id="2d151-221">You've now successfully built machine learning models for detecting period and anomaly on a periodical series.</span></span>

<span data-ttu-id="2d151-222">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="2d151-222">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection) repository.</span></span>

<span data-ttu-id="2d151-223">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="2d151-223">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="2d151-224">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="2d151-224">Load the data</span></span>
> * <span data-ttu-id="2d151-225">Detectar períodos en datos de una serie temporal</span><span class="sxs-lookup"><span data-stu-id="2d151-225">Detect period on the time series data</span></span>
> * <span data-ttu-id="2d151-226">Detectar anomalías en datos de una serie temporal</span><span class="sxs-lookup"><span data-stu-id="2d151-226">Detect anomaly on the time series data</span></span>

## <a name="next-steps"></a><span data-ttu-id="2d151-227">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2d151-227">Next steps</span></span>

<span data-ttu-id="2d151-228">Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo de detección de anomalías de consumo de energía.</span><span class="sxs-lookup"><span data-stu-id="2d151-228">Check out the Machine Learning samples GitHub repository to explore a Power Consumption Anomaly Detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="2d151-229">Repositorio dotnet/machinelearning-samples de GitHub</span><span class="sxs-lookup"><span data-stu-id="2d151-229">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)

---
title: 'Tutorial: Detección de anomalías en las ventas de productos'
description: Aprenda a crear una aplicación de detección de anomalías para los datos de ventas de productos. En este tutorial se va a crear una aplicación de consola de .NET Core mediante C# en Visual Studio 2019.
ms.date: 06/11/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 3e3e368ed3bcb35e7e2c8bdf08abe71afd4ae87c
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306226"
---
# <a name="tutorial-detect-anomalies-in-product-sales-with-mlnet"></a><span data-ttu-id="15baa-104">Tutorial: Detección de anomalías en ventas de productos con ML.NET</span><span class="sxs-lookup"><span data-stu-id="15baa-104">Tutorial: Detect anomalies in product sales with ML.NET</span></span>

<span data-ttu-id="15baa-105">Aprenda a crear una aplicación de detección de anomalías para los datos de ventas de productos.</span><span class="sxs-lookup"><span data-stu-id="15baa-105">Learn how to build an anomaly detection application for product sales data.</span></span> <span data-ttu-id="15baa-106">En este tutorial se va a crear una aplicación de consola de .NET Core mediante C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="15baa-106">This tutorial creates a .NET Core console application using C# in Visual Studio.</span></span>

<span data-ttu-id="15baa-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="15baa-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="15baa-108">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="15baa-108">Load the data</span></span>
> * <span data-ttu-id="15baa-109">Entrenar el modelo para la detección de anomalías de picos</span><span class="sxs-lookup"><span data-stu-id="15baa-109">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="15baa-110">Detectar anomalías de picos con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="15baa-110">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="15baa-111">Entrenar el modelo para la detección de anomalías de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="15baa-111">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="15baa-112">Detectar anomalías de puntos de cambio con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="15baa-112">Detect change point anomalies with the trained model</span></span>

<span data-ttu-id="15baa-113">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="15baa-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15baa-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="15baa-114">Prerequisites</span></span>

* <span data-ttu-id="15baa-115">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="15baa-115">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="15baa-116">El conjunto de datos product-sales.csv</span><span class="sxs-lookup"><span data-stu-id="15baa-116">The product-sales.csv dataset</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> <span data-ttu-id="15baa-117">El formato de datos en `product-sales.csv` se basa en el conjunto de datos "Shampoo Sales Over a Three Year Period" (Ventas de champú en un período de tres años) procedente originalmente de DataMarket y proporcionado por Time Series Data Library (TSDL), creado por Rob Hyndman.</span><span class="sxs-lookup"><span data-stu-id="15baa-117">The data format in `product-sales.csv` is based on the dataset “Shampoo Sales Over a Three Year Period” originally sourced from DataMarket and provided by Time Series Data Library (TSDL), created by Rob Hyndman.</span></span> <span data-ttu-id="15baa-118">Conjunto de datos "Shampoo Sales Over a Three Year Period" con una licencia de conjunto de datos que se concede de acuerdo con DataMarket Default Open License.</span><span class="sxs-lookup"><span data-stu-id="15baa-118">“Shampoo Sales Over a Three Year Period” Dataset Licensed Under the DataMarket Default Open License.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="15baa-119">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="15baa-119">Create a console application</span></span>

1. <span data-ttu-id="15baa-120">Cree una **aplicación de consola de .NET Core** denominada "ProductSalesAnomalyDetection".</span><span class="sxs-lookup"><span data-stu-id="15baa-120">Create a **.NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="15baa-121">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="15baa-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="15baa-122">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="15baa-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="15baa-123">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="15baa-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="15baa-124">Elija "nuget.org" como el origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione el paquete **v1.0.0** en la lista de paquetes y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="15baa-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select the **v1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="15baa-125">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="15baa-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="15baa-126">Repita estos pasos para **Microsoft.ML.TimeSeries v0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="15baa-126">Repeat these steps for **Microsoft.ML.TimeSeries v0.12.0**.</span></span>

4. <span data-ttu-id="15baa-127">Agregue las instrucciones `using` siguientes en la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="15baa-127">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="15baa-128">Descarga de los datos</span><span class="sxs-lookup"><span data-stu-id="15baa-128">Download your data</span></span>

1. <span data-ttu-id="15baa-129">Descargue el conjunto de datos y guárdelo en la carpeta *Datos* que creó anteriormente:</span><span class="sxs-lookup"><span data-stu-id="15baa-129">Download the dataset and save it to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="15baa-130">Haga clic con el botón derecho en [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) y seleccione "Guardar vínculo (o destino) como...".</span><span class="sxs-lookup"><span data-stu-id="15baa-130">Right click on [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="15baa-131">Asegúrese de que guarda el archivo \*.csv en la carpeta *Datos* o, después de guardarlo en otro lugar, mueva el archivo \*.csv a la carpeta *Datos*.</span><span class="sxs-lookup"><span data-stu-id="15baa-131">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="15baa-132">En el Explorador de soluciones, haga clic con el botón derecho en el archivo \*.csv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="15baa-132">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="15baa-133">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="15baa-133">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="15baa-134">La siguiente tabla es una vista previa de datos del archivo \*.csv:</span><span class="sxs-lookup"><span data-stu-id="15baa-134">The following table is a data preview from your \*.csv file:</span></span>

|<span data-ttu-id="15baa-135">Mes</span><span class="sxs-lookup"><span data-stu-id="15baa-135">Month</span></span>  |<span data-ttu-id="15baa-136">ProductSales</span><span class="sxs-lookup"><span data-stu-id="15baa-136">ProductSales</span></span> |
|-------|-------------|
|<span data-ttu-id="15baa-137">1 - Ene</span><span class="sxs-lookup"><span data-stu-id="15baa-137">1-Jan</span></span>  |    <span data-ttu-id="15baa-138">271</span><span class="sxs-lookup"><span data-stu-id="15baa-138">271</span></span>      |
|<span data-ttu-id="15baa-139">2 - Ene</span><span class="sxs-lookup"><span data-stu-id="15baa-139">2-Jan</span></span>  |    <span data-ttu-id="15baa-140">150,9</span><span class="sxs-lookup"><span data-stu-id="15baa-140">150.9</span></span>    |
|<span data-ttu-id="15baa-141">.....</span><span class="sxs-lookup"><span data-stu-id="15baa-141">.....</span></span>  |    <span data-ttu-id="15baa-142">.....</span><span class="sxs-lookup"><span data-stu-id="15baa-142">.....</span></span>    |
|<span data-ttu-id="15baa-143">1 - Feb</span><span class="sxs-lookup"><span data-stu-id="15baa-143">1-Feb</span></span>  |    <span data-ttu-id="15baa-144">199,3</span><span class="sxs-lookup"><span data-stu-id="15baa-144">199.3</span></span>    |
|<span data-ttu-id="15baa-145">.....</span><span class="sxs-lookup"><span data-stu-id="15baa-145">.....</span></span>  |    <span data-ttu-id="15baa-146">.....</span><span class="sxs-lookup"><span data-stu-id="15baa-146">.....</span></span>    |

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="15baa-147">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="15baa-147">Create classes and define paths</span></span>

<span data-ttu-id="15baa-148">A continuación, defina la estructura de datos de la clase de entrada.</span><span class="sxs-lookup"><span data-stu-id="15baa-148">Next, define your input class data structure.</span></span>

<span data-ttu-id="15baa-149">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="15baa-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="15baa-150">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="15baa-150">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="15baa-151">En el **cuadro de diálogo Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ProductSalesData.cs*.</span><span class="sxs-lookup"><span data-stu-id="15baa-151">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *ProductSalesData.cs*.</span></span> <span data-ttu-id="15baa-152">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="15baa-152">Then, select the **Add** button.</span></span>

<span data-ttu-id="15baa-153">El archivo *ProductSalesData.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="15baa-153">The *ProductSalesData.cs* file opens in the code editor.</span></span> <span data-ttu-id="15baa-154">Agregue la siguiente instrucción `using` al principio de *ProductSalesData.cs*:</span><span class="sxs-lookup"><span data-stu-id="15baa-154">Add the following `using` statement to the top of *ProductSalesData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="15baa-155">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases, `ProductSalesData` y `ProductSalesPrediction`, al archivo *ProductSalesData.cs*:</span><span class="sxs-lookup"><span data-stu-id="15baa-155">Remove the existing class definition and add the following code, which has two classes `ProductSalesData` and `ProductSalesPrediction`, to the *ProductSalesData.cs* file:</span></span>

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/ProductSalesData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="15baa-156">`ProductSalesData` especifica una clase de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="15baa-156">`ProductSalesData` specifies an input data class.</span></span> <span data-ttu-id="15baa-157">El atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) especifica qué columnas (por índice de columna) del conjunto de datos se deben cargar.</span><span class="sxs-lookup"><span data-stu-id="15baa-157">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> 

<span data-ttu-id="15baa-158">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="15baa-158">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="15baa-159">Debe crear dos campos globales para contener la ruta del archivo de conjunto de datos descargado recientemente y la ruta del archivo del modelo guardado:</span><span class="sxs-lookup"><span data-stu-id="15baa-159">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* <span data-ttu-id="15baa-160">`_dataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="15baa-160">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="15baa-161">`_docsize` tiene el número de registros en el archivo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="15baa-161">`_docsize` has the number of records in dataset file.</span></span> <span data-ttu-id="15baa-162">Se usará para calcular `pvalueHistoryLength`.</span><span class="sxs-lookup"><span data-stu-id="15baa-162">You'll use this to calculate `pvalueHistoryLength`.</span></span>

<span data-ttu-id="15baa-163">Agregue el código siguiente a la línea justo encima del método `Main` para especificar las rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="15baa-163">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="15baa-164">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="15baa-164">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="15baa-165">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="15baa-165">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="15baa-166">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="15baa-166">Initialize variables in Main</span></span>

<span data-ttu-id="15baa-167">Reemplace la línea `Console.WriteLine("Hello World!")` en el método `Main` con el siguiente código para declarar e inicializar la variable `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="15baa-167">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateMLContext "Create the ML Context")]

### <a name="load-the-data"></a><span data-ttu-id="15baa-168">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="15baa-168">Load the data</span></span>

<span data-ttu-id="15baa-169">Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="15baa-169">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="15baa-170">`IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto).</span><span class="sxs-lookup"><span data-stu-id="15baa-170">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="15baa-171">Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="15baa-171">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span> <span data-ttu-id="15baa-172">Agregue el siguiente código como la siguiente línea del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="15baa-172">Add the following code as the next line of the `Main()` method:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#LoadData "loading dataset")]

<span data-ttu-id="15baa-173">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo.</span><span class="sxs-lookup"><span data-stu-id="15baa-173">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="15baa-174">Toma las variables de ruta de acceso de datos y devuelve `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="15baa-174">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="ml-task---time-series-anomaly-detection"></a><span data-ttu-id="15baa-175">Tareas de ML: detección de anomalías de serie temporal</span><span class="sxs-lookup"><span data-stu-id="15baa-175">ML task - time series anomaly detection</span></span> 

<span data-ttu-id="15baa-176">La detección de anomalías marca comportamientos o eventos inesperados o poco habituales.</span><span class="sxs-lookup"><span data-stu-id="15baa-176">Anomaly detection flags unexpected or unusual events or behaviors.</span></span> <span data-ttu-id="15baa-177">Proporciona pistas sobre dónde buscar problemas y ayuda a responder la pregunta "¿es extraño esto?".</span><span class="sxs-lookup"><span data-stu-id="15baa-177">It gives clues where to look for problems and helps you answer the question "Is this weird?".</span></span>

![Es extraño esto](./media/sales-anomaly-detection/anomalydetection.png)

<span data-ttu-id="15baa-179">La detección de anomalías es el proceso de detectar valores atípicos de datos de series temporales, puntos en determinada serie temporal de entrada donde el comportamiento no es lo que se esperaba o es "extraño".</span><span class="sxs-lookup"><span data-stu-id="15baa-179">Anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span>

<span data-ttu-id="15baa-180">Esto puede resultar útil de muchas maneras.</span><span class="sxs-lookup"><span data-stu-id="15baa-180">This can be useful in lots of ways.</span></span> <span data-ttu-id="15baa-181">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="15baa-181">For instance:</span></span>

<span data-ttu-id="15baa-182">Si tiene un automóvil, tal vez desee saber: ¿Es normal la lectura del medidor de gasolina o tengo una fuga?</span><span class="sxs-lookup"><span data-stu-id="15baa-182">If you have a car, you might want to know: Is this oil gauge reading normal, or do I have a leak?</span></span>
<span data-ttu-id="15baa-183">Si está supervisando el consumo de energía, desearía saber: ¿Hay una interrupción?</span><span class="sxs-lookup"><span data-stu-id="15baa-183">If you're monitoring power consumption, you’d want to know: Is there an outage?</span></span>

<span data-ttu-id="15baa-184">Hay dos tipos de anomalías de series temporales que se pueden detectar:</span><span class="sxs-lookup"><span data-stu-id="15baa-184">There are two types of time series anomalies that can be detected:</span></span> 

* <span data-ttu-id="15baa-185">Los **picos** indican ráfagas temporales de comportamiento anómalo en el sistema.</span><span class="sxs-lookup"><span data-stu-id="15baa-185">**Spikes** indicate temporary bursts of anomalous behavior in the system.</span></span> 

* <span data-ttu-id="15baa-186">Los **puntos de cambio** indican el inicio de cambios persistentes con el tiempo en el sistema.</span><span class="sxs-lookup"><span data-stu-id="15baa-186">**Change points** indicate the beginning of persistent changes over time in the system.</span></span> 

<span data-ttu-id="15baa-187">En ML.NET, los algoritmos de la detección de picos de IID o de la detección de puntos de cambio de IID son adecuados para los [conjuntos de datos independientes y distribuidos de manera idéntica](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span><span class="sxs-lookup"><span data-stu-id="15baa-187">In ML.NET, The IID Spike Detection or IID Change point Detection algorithms are suited for [independent and identically distributed datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span></span> 

<span data-ttu-id="15baa-188">Analizará los mismos datos de ventas de productos para detectar los picos y los puntos de cambio.</span><span class="sxs-lookup"><span data-stu-id="15baa-188">You'll analyze the same product sales data to detect spikes and change points.</span></span> <span data-ttu-id="15baa-189">El proceso de modelo de entrenamiento y compilación es el mismo para la detección de picos y la detección de puntos de cambio. La principal diferencia es el algoritmo de detección específico que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="15baa-189">The building and training model process is the same for spike detection and change point detection; the main difference is the specific detection algorithm used.</span></span>

## <a name="spike-detection"></a><span data-ttu-id="15baa-190">Detección de picos</span><span class="sxs-lookup"><span data-stu-id="15baa-190">Spike detection</span></span> 

<span data-ttu-id="15baa-191">El objetivo de la detección de picos es identificar ráfagas repentinas pero temporales que difieren significativamente de la mayoría de los valores de datos de las series temporales.</span><span class="sxs-lookup"><span data-stu-id="15baa-191">The goal of spike detection is to identify sudden yet temporary bursts that significantly differ from the majority of the time series data values.</span></span> <span data-ttu-id="15baa-192">Es importante detectar estos elementos, eventos u observaciones poco frecuentes y sospechosos de manera oportuna con el fin de minimizarlos.</span><span class="sxs-lookup"><span data-stu-id="15baa-192">It's important to detect these suspicious rare items, events or observations in a timely manner to be minimized.</span></span> <span data-ttu-id="15baa-193">El siguiente enfoque puede utilizarse para detectar una variedad de anomalías, como interrupciones, ciberataques o contenido web viral.</span><span class="sxs-lookup"><span data-stu-id="15baa-193">The following approach can be used to detect a variety of anomalies such as: outages, cyber-attacks, or viral web content.</span></span> <span data-ttu-id="15baa-194">La siguiente imagen es un ejemplo de los picos de un conjunto de datos de serie temporal:</span><span class="sxs-lookup"><span data-stu-id="15baa-194">The following image is an example of spikes in a time series dataset:</span></span>

![SpikeDetection](./media/sales-anomaly-detection/SpikeDetection.png)

### <a name="create-the-detectspike-method"></a><span data-ttu-id="15baa-196">Crear el método DetectSpike()</span><span class="sxs-lookup"><span data-stu-id="15baa-196">Create the DetectSpike() method</span></span>

<span data-ttu-id="15baa-197">Agregue la siguiente llamada al método `DetectSpike()` como siguiente línea de código del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="15baa-197">Add the following call to the `DetectSpike()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectSpike](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectSpike)]

<span data-ttu-id="15baa-198">El método `DetectSpike()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="15baa-198">The `DetectSpike()` method executes the following tasks:</span></span>

* <span data-ttu-id="15baa-199">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="15baa-199">Trains the model.</span></span>
* <span data-ttu-id="15baa-200">Detecta picos en función de los datos históricos de ventas.</span><span class="sxs-lookup"><span data-stu-id="15baa-200">Detects spikes based on historical sales data.</span></span>
* <span data-ttu-id="15baa-201">Muestra los resultados.</span><span class="sxs-lookup"><span data-stu-id="15baa-201">Displays the results.</span></span>

<span data-ttu-id="15baa-202">Cree el método `DetectSpike()`, justo después del método `Main()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="15baa-202">Create the `DetectSpike()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="15baa-203">Use [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) para entrenar el modelo para la detección de picos.</span><span class="sxs-lookup"><span data-stu-id="15baa-203">Use the [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) to train the model for spike detection.</span></span> <span data-ttu-id="15baa-204">Agréguelo a un método `DetectChangepoint()` en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="15baa-204">Add it to the `DetectChangepoint()` method with the following code:</span></span>

[!code-csharp[AddSpikeTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddSpikeTrainer)]

<span data-ttu-id="15baa-205">Para ajustar el modelo a los datos de `productSales`, agregue lo que se indica debajo como la siguiente línea de código en el método `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="15baa-205">Fit the model to the `productSales` data by adding the following as the next line of code in the `DetectSpike()` method:</span></span>

[!code-csharp[TrainModel1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel1)]

<span data-ttu-id="15baa-206">El método [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) entrena el modelo al transformar el conjunto de datos y aplicar el aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="15baa-206">The [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="15baa-207">Agregue la siguiente línea de código para transformar los datos `productSales` como la siguiente línea en el método `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="15baa-207">Add the following line of code to transform the `productSales` data as the next line in the `DetectSpike()` method:</span></span>

[!code-csharp[TransformData1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData1)]

<span data-ttu-id="15baa-208">El código anterior usa el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) para realizar predicciones para varias filas de entrada de un conjunto de datos de prueba especificado.</span><span class="sxs-lookup"><span data-stu-id="15baa-208">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="15baa-209">Convierta su `transformedData` en `IEnumerable` fuertemente tipado para mostrar fácilmente mediante el método [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="15baa-209">Convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

[!code-csharp[CreateEnumerable1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable1)]

<span data-ttu-id="15baa-210">Cree una línea de encabezado de visualización mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="15baa-210">Create a display header line using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayHeader1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader1)]

<span data-ttu-id="15baa-211">Se mostrará la siguiente información en los resultados de detección de picos:</span><span class="sxs-lookup"><span data-stu-id="15baa-211">You'll display the following information in your spike detection results:</span></span>

* <span data-ttu-id="15baa-212">`Alert` indica una alerta de pico para determinado punto de datos.</span><span class="sxs-lookup"><span data-stu-id="15baa-212">`Alert` indicates a spike alert for a given data point.</span></span>

* <span data-ttu-id="15baa-213">`Score` es el valor `ProductSales` para determinado punto de datos en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="15baa-213">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>

* <span data-ttu-id="15baa-214">`P-Value` La "P" significa probabilidad.</span><span class="sxs-lookup"><span data-stu-id="15baa-214">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="15baa-215">Esto indica la probabilidad de que este punto de datos sea una anomalía.</span><span class="sxs-lookup"><span data-stu-id="15baa-215">This indicates how likely this data point is an anomaly.</span></span> 

<span data-ttu-id="15baa-216">Use el siguiente código para iterar en `predictions` `IEnumerable` y mostrar los resultados:</span><span class="sxs-lookup"><span data-stu-id="15baa-216">Use the following code to iterate through the `predictions` `IEnumerable` and display the results:</span></span>

[!code-csharp[DisplayResults1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults1)]

## <a name="spike-detection-results"></a><span data-ttu-id="15baa-217">Resultados de la detección de picos</span><span class="sxs-lookup"><span data-stu-id="15baa-217">Spike detection results</span></span>

<span data-ttu-id="15baa-218">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="15baa-218">Your results should be similar to the following.</span></span> <span data-ttu-id="15baa-219">Durante el procesamiento, se muestran mensajes.</span><span class="sxs-lookup"><span data-stu-id="15baa-219">During processing, messages are displayed.</span></span> <span data-ttu-id="15baa-220">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="15baa-220">You may see warnings, or processing messages.</span></span> <span data-ttu-id="15baa-221">Se han quitado de los siguientes resultados para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="15baa-221">These have been removed from the following results for clarity.</span></span>

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a><span data-ttu-id="15baa-222">Detección de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="15baa-222">Change point detection</span></span>

<span data-ttu-id="15baa-223">`Change points` son cambios permanentes en una distribución de valores de secuencia de eventos de serie temporal, como los cambios de nivel y las tendencias.</span><span class="sxs-lookup"><span data-stu-id="15baa-223">`Change points` are persistent changes in a time series event stream distribution of values, like level changes and trends.</span></span> <span data-ttu-id="15baa-224">Estos cambios persistentes duran mucho más tiempo que `spikes` y podrían indicar eventos catastróficos.</span><span class="sxs-lookup"><span data-stu-id="15baa-224">These persistent changes last much longer than `spikes` and could indicate catastrophic event(s).</span></span> <span data-ttu-id="15baa-225">`Change points` no son normalmente visibles a simple vista, pero se pueden detectar en los datos mediante enfoques como el del siguiente método.</span><span class="sxs-lookup"><span data-stu-id="15baa-225">`Change points` are not usually visible to the naked eye, but can be detected in your data using approaches such as in the following method.</span></span>  <span data-ttu-id="15baa-226">La siguiente imagen es un ejemplo de una detección de puntos de cambio:</span><span class="sxs-lookup"><span data-stu-id="15baa-226">The following image is an example of a change point detection:</span></span>

![ChangePointDetection](./media/sales-anomaly-detection/ChangePointDetection.png)

### <a name="create-the-detectchangepoint-method"></a><span data-ttu-id="15baa-228">Crear el método DetectChangepoint()</span><span class="sxs-lookup"><span data-stu-id="15baa-228">Create the DetectChangepoint() method</span></span>

<span data-ttu-id="15baa-229">Agregue la siguiente llamada al método `DetectChangepoint()` como siguiente línea de código del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="15baa-229">Add the following call to the `DetectChangepoint()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectChangepoint](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectChangepoint)]

<span data-ttu-id="15baa-230">El método `DetectChangepoint()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="15baa-230">The `DetectChangepoint()` method executes the following tasks:</span></span>

* <span data-ttu-id="15baa-231">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="15baa-231">Trains the model.</span></span>
* <span data-ttu-id="15baa-232">Detecta puntos de cambio en función de los datos históricos de ventas.</span><span class="sxs-lookup"><span data-stu-id="15baa-232">Detects change points based on historical sales data.</span></span>
* <span data-ttu-id="15baa-233">Muestra los resultados.</span><span class="sxs-lookup"><span data-stu-id="15baa-233">Displays the results.</span></span>

<span data-ttu-id="15baa-234">Cree el método `DetectChangepoint()`, justo después del método `Main()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="15baa-234">Create the `DetectChangepoint()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="15baa-235">[iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) se usa para entrenar el modelo para la detección de puntos de cambio.</span><span class="sxs-lookup"><span data-stu-id="15baa-235">The [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) is used to train the model for change point detection.</span></span> <span data-ttu-id="15baa-236">Agréguelo a un método `DetectChangepoint()` en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="15baa-236">Add it to the `DetectChangepoint()` method with the following code:</span></span>

[!code-csharp[AddChangepointTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddChangepointTrainer)]

<span data-ttu-id="15baa-237">Tal como se ha hecho anteriormente, para ajustar el modelo a los datos de `productSales`, agregue lo que se indica debajo como la siguiente línea de código en el método `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="15baa-237">As you did previously, fit the model to the `productSales` data by adding the following as the next line of code in the `DetectChangePoint()` method:</span></span>

[!code-csharp[TrainModel2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel2)]

<span data-ttu-id="15baa-238">Use el método `Transform()` para transformar los datos de `Training` mediante la adición del código siguiente a `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="15baa-238">Use the `Transform()` method to transform the `Training` data by adding the following code to `DetectChangePoint()`:</span></span>

[!code-csharp[TransformData2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData2)]

<span data-ttu-id="15baa-239">Como lo hizo anteriormente, convierta su `transformedData` en `IEnumerable` fuertemente tipado para mostrar fácilmente mediante el método `CreateEnumerable()` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="15baa-239">As you did previously, convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the `CreateEnumerable()`method with the following code:</span></span>

[!code-csharp[CreateEnumerable2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable2)]

<span data-ttu-id="15baa-240">Cree un encabezado de visualización con el siguiente código como la siguiente línea en el método `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="15baa-240">Create a display header with the following code as the next line in the `DetectChangePoint()` method:</span></span>

[!code-csharp[DisplayHeader2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader2)]

<span data-ttu-id="15baa-241">Se mostrará la siguiente información en los resultados de detección de puntos de cambio:</span><span class="sxs-lookup"><span data-stu-id="15baa-241">You'll display the following information in your change point detection results:</span></span>

* <span data-ttu-id="15baa-242">`Alert` indica una alerta de punto de cambio para determinado punto de datos.</span><span class="sxs-lookup"><span data-stu-id="15baa-242">`Alert` indicates a change point alert for a given data point.</span></span>
* <span data-ttu-id="15baa-243">`Score` es el valor `ProductSales` para determinado punto de datos en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="15baa-243">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
* <span data-ttu-id="15baa-244">`P-Value` La "P" significa probabilidad.</span><span class="sxs-lookup"><span data-stu-id="15baa-244">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="15baa-245">Esto indica la probabilidad de que este punto de datos sea una anomalía.</span><span class="sxs-lookup"><span data-stu-id="15baa-245">This indicates how likely this data point is an anomaly.</span></span> 
* <span data-ttu-id="15baa-246">`Martingale value` se usa para identificar cuán "extraño" es un punto de datos, en función de la secuencia de valores de P.</span><span class="sxs-lookup"><span data-stu-id="15baa-246">`Martingale value` is used to identify how "weird" a data point is, based on the sequence of P-values.</span></span>  

<span data-ttu-id="15baa-247">Itere en `predictions` `IEnumerable` y muestre los resultados con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="15baa-247">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

[!code-csharp[DisplayResults2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults2)]

## <a name="change-point-detection-results"></a><span data-ttu-id="15baa-248">Resultados de la detección de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="15baa-248">Change point detection results</span></span>

<span data-ttu-id="15baa-249">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="15baa-249">Your results should be similar to the following.</span></span> <span data-ttu-id="15baa-250">Durante el procesamiento, se muestran mensajes.</span><span class="sxs-lookup"><span data-stu-id="15baa-250">During processing, messages are displayed.</span></span> <span data-ttu-id="15baa-251">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="15baa-251">You may see warnings, or processing messages.</span></span> <span data-ttu-id="15baa-252">Se han quitado de los siguientes resultados para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="15baa-252">These have been removed from the following results for clarity.</span></span>

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

<span data-ttu-id="15baa-253">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="15baa-253">Congratulations!</span></span> <span data-ttu-id="15baa-254">Ya ha creado correctamente los modelos de aprendizaje automático para detectar anomalías de picos y puntos de cambio en los datos de ventas.</span><span class="sxs-lookup"><span data-stu-id="15baa-254">You've now successfully built machine learning models for detecting spikes and change point anomalies in sales data.</span></span>

<span data-ttu-id="15baa-255">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="15baa-255">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

<span data-ttu-id="15baa-256">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="15baa-256">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="15baa-257">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="15baa-257">Load the data</span></span>
> * <span data-ttu-id="15baa-258">Entrenar el modelo para la detección de anomalías de picos</span><span class="sxs-lookup"><span data-stu-id="15baa-258">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="15baa-259">Detectar anomalías de picos con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="15baa-259">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="15baa-260">Entrenar el modelo para la detección de anomalías de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="15baa-260">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="15baa-261">Detectar anomalías de puntos de cambio con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="15baa-261">Detect change point anomalies with the trained mode</span></span>

## <a name="next-steps"></a><span data-ttu-id="15baa-262">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="15baa-262">Next steps</span></span>

<span data-ttu-id="15baa-263">Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo de detección de anomalías de consumo de energía.</span><span class="sxs-lookup"><span data-stu-id="15baa-263">Check out the Machine Learning samples GitHub repository to explore a Power Consumption Anomaly Detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="15baa-264">Repositorio dotnet/machinelearning-samples de GitHub</span><span class="sxs-lookup"><span data-stu-id="15baa-264">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)

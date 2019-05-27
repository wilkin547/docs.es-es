---
title: Uso de ML.NET en un escenario de detección de anomalías de ventas
description: Descubra cómo usar ML.NET en un escenario de detección de anomalías de ventas de productos para aprender a analizar los datos de los picos de anomalías y puntos de cambio para realizar la acción adecuada.
ms.date: 05/06/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: b0dbd8793e2be3973c37f0f78bc0ddd61b6bfea7
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065658"
---
# <a name="tutorial-use-mlnet-for-product-sales-anomaly-detection"></a><span data-ttu-id="5d384-103">Tutorial: Uso de ML.NET para la detección de anomalías de ventas de productos</span><span class="sxs-lookup"><span data-stu-id="5d384-103">Tutorial: Use ML.NET for product sales anomaly detection</span></span> 

<span data-ttu-id="5d384-104">En este tutorial de ejemplo se muestra cómo utilizar ML.NET para detectar anomalías en datos de ventas de productos para realizar la acción adecuada a través de una aplicación de consola de .NET Core mediante C# en Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="5d384-104">This sample tutorial illustrates using ML.NET to detect anomalies in product sales data to take the appropriate action via a .NET Core console application using C# in Visual Studio 2019.</span></span> 

<span data-ttu-id="5d384-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="5d384-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5d384-106">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="5d384-106">Load the data</span></span>
> * <span data-ttu-id="5d384-107">Entrenar el modelo para la detección de anomalías de picos</span><span class="sxs-lookup"><span data-stu-id="5d384-107">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="5d384-108">Detectar anomalías de picos con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="5d384-108">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="5d384-109">Entrenar el modelo para la detección de anomalías de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="5d384-109">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="5d384-110">Detectar anomalías de puntos de cambio con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="5d384-110">Detect change point anomalies with the trained model</span></span>

<span data-ttu-id="5d384-111">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="5d384-111">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5d384-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5d384-112">Prerequisites</span></span>

* <span data-ttu-id="5d384-113">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="5d384-113">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="5d384-114">El conjunto de datos product-sales.csv</span><span class="sxs-lookup"><span data-stu-id="5d384-114">The product-sales.csv dataset</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> <span data-ttu-id="5d384-115">El formato de datos en `product-sales.csv` se basa en el conjunto de datos "Shampoo Sales Over a Three Year Period" (Ventas de champú en un período de tres años) procedente originalmente de DataMarket y proporcionado por Time Series Data Library (TSDL), creado por Rob Hyndman.</span><span class="sxs-lookup"><span data-stu-id="5d384-115">The data format in `product-sales.csv` is based on the dataset “Shampoo Sales Over a Three Year Period” originally sourced from DataMarket and provided by Time Series Data Library (TSDL), created by Rob Hyndman.</span></span> <span data-ttu-id="5d384-116">Conjunto de datos "Shampoo Sales Over a Three Year Period" con una licencia de conjunto de datos que se concede de acuerdo con DataMarket Default Open License.</span><span class="sxs-lookup"><span data-stu-id="5d384-116">“Shampoo Sales Over a Three Year Period” Dataset Licensed Under the DataMarket Default Open License.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="5d384-117">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="5d384-117">Create a console application</span></span>

1. <span data-ttu-id="5d384-118">Cree una **aplicación de consola de .NET Core** denominada "ProductSalesAnomalyDetection".</span><span class="sxs-lookup"><span data-stu-id="5d384-118">Create a **.NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="5d384-119">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="5d384-119">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="5d384-120">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="5d384-120">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="5d384-121">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="5d384-121">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="5d384-122">Elija "nuget.org" como el origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione el paquete **v1.0.0** en la lista de paquetes y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="5d384-122">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select the **v1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="5d384-123">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="5d384-123">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="5d384-124">Repita estos pasos para **Microsoft.ML.TimeSeries v0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="5d384-124">Repeat these steps for **Microsoft.ML.TimeSeries v0.12.0**.</span></span>

4. <span data-ttu-id="5d384-125">Agregue las instrucciones `using` siguientes en la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="5d384-125">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="5d384-126">Descarga de los datos</span><span class="sxs-lookup"><span data-stu-id="5d384-126">Download your data</span></span>

1. <span data-ttu-id="5d384-127">Descargue el conjunto de datos y guárdelo en la carpeta *Datos* que creó anteriormente:</span><span class="sxs-lookup"><span data-stu-id="5d384-127">Download the dataset and save it to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="5d384-128">Haga clic con el botón derecho en [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) y seleccione "Guardar vínculo (o destino) como...".</span><span class="sxs-lookup"><span data-stu-id="5d384-128">Right click on [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="5d384-129">Asegúrese de que guarda el archivo \*.csv en la carpeta *Datos* o, después de guardarlo en otro lugar, mueva el archivo \*.csv a la carpeta *Datos*.</span><span class="sxs-lookup"><span data-stu-id="5d384-129">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="5d384-130">En el Explorador de soluciones, haga clic con el botón derecho en el archivo \*.csv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5d384-130">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="5d384-131">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="5d384-131">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="5d384-132">La siguiente tabla es una vista previa de datos del archivo \*.csv:</span><span class="sxs-lookup"><span data-stu-id="5d384-132">The following table is a data preview from your \*.csv file:</span></span>

|<span data-ttu-id="5d384-133">Mes</span><span class="sxs-lookup"><span data-stu-id="5d384-133">Month</span></span>  |<span data-ttu-id="5d384-134">ProductSales</span><span class="sxs-lookup"><span data-stu-id="5d384-134">ProductSales</span></span> |
|-------|-------------|
|<span data-ttu-id="5d384-135">1 - Ene</span><span class="sxs-lookup"><span data-stu-id="5d384-135">1-Jan</span></span>  |    <span data-ttu-id="5d384-136">271</span><span class="sxs-lookup"><span data-stu-id="5d384-136">271</span></span>      |
|<span data-ttu-id="5d384-137">2 - Ene</span><span class="sxs-lookup"><span data-stu-id="5d384-137">2-Jan</span></span>  |    <span data-ttu-id="5d384-138">150,9</span><span class="sxs-lookup"><span data-stu-id="5d384-138">150.9</span></span>    |
|<span data-ttu-id="5d384-139">.....</span><span class="sxs-lookup"><span data-stu-id="5d384-139">.....</span></span>  |    <span data-ttu-id="5d384-140">.....</span><span class="sxs-lookup"><span data-stu-id="5d384-140">.....</span></span>    |
|<span data-ttu-id="5d384-141">1 - Feb</span><span class="sxs-lookup"><span data-stu-id="5d384-141">1-Feb</span></span>  |    <span data-ttu-id="5d384-142">199,3</span><span class="sxs-lookup"><span data-stu-id="5d384-142">199.3</span></span>    |
|<span data-ttu-id="5d384-143">.....</span><span class="sxs-lookup"><span data-stu-id="5d384-143">.....</span></span>  |    <span data-ttu-id="5d384-144">.....</span><span class="sxs-lookup"><span data-stu-id="5d384-144">.....</span></span>    |

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="5d384-145">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="5d384-145">Create classes and define paths</span></span>

<span data-ttu-id="5d384-146">A continuación, defina la estructura de datos de la clase de entrada.</span><span class="sxs-lookup"><span data-stu-id="5d384-146">Next, define your input class data structure.</span></span>

<span data-ttu-id="5d384-147">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="5d384-147">Add a new class to your project:</span></span>

1. <span data-ttu-id="5d384-148">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="5d384-148">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="5d384-149">En el **cuadro de diálogo Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ProductSalesData.cs*.</span><span class="sxs-lookup"><span data-stu-id="5d384-149">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *ProductSalesData.cs*.</span></span> <span data-ttu-id="5d384-150">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5d384-150">Then, select the **Add** button.</span></span>

<span data-ttu-id="5d384-151">El archivo *ProductSalesData.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="5d384-151">The *ProductSalesData.cs* file opens in the code editor.</span></span> <span data-ttu-id="5d384-152">Agregue la siguiente instrucción `using` al principio de *ProductSalesData.cs*:</span><span class="sxs-lookup"><span data-stu-id="5d384-152">Add the following `using` statement to the top of *ProductSalesData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="5d384-153">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases, `ProductSalesData` y `ProductSalesPrediction`, al archivo *ProductSalesData.cs*:</span><span class="sxs-lookup"><span data-stu-id="5d384-153">Remove the existing class definition and add the following code, which has two classes `ProductSalesData` and `ProductSalesPrediction`, to the *ProductSalesData.cs* file:</span></span>

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/ProductSalesData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="5d384-154">`ProductSalesData` especifica una clase de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="5d384-154">`ProductSalesData` specifies an input data class.</span></span> <span data-ttu-id="5d384-155">El atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) especifica qué columnas (por índice de columna) del conjunto de datos se deben cargar.</span><span class="sxs-lookup"><span data-stu-id="5d384-155">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> 

<span data-ttu-id="5d384-156">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="5d384-156">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="5d384-157">Debe crear dos campos globales para contener la ruta del archivo de conjunto de datos descargado recientemente y la ruta del archivo del modelo guardado:</span><span class="sxs-lookup"><span data-stu-id="5d384-157">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* <span data-ttu-id="5d384-158">`_dataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="5d384-158">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="5d384-159">`_docsize` tiene el número de registros en el archivo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="5d384-159">`_docsize` has the number of records in dataset file.</span></span> <span data-ttu-id="5d384-160">Se usará para calcular `pvalueHistoryLength`.</span><span class="sxs-lookup"><span data-stu-id="5d384-160">You'll use this to calculate `pvalueHistoryLength`.</span></span>

<span data-ttu-id="5d384-161">Agregue el código siguiente a la línea justo encima del método `Main` para especificar las rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="5d384-161">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="5d384-162">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="5d384-162">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="5d384-163">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="5d384-163">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="5d384-164">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="5d384-164">Initialize variables in Main</span></span>

<span data-ttu-id="5d384-165">Reemplace la línea `Console.WriteLine("Hello World!")` en el método `Main` con el siguiente código para declarar e inicializar la variable `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="5d384-165">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateMLContext "Create the ML Context")]

### <a name="load-the-data"></a><span data-ttu-id="5d384-166">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="5d384-166">Load the data</span></span>

<span data-ttu-id="5d384-167">Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="5d384-167">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="5d384-168">`IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto).</span><span class="sxs-lookup"><span data-stu-id="5d384-168">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="5d384-169">Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="5d384-169">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span> <span data-ttu-id="5d384-170">Agregue el siguiente código como la siguiente línea del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="5d384-170">Add the following code as the next line of the `Main()` method:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#LoadData "loading dataset")]

<span data-ttu-id="5d384-171">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo.</span><span class="sxs-lookup"><span data-stu-id="5d384-171">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="5d384-172">Toma las variables de ruta de acceso de datos y devuelve `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="5d384-172">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="ml-task---time-series-anomaly-detection"></a><span data-ttu-id="5d384-173">Tareas de ML: detección de anomalías de serie temporal</span><span class="sxs-lookup"><span data-stu-id="5d384-173">ML task - time series anomaly detection</span></span> 

<span data-ttu-id="5d384-174">La detección de anomalías marca comportamientos o eventos inesperados o poco habituales.</span><span class="sxs-lookup"><span data-stu-id="5d384-174">Anomaly detection flags unexpected or unusual events or behaviors.</span></span> <span data-ttu-id="5d384-175">Proporciona pistas sobre dónde buscar problemas y ayuda a responder la pregunta "¿es extraño esto?".</span><span class="sxs-lookup"><span data-stu-id="5d384-175">It gives clues where to look for problems and helps you answer the question "Is this weird?".</span></span>

![Es extraño esto](./media/sales-anomaly-detection/anomalydetection.png)

<span data-ttu-id="5d384-177">La detección de anomalías es el proceso de detectar valores atípicos de datos de series temporales, puntos en determinada serie temporal de entrada donde el comportamiento no es lo que se esperaba o es "extraño".</span><span class="sxs-lookup"><span data-stu-id="5d384-177">Anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span>

<span data-ttu-id="5d384-178">Esto puede resultar útil de muchas maneras.</span><span class="sxs-lookup"><span data-stu-id="5d384-178">This can be useful in lots of ways.</span></span> <span data-ttu-id="5d384-179">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5d384-179">For instance:</span></span>

<span data-ttu-id="5d384-180">Si tiene un automóvil, tal vez desee saber: ¿Es normal la lectura del medidor de gasolina o tengo una fuga?</span><span class="sxs-lookup"><span data-stu-id="5d384-180">If you have a car, you might want to know: Is this oil gauge reading normal, or do I have a leak?</span></span>
<span data-ttu-id="5d384-181">Si está supervisando el consumo de energía, desearía saber: ¿Hay una interrupción?</span><span class="sxs-lookup"><span data-stu-id="5d384-181">If you're monitoring power consumption, you’d want to know: Is there an outage?</span></span>

<span data-ttu-id="5d384-182">Hay dos tipos de anomalías de series temporales que se pueden detectar:</span><span class="sxs-lookup"><span data-stu-id="5d384-182">There are two types of time series anomalies that can be detected:</span></span> 

* <span data-ttu-id="5d384-183">Los **picos** indican ráfagas temporales de comportamiento anómalo en el sistema.</span><span class="sxs-lookup"><span data-stu-id="5d384-183">**Spikes** indicate temporary bursts of anomalous behavior in the system.</span></span> 

* <span data-ttu-id="5d384-184">Los **puntos de cambio** indican el inicio de cambios persistentes con el tiempo en el sistema.</span><span class="sxs-lookup"><span data-stu-id="5d384-184">**Change points** indicate the beginning of persistent changes over time in the system.</span></span> 

<span data-ttu-id="5d384-185">En ML.NET, los algoritmos de la detección de picos de IID o de la detección de puntos de cambio de IID son adecuados para los [conjuntos de datos independientes y distribuidos de manera idéntica](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span><span class="sxs-lookup"><span data-stu-id="5d384-185">In ML.NET, The IID Spike Detection or IID Change point Detection algorithms are suited for [independent and identically distributed datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span></span> 

<span data-ttu-id="5d384-186">Analizará los mismos datos de ventas de productos para detectar los picos y los puntos de cambio.</span><span class="sxs-lookup"><span data-stu-id="5d384-186">You'll analyze the same product sales data to detect spikes and change points.</span></span> <span data-ttu-id="5d384-187">El proceso de modelo de entrenamiento y compilación es el mismo para la detección de picos y la detección de puntos de cambio. La principal diferencia es el algoritmo de detección específico que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="5d384-187">The building and training model process is the same for spike detection and change point detection; the main difference is the specific detection algorithm used.</span></span>

## <a name="spike-detection"></a><span data-ttu-id="5d384-188">Detección de picos</span><span class="sxs-lookup"><span data-stu-id="5d384-188">Spike detection</span></span> 

<span data-ttu-id="5d384-189">El objetivo de la detección de picos es identificar ráfagas repentinas pero temporales que difieren significativamente de la mayoría de los valores de datos de las series temporales.</span><span class="sxs-lookup"><span data-stu-id="5d384-189">The goal of spike detection is to identify sudden yet temporary bursts that significantly differ from the majority of the time series data values.</span></span> <span data-ttu-id="5d384-190">Es importante detectar estos elementos, eventos u observaciones poco frecuentes y sospechosos de manera oportuna con el fin de minimizarlos.</span><span class="sxs-lookup"><span data-stu-id="5d384-190">It's important to detect these suspicious rare items, events or observations in a timely manner to be minimized.</span></span> <span data-ttu-id="5d384-191">El siguiente enfoque puede utilizarse para detectar una variedad de anomalías, como interrupciones, ciberataques o contenido web viral.</span><span class="sxs-lookup"><span data-stu-id="5d384-191">The following approach can be used to detect a variety of anomalies such as: outages, cyber-attacks, or viral web content.</span></span> <span data-ttu-id="5d384-192">La siguiente imagen es un ejemplo de los picos de un conjunto de datos de serie temporal:</span><span class="sxs-lookup"><span data-stu-id="5d384-192">The following image is an example of spikes in a time series dataset:</span></span>

![SpikeDetection](./media/sales-anomaly-detection/SpikeDetection.png)

### <a name="create-the-detectspike-method"></a><span data-ttu-id="5d384-194">Crear el método DetectSpike()</span><span class="sxs-lookup"><span data-stu-id="5d384-194">Create the DetectSpike() method</span></span>

<span data-ttu-id="5d384-195">Agregue la siguiente llamada al método `DetectSpike()` como siguiente línea de código del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="5d384-195">Add the following call to the `DetectSpike()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectSpike](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectSpike)]

<span data-ttu-id="5d384-196">El método `DetectSpike()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d384-196">The `DetectSpike()` method executes the following tasks:</span></span>

* <span data-ttu-id="5d384-197">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="5d384-197">Trains the model.</span></span>
* <span data-ttu-id="5d384-198">Detecta picos en función de los datos históricos de ventas.</span><span class="sxs-lookup"><span data-stu-id="5d384-198">Detects spikes based on on historical sales data.</span></span>
* <span data-ttu-id="5d384-199">Muestra los resultados.</span><span class="sxs-lookup"><span data-stu-id="5d384-199">Displays the results.</span></span>

<span data-ttu-id="5d384-200">Cree el método `DetectSpike()`, justo después del método `Main()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d384-200">Create the `DetectSpike()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="5d384-201">Use [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) para entrenar el modelo para la detección de picos.</span><span class="sxs-lookup"><span data-stu-id="5d384-201">Use the [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) to train the model for spike detection.</span></span> <span data-ttu-id="5d384-202">Agréguelo a un método `DetectChangepoint()` en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="5d384-202">Add it to the `DetectChangepoint()` method with the following code:</span></span>

[!code-csharp[AddSpikeTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddSpikeTrainer)]

<span data-ttu-id="5d384-203">Ajuste el modelo a los datos `productSales` y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="5d384-203">Fit the model to the `productSales` data and return the trained model by adding the following as the next line of code in the `DetectSpike()` method:</span></span>

[!code-csharp[TrainModel1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel1)]

<span data-ttu-id="5d384-204">El método [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) entrena el modelo transformando el conjunto de datos y aplicando el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="5d384-204">The [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="5d384-205">Agregue la siguiente línea de código para transformar los datos `productSales` como la siguiente línea en el método `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="5d384-205">Add the following line of code to transform the `productSales` data as the next line in the `DetectSpike()` method:</span></span>

[!code-csharp[TransformData1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData1)]

<span data-ttu-id="5d384-206">El código anterior usa el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) para realizar predicciones para varias filas de entrada de un conjunto de datos de prueba especificado.</span><span class="sxs-lookup"><span data-stu-id="5d384-206">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="5d384-207">Convierta su `transformedData` en `IEnumerable` fuertemente tipado para mostrar fácilmente mediante el método [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d384-207">Convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

[!code-csharp[CreateEnumerable1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable1)]

<span data-ttu-id="5d384-208">Cree una línea de encabezado de visualización mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d384-208">Create a display header line using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayHeader1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader1)]

<span data-ttu-id="5d384-209">Se mostrará la siguiente información en los resultados de detección de picos:</span><span class="sxs-lookup"><span data-stu-id="5d384-209">You'll display the following information in your spike detection results:</span></span>

* <span data-ttu-id="5d384-210">`Alert` indica una alerta de pico para determinado punto de datos.</span><span class="sxs-lookup"><span data-stu-id="5d384-210">`Alert` indicates a spike alert for a given data point.</span></span>

* <span data-ttu-id="5d384-211">`Score` es el valor `ProductSales` para determinado punto de datos en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="5d384-211">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>

* <span data-ttu-id="5d384-212">`P-Value` La "P" significa probabilidad.</span><span class="sxs-lookup"><span data-stu-id="5d384-212">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="5d384-213">Esto indica la probabilidad de que este punto de datos sea una anomalía.</span><span class="sxs-lookup"><span data-stu-id="5d384-213">This indicates how likely this data point is an anomaly.</span></span> 

<span data-ttu-id="5d384-214">Use el siguiente código para iterar en `predictions` `IEnumerable` y mostrar los resultados:</span><span class="sxs-lookup"><span data-stu-id="5d384-214">Use the following code to iterate through the `predictions` `IEnumerable` and display the results:</span></span>

[!code-csharp[DisplayResults1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults1)]

## <a name="spike-detection-results"></a><span data-ttu-id="5d384-215">Resultados de la detección de picos</span><span class="sxs-lookup"><span data-stu-id="5d384-215">Spike detection results</span></span>

<span data-ttu-id="5d384-216">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="5d384-216">Your results should be similar to the following.</span></span> <span data-ttu-id="5d384-217">Durante el procesamiento, se muestran mensajes.</span><span class="sxs-lookup"><span data-stu-id="5d384-217">During processing, messages are displayed.</span></span> <span data-ttu-id="5d384-218">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5d384-218">You may see warnings, or processing messages.</span></span> <span data-ttu-id="5d384-219">Se han quitado de los siguientes resultados para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="5d384-219">These have been removed from the following results for clarity.</span></span>

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

## <a name="change-point-detection"></a><span data-ttu-id="5d384-220">Detección de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="5d384-220">Change point detection</span></span>

<span data-ttu-id="5d384-221">`Change points` son cambios permanentes en una distribución de valores de secuencia de eventos de serie temporal, como los cambios de nivel y las tendencias.</span><span class="sxs-lookup"><span data-stu-id="5d384-221">`Change points` are persistent changes in a time series event stream distribution of values, like level changes and trends.</span></span> <span data-ttu-id="5d384-222">Estos cambios persistentes duran mucho más tiempo que `spikes` y podrían indicar eventos catastróficos.</span><span class="sxs-lookup"><span data-stu-id="5d384-222">These persistent changes last much longer than `spikes` and could indicate catastrophic event(s).</span></span> <span data-ttu-id="5d384-223">`Change points` no son normalmente visibles a simple vista, pero se pueden detectar en los datos mediante enfoques como el del siguiente método.</span><span class="sxs-lookup"><span data-stu-id="5d384-223">`Change points` are not usually visible to the naked eye, but can be detected in your data using approaches such as in the following method.</span></span>  <span data-ttu-id="5d384-224">La siguiente imagen es un ejemplo de una detección de puntos de cambio:</span><span class="sxs-lookup"><span data-stu-id="5d384-224">The following image is an example of a change point detection:</span></span>

![ChangePointDetection](./media/sales-anomaly-detection/ChangePointDetection.png)

### <a name="create-the-detectchangepoint-method"></a><span data-ttu-id="5d384-226">Crear el método DetectChangepoint()</span><span class="sxs-lookup"><span data-stu-id="5d384-226">Create the DetectChangepoint() method</span></span>

<span data-ttu-id="5d384-227">Agregue la siguiente llamada al método `DetectChangepoint()` como siguiente línea de código del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="5d384-227">Add the following call to the `DetectChangepoint()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectChangepoint](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectChangepoint)]

<span data-ttu-id="5d384-228">El método `DetectChangepoint()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d384-228">The `DetectChangepoint()` method executes the following tasks:</span></span>

* <span data-ttu-id="5d384-229">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="5d384-229">Trains the model.</span></span>
* <span data-ttu-id="5d384-230">Detecta puntos de cambio en función de los datos históricos de ventas.</span><span class="sxs-lookup"><span data-stu-id="5d384-230">Detects change points based on historical sales data.</span></span>
* <span data-ttu-id="5d384-231">Muestra los resultados.</span><span class="sxs-lookup"><span data-stu-id="5d384-231">Displays the results.</span></span>

<span data-ttu-id="5d384-232">Cree el método `DetectChangepoint()`, justo después del método `Main()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d384-232">Create the `DetectChangepoint()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="5d384-233">[iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) se usa para entrenar el modelo para la detección de puntos de cambio.</span><span class="sxs-lookup"><span data-stu-id="5d384-233">The [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) is used to train the model for change point detection.</span></span> <span data-ttu-id="5d384-234">Agréguelo a un método `DetectChangepoint()` en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="5d384-234">Add it to the `DetectChangepoint()` method with the following code:</span></span>

[!code-csharp[AddChangepointTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddChangepointTrainer)]

<span data-ttu-id="5d384-235">Como lo hizo anteriormente, ajuste el modelo a los datos `productSales` y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="5d384-235">As you did previously, fit the model to the `productSales` data and return the trained model by adding the following as the next line of code in the `DetectChangePoint()` method:</span></span>

[!code-csharp[TrainModel2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel2)]

<span data-ttu-id="5d384-236">Use el método `Transform()` para transformar los datos de `Training` mediante la adición del código siguiente a `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="5d384-236">Use the `Transform()` method to transform the `Training` data by adding the following code to `DetectChangePoint()`:</span></span>

[!code-csharp[TransformData2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData2)]

<span data-ttu-id="5d384-237">Como lo hizo anteriormente, convierta su `transformedData` en `IEnumerable` fuertemente tipado para mostrar fácilmente mediante el método `CreateEnumerable()` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d384-237">As you did previously, convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the `CreateEnumerable()`method with the following code:</span></span>

[!code-csharp[CreateEnumerable2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable2)]

<span data-ttu-id="5d384-238">Cree un encabezado de visualización con el siguiente código como la siguiente línea en el método `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="5d384-238">Create a display header with the following code as the next line in the `DetectChangePoint()` method:</span></span>

[!code-csharp[DisplayHeader2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader2)]

<span data-ttu-id="5d384-239">Se mostrará la siguiente información en los resultados de detección de puntos de cambio:</span><span class="sxs-lookup"><span data-stu-id="5d384-239">You'll display the following information in your change point detection results:</span></span>

* <span data-ttu-id="5d384-240">`Alert` indica una alerta de punto de cambio para determinado punto de datos.</span><span class="sxs-lookup"><span data-stu-id="5d384-240">`Alert` indicates a change point alert for a given data point.</span></span>
* <span data-ttu-id="5d384-241">`Score` es el valor `ProductSales` para determinado punto de datos en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="5d384-241">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
* <span data-ttu-id="5d384-242">`P-Value` La "P" significa probabilidad.</span><span class="sxs-lookup"><span data-stu-id="5d384-242">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="5d384-243">Esto indica la probabilidad de que este punto de datos sea una anomalía.</span><span class="sxs-lookup"><span data-stu-id="5d384-243">This indicates how likely this data point is an anomaly.</span></span> 
* <span data-ttu-id="5d384-244">`Martingale value` se usa para identificar cuán "extraño" es un punto de datos, en función de la secuencia de valores de P.</span><span class="sxs-lookup"><span data-stu-id="5d384-244">`Martingale value` is used to identify how "weird" a data point is, based on the sequence of P-values.</span></span>  

<span data-ttu-id="5d384-245">Itere en `predictions` `IEnumerable` y muestre los resultados con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="5d384-245">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

[!code-csharp[DisplayResults2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults2)]

## <a name="change-point-detection-results"></a><span data-ttu-id="5d384-246">Resultados de la detección de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="5d384-246">Change point detection results</span></span>

<span data-ttu-id="5d384-247">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="5d384-247">Your results should be similar to the following.</span></span> <span data-ttu-id="5d384-248">Durante el procesamiento, se muestran mensajes.</span><span class="sxs-lookup"><span data-stu-id="5d384-248">During processing, messages are displayed.</span></span> <span data-ttu-id="5d384-249">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5d384-249">You may see warnings, or processing messages.</span></span> <span data-ttu-id="5d384-250">Se han quitado de los siguientes resultados para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="5d384-250">These have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="5d384-251">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="5d384-251">Congratulations!</span></span> <span data-ttu-id="5d384-252">Ya ha creado correctamente los modelos de aprendizaje automático para detectar anomalías de picos y puntos de cambio en los datos de ventas.</span><span class="sxs-lookup"><span data-stu-id="5d384-252">You've now successfully built machine learning models for detecting spikes and change point anomalies in sales data.</span></span>

<span data-ttu-id="5d384-253">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="5d384-253">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

<span data-ttu-id="5d384-254">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="5d384-254">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5d384-255">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="5d384-255">Load the data</span></span>
> * <span data-ttu-id="5d384-256">Entrenar el modelo para la detección de anomalías de picos</span><span class="sxs-lookup"><span data-stu-id="5d384-256">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="5d384-257">Detectar anomalías de picos con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="5d384-257">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="5d384-258">Entrenar el modelo para la detección de anomalías de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="5d384-258">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="5d384-259">Detectar anomalías de puntos de cambio con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="5d384-259">Detect change point anomalies with the trained mode</span></span>

## <a name="next-steps"></a><span data-ttu-id="5d384-260">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5d384-260">Next steps</span></span>

<span data-ttu-id="5d384-261">Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo de detección de anomalías de consumo de energía.</span><span class="sxs-lookup"><span data-stu-id="5d384-261">Check out the Machine Learning samples GitHub repository to explore a Power Consumption Anomaly Detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="5d384-262">Repositorio dotnet/machinelearning-samples de GitHub</span><span class="sxs-lookup"><span data-stu-id="5d384-262">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/TimeSeries_PowerAnomalyDetection)

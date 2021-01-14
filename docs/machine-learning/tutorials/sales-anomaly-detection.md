---
title: 'Tutorial: Detección de anomalías en las ventas de productos'
description: Aprenda a crear una aplicación de detección de anomalías para los datos de ventas de productos. En este tutorial se va a crear una aplicación de consola de .NET Core mediante C# en Visual Studio 2019.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 48a8b26409b20e2a01aa97425153336b34c9b5b7
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97594181"
---
# <a name="tutorial-detect-anomalies-in-product-sales-with-mlnet"></a><span data-ttu-id="4f17f-104">Tutorial: Detección de anomalías en ventas de productos con ML.NET</span><span class="sxs-lookup"><span data-stu-id="4f17f-104">Tutorial: Detect anomalies in product sales with ML.NET</span></span>

<span data-ttu-id="4f17f-105">Aprenda a crear una aplicación de detección de anomalías para los datos de ventas de productos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-105">Learn how to build an anomaly detection application for product sales data.</span></span> <span data-ttu-id="4f17f-106">En este tutorial se va a crear una aplicación de consola de .NET Core mediante C# en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4f17f-106">This tutorial creates a .NET Core console application using C# in Visual Studio.</span></span>

<span data-ttu-id="4f17f-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="4f17f-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="4f17f-108">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="4f17f-108">Load the data</span></span>
> * <span data-ttu-id="4f17f-109">Crear una transformación para la detección de anomalías de picos</span><span class="sxs-lookup"><span data-stu-id="4f17f-109">Create a transform for spike anomaly detection</span></span>
> * <span data-ttu-id="4f17f-110">Detectar anomalías de picos con la transformación</span><span class="sxs-lookup"><span data-stu-id="4f17f-110">Detect spike anomalies with the transform</span></span>
> * <span data-ttu-id="4f17f-111">Crear una transformación para la detección de anomalías de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="4f17f-111">Create a transform for change point anomaly detection</span></span>
> * <span data-ttu-id="4f17f-112">Detectar anomalías de puntos de cambio con la transformación</span><span class="sxs-lookup"><span data-stu-id="4f17f-112">Detect change point anomalies with the transform</span></span>

<span data-ttu-id="4f17f-113">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="4f17f-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4f17f-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4f17f-114">Prerequisites</span></span>

* <span data-ttu-id="4f17f-115">[Visual Studio 2017, versión 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="4f17f-115">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="4f17f-116">El conjunto de datos product-sales.csv</span><span class="sxs-lookup"><span data-stu-id="4f17f-116">The product-sales.csv dataset</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> <span data-ttu-id="4f17f-117">El formato de datos en `product-sales.csv` se basa en el conjunto de datos "Shampoo Sales Over a Three Year Period" (Ventas de champú en un período de tres años) procedente originalmente de DataMarket y proporcionado por Time Series Data Library (TSDL), creado por Rob Hyndman.</span><span class="sxs-lookup"><span data-stu-id="4f17f-117">The data format in `product-sales.csv` is based on the dataset “Shampoo Sales Over a Three Year Period” originally sourced from DataMarket and provided by Time Series Data Library (TSDL), created by Rob Hyndman.</span></span>
> <span data-ttu-id="4f17f-118">Conjunto de datos "Shampoo Sales Over a Three Year Period" con una licencia de conjunto de datos que se concede de acuerdo con DataMarket Default Open License.</span><span class="sxs-lookup"><span data-stu-id="4f17f-118">“Shampoo Sales Over a Three Year Period” Dataset Licensed Under the DataMarket Default Open License.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="4f17f-119">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="4f17f-119">Create a console application</span></span>

1. <span data-ttu-id="4f17f-120">Cree una **aplicación de consola de .NET Core** denominada "ProductSalesAnomalyDetection".</span><span class="sxs-lookup"><span data-stu-id="4f17f-120">Create a **.NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="4f17f-121">Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="4f17f-122">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="4f17f-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="4f17f-123">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="4f17f-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="4f17f-124">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML** y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="4f17f-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML** and select the **Install** button.</span></span> <span data-ttu-id="4f17f-125">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="4f17f-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="4f17f-126">Repita estos pasos para **Microsoft.ML.TimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="4f17f-126">Repeat these steps for **Microsoft.ML.TimeSeries**.</span></span>

4. <span data-ttu-id="4f17f-127">Agregue las instrucciones `using` siguientes en la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="4f17f-127">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](./snippets/sales-anomaly-detection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="4f17f-128">Descarga de los datos</span><span class="sxs-lookup"><span data-stu-id="4f17f-128">Download your data</span></span>

1. <span data-ttu-id="4f17f-129">Descargue el conjunto de datos y guárdelo en la carpeta *Datos* que creó anteriormente:</span><span class="sxs-lookup"><span data-stu-id="4f17f-129">Download the dataset and save it to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="4f17f-130">Haga clic con el botón derecho en [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) y seleccione "Guardar vínculo (o destino) como...".</span><span class="sxs-lookup"><span data-stu-id="4f17f-130">Right click on [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="4f17f-131">Asegúrese de que guarda el archivo \*.csv en la carpeta *Datos* o, después de guardarlo en otro lugar, mueva el archivo \*.csv a la carpeta *Datos*.</span><span class="sxs-lookup"><span data-stu-id="4f17f-131">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="4f17f-132">En el Explorador de soluciones, haga clic con el botón derecho en el archivo \*.csv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4f17f-132">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="4f17f-133">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="4f17f-133">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="4f17f-134">La siguiente tabla es una vista previa de datos del archivo \*.csv:</span><span class="sxs-lookup"><span data-stu-id="4f17f-134">The following table is a data preview from your \*.csv file:</span></span>

|<span data-ttu-id="4f17f-135">Mes</span><span class="sxs-lookup"><span data-stu-id="4f17f-135">Month</span></span>  |<span data-ttu-id="4f17f-136">ProductSales</span><span class="sxs-lookup"><span data-stu-id="4f17f-136">ProductSales</span></span> |
|-------|-------------|
|<span data-ttu-id="4f17f-137">1 - Ene</span><span class="sxs-lookup"><span data-stu-id="4f17f-137">1-Jan</span></span>  |    <span data-ttu-id="4f17f-138">271</span><span class="sxs-lookup"><span data-stu-id="4f17f-138">271</span></span>      |
|<span data-ttu-id="4f17f-139">2 - Ene</span><span class="sxs-lookup"><span data-stu-id="4f17f-139">2-Jan</span></span>  |    <span data-ttu-id="4f17f-140">150,9</span><span class="sxs-lookup"><span data-stu-id="4f17f-140">150.9</span></span>    |
|<span data-ttu-id="4f17f-141">.....</span><span class="sxs-lookup"><span data-stu-id="4f17f-141">.....</span></span>  |    <span data-ttu-id="4f17f-142">.....</span><span class="sxs-lookup"><span data-stu-id="4f17f-142">.....</span></span>    |
|<span data-ttu-id="4f17f-143">1 - Feb</span><span class="sxs-lookup"><span data-stu-id="4f17f-143">1-Feb</span></span>  |    <span data-ttu-id="4f17f-144">199,3</span><span class="sxs-lookup"><span data-stu-id="4f17f-144">199.3</span></span>    |
|<span data-ttu-id="4f17f-145">.....</span><span class="sxs-lookup"><span data-stu-id="4f17f-145">.....</span></span>  |    <span data-ttu-id="4f17f-146">.....</span><span class="sxs-lookup"><span data-stu-id="4f17f-146">.....</span></span>    |

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="4f17f-147">Crear clases y definir rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="4f17f-147">Create classes and define paths</span></span>

<span data-ttu-id="4f17f-148">A continuación, defina las estructuras de datos de la clase de entrada y de predicción.</span><span class="sxs-lookup"><span data-stu-id="4f17f-148">Next, define your input and prediction class data structures.</span></span>

<span data-ttu-id="4f17f-149">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="4f17f-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="4f17f-150">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="4f17f-150">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="4f17f-151">En el **cuadro de diálogo Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ProductSalesData.cs*.</span><span class="sxs-lookup"><span data-stu-id="4f17f-151">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *ProductSalesData.cs*.</span></span> <span data-ttu-id="4f17f-152">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4f17f-152">Then, select the **Add** button.</span></span>

   <span data-ttu-id="4f17f-153">El archivo *ProductSalesData.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="4f17f-153">The *ProductSalesData.cs* file opens in the code editor.</span></span>

3. <span data-ttu-id="4f17f-154">Agregue la siguiente instrucción `using` al principio de *ProductSalesData.cs*:</span><span class="sxs-lookup"><span data-stu-id="4f17f-154">Add the following `using` statement to the top of *ProductSalesData.cs*:</span></span>

   ```csharp
   using Microsoft.ML.Data;
   ```

4. <span data-ttu-id="4f17f-155">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases, `ProductSalesData` y `ProductSalesPrediction`, al archivo *ProductSalesData.cs*:</span><span class="sxs-lookup"><span data-stu-id="4f17f-155">Remove the existing class definition and add the following code, which has two classes `ProductSalesData` and `ProductSalesPrediction`, to the *ProductSalesData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](./snippets/sales-anomaly-detection/csharp/ProductSalesData.cs#DeclareTypes "Declare data record types")]

    <span data-ttu-id="4f17f-156">`ProductSalesData` especifica una clase de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="4f17f-156">`ProductSalesData` specifies an input data class.</span></span> <span data-ttu-id="4f17f-157">El atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) especifica qué columnas (por índice de columna) del conjunto de datos se deben cargar.</span><span class="sxs-lookup"><span data-stu-id="4f17f-157">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span>

    <span data-ttu-id="4f17f-158">`ProductSalesPrediction` especifica la clase de datos de predicción.</span><span class="sxs-lookup"><span data-stu-id="4f17f-158">`ProductSalesPrediction` specifies the prediction data class.</span></span> <span data-ttu-id="4f17f-159">En la detección de anomalías, la predicción consiste en una alerta que indica si hay una anomalía, una puntuación sin procesar y un valor p.</span><span class="sxs-lookup"><span data-stu-id="4f17f-159">For anomaly detection, the prediction consists of an alert to indicate whether there is an anomaly, a raw score, and p-value.</span></span> <span data-ttu-id="4f17f-160">Cuanto más se acerque el valor p a 0, más probable es que se haya producido una anomalía.</span><span class="sxs-lookup"><span data-stu-id="4f17f-160">The closer the p-value is to 0, the more likely an anomaly has occurred.</span></span>

5. <span data-ttu-id="4f17f-161">Cree dos campos globales para contener la ruta de acceso del archivo de conjunto de datos recientemente descargado y la ruta de acceso del archivo de modelo guardado:</span><span class="sxs-lookup"><span data-stu-id="4f17f-161">Create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

    * <span data-ttu-id="4f17f-162">`_dataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="4f17f-162">`_dataPath` has the path to the dataset used to train the model.</span></span>
    * <span data-ttu-id="4f17f-163">`_docsize` tiene el número de registros en el archivo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-163">`_docsize` has the number of records in dataset file.</span></span> <span data-ttu-id="4f17f-164">Usará `_docSize` para calcular `pvalueHistoryLength`.</span><span class="sxs-lookup"><span data-stu-id="4f17f-164">You'll use `_docSize` to calculate `pvalueHistoryLength`.</span></span>

6. <span data-ttu-id="4f17f-165">Agregue el código siguiente a la línea justo encima del método `Main` para especificar las rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="4f17f-165">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

    [!code-csharp[Declare global variables](./snippets/sales-anomaly-detection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a><span data-ttu-id="4f17f-166">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="4f17f-166">Initialize variables in Main</span></span>

1. <span data-ttu-id="4f17f-167">Reemplace la línea `Console.WriteLine("Hello World!")` del método `Main` por el siguiente código para declarar e inicializar la variable `mlContext`:</span><span class="sxs-lookup"><span data-stu-id="4f17f-167">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

    [!code-csharp[CreateMLContext](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    <span data-ttu-id="4f17f-168">La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-168">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="4f17f-169">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="4f17f-169">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="load-the-data"></a><span data-ttu-id="4f17f-170">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="4f17f-170">Load the data</span></span>

<span data-ttu-id="4f17f-171">Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="4f17f-171">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="4f17f-172">`IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto).</span><span class="sxs-lookup"><span data-stu-id="4f17f-172">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="4f17f-173">Los datos se pueden cargar desde un archivo de texto o u otros orígenes (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="4f17f-173">Data can be loaded from a text file or from other sources (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="4f17f-174">Agregue el siguiente código como la siguiente línea del método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="4f17f-174">Add the following code as the next line of the `Main()` method:</span></span>

    [!code-csharp[LoadData](./snippets/sales-anomaly-detection/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="4f17f-175">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo.</span><span class="sxs-lookup"><span data-stu-id="4f17f-175">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="4f17f-176">Toma las variables de ruta de acceso de datos y devuelve `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="4f17f-176">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="time-series-anomaly-detection"></a><span data-ttu-id="4f17f-177">Detección de anomalías en una serie temporal</span><span class="sxs-lookup"><span data-stu-id="4f17f-177">Time series anomaly detection</span></span>

<span data-ttu-id="4f17f-178">La detección de anomalías marca comportamientos o eventos inesperados o poco habituales.</span><span class="sxs-lookup"><span data-stu-id="4f17f-178">Anomaly detection flags unexpected or unusual events or behaviors.</span></span> <span data-ttu-id="4f17f-179">Proporciona pistas sobre dónde buscar problemas y ayuda a responder la pregunta "¿es extraño esto?".</span><span class="sxs-lookup"><span data-stu-id="4f17f-179">It gives clues where to look for problems and helps you answer the question "Is this weird?".</span></span>

![Ejemplo de la detección de anomalías "Es extraño esto".](./media/sales-anomaly-detection/time-series-anomaly-detection.png)

<span data-ttu-id="4f17f-181">La detección de anomalías es el proceso de detectar valores atípicos de datos de series temporales, puntos en determinada serie temporal de entrada donde el comportamiento no es lo que se esperaba o es "extraño".</span><span class="sxs-lookup"><span data-stu-id="4f17f-181">Anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span>

<span data-ttu-id="4f17f-182">La detección de anomalías puede ser útil de muchas maneras.</span><span class="sxs-lookup"><span data-stu-id="4f17f-182">Anomaly detection can be useful in lots of ways.</span></span> <span data-ttu-id="4f17f-183">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4f17f-183">For instance:</span></span>

<span data-ttu-id="4f17f-184">Si tiene un automóvil, tal vez desee saber: ¿Es normal la lectura del medidor de gasolina o tengo una fuga?</span><span class="sxs-lookup"><span data-stu-id="4f17f-184">If you have a car, you might want to know: Is this oil gauge reading normal, or do I have a leak?</span></span>
<span data-ttu-id="4f17f-185">Si está supervisando el consumo de energía, desearía saber: ¿Hay una interrupción?</span><span class="sxs-lookup"><span data-stu-id="4f17f-185">If you're monitoring power consumption, you’d want to know: Is there an outage?</span></span>

<span data-ttu-id="4f17f-186">Hay dos tipos de anomalías de series temporales que se pueden detectar:</span><span class="sxs-lookup"><span data-stu-id="4f17f-186">There are two types of time series anomalies that can be detected:</span></span>

* <span data-ttu-id="4f17f-187">Los **picos** indican ráfagas temporales de comportamiento anómalo en el sistema.</span><span class="sxs-lookup"><span data-stu-id="4f17f-187">**Spikes** indicate temporary bursts of anomalous behavior in the system.</span></span>

* <span data-ttu-id="4f17f-188">Los **puntos de cambio** indican el inicio de cambios persistentes con el tiempo en el sistema.</span><span class="sxs-lookup"><span data-stu-id="4f17f-188">**Change points** indicate the beginning of persistent changes over time in the system.</span></span>

<span data-ttu-id="4f17f-189">En ML.NET, los algoritmos de la detección de picos de IID o de la detección de puntos de cambio de IID son adecuados para los [conjuntos de datos independientes y distribuidos de manera idéntica](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span><span class="sxs-lookup"><span data-stu-id="4f17f-189">In ML.NET, The IID Spike Detection or IID Change point Detection algorithms are suited for [independent and identically distributed datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span></span>

<span data-ttu-id="4f17f-190">A diferencia de los modelos de los otros tutoriales, las transformaciones del detector de anomalías de series temporales funcionan directamente en los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="4f17f-190">Unlike the models in the other tutorials, the time series anomaly detector transforms operate directly on input data.</span></span> <span data-ttu-id="4f17f-191">El método `IEstimator.Fit()` no necesita datos de entrenamiento para generar la transformación.</span><span class="sxs-lookup"><span data-stu-id="4f17f-191">The `IEstimator.Fit()` method does not need training data to produce the transform.</span></span> <span data-ttu-id="4f17f-192">Sin embargo, necesita el esquema de datos, que se proporciona mediante una vista de datos generada a partir de una lista vacía de `ProductSalesData`.</span><span class="sxs-lookup"><span data-stu-id="4f17f-192">It does need the data schema though, which is provided by a data view generated from an empty list of `ProductSalesData`.</span></span>

<span data-ttu-id="4f17f-193">Analizará los mismos datos de ventas de productos para detectar los picos y los puntos de cambio.</span><span class="sxs-lookup"><span data-stu-id="4f17f-193">You'll analyze the same product sales data to detect spikes and change points.</span></span> <span data-ttu-id="4f17f-194">El proceso de modelo de entrenamiento y compilación es el mismo para la detección de picos y la detección de puntos de cambio. La principal diferencia es el algoritmo de detección específico que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="4f17f-194">The building and training model process is the same for spike detection and change point detection; the main difference is the specific detection algorithm used.</span></span>

## <a name="spike-detection"></a><span data-ttu-id="4f17f-195">Detección de picos</span><span class="sxs-lookup"><span data-stu-id="4f17f-195">Spike detection</span></span>

<span data-ttu-id="4f17f-196">El objetivo de la detección de picos es identificar ráfagas repentinas pero temporales que difieren significativamente de la mayoría de los valores de datos de las series temporales.</span><span class="sxs-lookup"><span data-stu-id="4f17f-196">The goal of spike detection is to identify sudden yet temporary bursts that significantly differ from the majority of the time series data values.</span></span> <span data-ttu-id="4f17f-197">Es importante detectar estos elementos, eventos u observaciones poco frecuentes y sospechosos de manera oportuna con el fin de minimizarlos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-197">It's important to detect these suspicious rare items, events, or observations in a timely manner to be minimized.</span></span> <span data-ttu-id="4f17f-198">El siguiente enfoque puede utilizarse para detectar una variedad de anomalías, como interrupciones, ciberataques o contenido web viral.</span><span class="sxs-lookup"><span data-stu-id="4f17f-198">The following approach can be used to detect a variety of anomalies such as: outages, cyber-attacks, or viral web content.</span></span> <span data-ttu-id="4f17f-199">La siguiente imagen es un ejemplo de los picos de un conjunto de datos de serie temporal:</span><span class="sxs-lookup"><span data-stu-id="4f17f-199">The following image is an example of spikes in a time series dataset:</span></span>

![Captura de pantalla en la que se muestran dos detecciones de picos.](./media/sales-anomaly-detection/two-spike-detections.png)

### <a name="add-the-createemptydataview-method"></a><span data-ttu-id="4f17f-201">Agregar el método CreateEmptyDataView()</span><span class="sxs-lookup"><span data-stu-id="4f17f-201">Add the CreateEmptyDataView() method</span></span>

<span data-ttu-id="4f17f-202">Agregue el método siguiente a `Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="4f17f-202">Add the following method to `Program.cs`:</span></span>

[!code-csharp[CreateEmptyDataView](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateEmptyDataView)]

<span data-ttu-id="4f17f-203">`CreateEmptyDataView()` genera un objeto de vista de datos vacío con el esquema correcto que se va a usar como entrada para el método `IEstimator.Fit()`.</span><span class="sxs-lookup"><span data-stu-id="4f17f-203">The `CreateEmptyDataView()` produces an empty data view object with the correct schema to be used as input to the `IEstimator.Fit()` method.</span></span>

### <a name="create-the-detectspike-method"></a><span data-ttu-id="4f17f-204">Crear el método DetectSpike()</span><span class="sxs-lookup"><span data-stu-id="4f17f-204">Create the DetectSpike() method</span></span>

<span data-ttu-id="4f17f-205">El método `DetectSpike()` realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4f17f-205">The `DetectSpike()` method:</span></span>

* <span data-ttu-id="4f17f-206">Crea la transformación desde el estimador.</span><span class="sxs-lookup"><span data-stu-id="4f17f-206">Creates the transform from the estimator.</span></span>
* <span data-ttu-id="4f17f-207">Detecta picos en función de los datos históricos de ventas.</span><span class="sxs-lookup"><span data-stu-id="4f17f-207">Detects spikes based on historical sales data.</span></span>
* <span data-ttu-id="4f17f-208">Muestra los resultados.</span><span class="sxs-lookup"><span data-stu-id="4f17f-208">Displays the results.</span></span>

1. <span data-ttu-id="4f17f-209">Cree el método `DetectSpike()`, justo después del método `Main()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f17f-209">Create the `DetectSpike()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. <span data-ttu-id="4f17f-210">Use [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) para entrenar el modelo para la detección de picos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-210">Use the [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) to train the model for spike detection.</span></span> <span data-ttu-id="4f17f-211">Agréguelo a un método `DetectSpike()` en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="4f17f-211">Add it to the `DetectSpike()` method with the following code:</span></span>

    [!code-csharp[AddSpikeTrainer](./snippets/sales-anomaly-detection/csharp/Program.cs#AddSpikeTrainer)]

1. <span data-ttu-id="4f17f-212">Para crear la transformación de detección de picos, agregue lo que se indica a continuación como la siguiente línea de código en el método `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="4f17f-212">Create the spike detection transform by adding the following as the next line of code in the `DetectSpike()` method:</span></span>

    [!code-csharp[TrainModel1](./snippets/sales-anomaly-detection/csharp/Program.cs#TrainModel1)]

1. <span data-ttu-id="4f17f-213">Agregue la siguiente línea de código para transformar los datos `productSales` como la siguiente línea en el método `DetectSpike()`:</span><span class="sxs-lookup"><span data-stu-id="4f17f-213">Add the following line of code to transform the `productSales` data as the next line in the `DetectSpike()` method:</span></span>

    [!code-csharp[TransformData1](./snippets/sales-anomaly-detection/csharp/Program.cs#TransformData1)]

    <span data-ttu-id="4f17f-214">El código anterior usa el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) para hacer predicciones para varias filas de entrada de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-214">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple input rows of a dataset.</span></span>

1. <span data-ttu-id="4f17f-215">Convierta `transformedData` en `IEnumerable` fuertemente tipado para mostrar fácilmente mediante el método [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) con este código:</span><span class="sxs-lookup"><span data-stu-id="4f17f-215">Convert your `transformedData` into a strongly typed `IEnumerable` for easier display using the [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

    [!code-csharp[CreateEnumerable1](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateEnumerable1)]

1. <span data-ttu-id="4f17f-216">Cree una línea de encabezado de visualización mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f17f-216">Create a display header line using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

    [!code-csharp[DisplayHeader1](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayHeader1)]

    <span data-ttu-id="4f17f-217">Se mostrará la siguiente información en los resultados de detección de picos:</span><span class="sxs-lookup"><span data-stu-id="4f17f-217">You'll display the following information in your spike detection results:</span></span>

    * <span data-ttu-id="4f17f-218">`Alert` indica una alerta de pico para determinado punto de datos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-218">`Alert` indicates a spike alert for a given data point.</span></span>
    * <span data-ttu-id="4f17f-219">`Score` es el valor `ProductSales` para determinado punto de datos en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-219">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
    * <span data-ttu-id="4f17f-220">`P-Value` La "P" significa probabilidad.</span><span class="sxs-lookup"><span data-stu-id="4f17f-220">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="4f17f-221">Cuanto más se acerque el valor p a 0, más probable es que el punto de datos sea una anomalía.</span><span class="sxs-lookup"><span data-stu-id="4f17f-221">The closer the p-value is to 0, the more likely the data point is an anomaly.</span></span>

1. <span data-ttu-id="4f17f-222">Use el siguiente código para iterar en `predictions` `IEnumerable` y mostrar los resultados:</span><span class="sxs-lookup"><span data-stu-id="4f17f-222">Use the following code to iterate through the `predictions` `IEnumerable` and display the results:</span></span>

    [!code-csharp[DisplayResults1](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayResults1)]

1. <span data-ttu-id="4f17f-223">Agregue la llamada al método `DetectSpike()` en el método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="4f17f-223">Add the call to the `DetectSpike()`method in the `Main()` method:</span></span>

    [!code-csharp[CallDetectSpike](./snippets/sales-anomaly-detection/csharp/Program.cs#CallDetectSpike)]

## <a name="spike-detection-results"></a><span data-ttu-id="4f17f-224">Resultados de la detección de picos</span><span class="sxs-lookup"><span data-stu-id="4f17f-224">Spike detection results</span></span>

<span data-ttu-id="4f17f-225">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="4f17f-225">Your results should be similar to the following.</span></span> <span data-ttu-id="4f17f-226">Durante el procesamiento, se muestran mensajes.</span><span class="sxs-lookup"><span data-stu-id="4f17f-226">During processing, messages are displayed.</span></span> <span data-ttu-id="4f17f-227">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4f17f-227">You may see warnings, or processing messages.</span></span> <span data-ttu-id="4f17f-228">Algunos de los mensajes se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="4f17f-228">Some of the messages have been removed from the following results for clarity.</span></span>

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

## <a name="change-point-detection"></a><span data-ttu-id="4f17f-229">Detección de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="4f17f-229">Change point detection</span></span>

<span data-ttu-id="4f17f-230">`Change points` son cambios permanentes en una distribución de valores de secuencia de eventos de serie temporal, como los cambios de nivel y las tendencias.</span><span class="sxs-lookup"><span data-stu-id="4f17f-230">`Change points` are persistent changes in a time series event stream distribution of values, like level changes and trends.</span></span> <span data-ttu-id="4f17f-231">Estos cambios persistentes duran mucho más tiempo que `spikes` y podrían indicar eventos catastróficos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-231">These persistent changes last much longer than `spikes` and could indicate catastrophic event(s).</span></span> <span data-ttu-id="4f17f-232">`Change points` no son normalmente visibles a simple vista, pero se pueden detectar en los datos mediante enfoques como el del siguiente método.</span><span class="sxs-lookup"><span data-stu-id="4f17f-232">`Change points` are not usually visible to the naked eye, but can be detected in your data using approaches such as in the following method.</span></span>  <span data-ttu-id="4f17f-233">La siguiente imagen es un ejemplo de una detección de puntos de cambio:</span><span class="sxs-lookup"><span data-stu-id="4f17f-233">The following image is an example of a change point detection:</span></span>

![Captura de pantalla en la que se muestra una detección de puntos de cambio.](./media/sales-anomaly-detection/change-point-detection.png)

### <a name="create-the-detectchangepoint-method"></a><span data-ttu-id="4f17f-235">Crear el método DetectChangepoint()</span><span class="sxs-lookup"><span data-stu-id="4f17f-235">Create the DetectChangepoint() method</span></span>

<span data-ttu-id="4f17f-236">El método `DetectChangepoint()` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4f17f-236">The `DetectChangepoint()` method executes the following tasks:</span></span>

* <span data-ttu-id="4f17f-237">Crea la transformación desde el estimador.</span><span class="sxs-lookup"><span data-stu-id="4f17f-237">Creates the transform from the estimator.</span></span>
* <span data-ttu-id="4f17f-238">Detecta puntos de cambio en función de los datos históricos de ventas.</span><span class="sxs-lookup"><span data-stu-id="4f17f-238">Detects change points based on historical sales data.</span></span>
* <span data-ttu-id="4f17f-239">Muestra los resultados.</span><span class="sxs-lookup"><span data-stu-id="4f17f-239">Displays the results.</span></span>

1. <span data-ttu-id="4f17f-240">Cree el método `DetectChangepoint()`, justo después del método `Main()`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f17f-240">Create the `DetectChangepoint()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. <span data-ttu-id="4f17f-241">Cree [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) en el método `DetectChangepoint()` con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f17f-241">Create the [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) in the `DetectChangepoint()` method with the following code:</span></span>

    [!code-csharp[AddChangepointTrainer](./snippets/sales-anomaly-detection/csharp/Program.cs#AddChangepointTrainer)]

1. <span data-ttu-id="4f17f-242">Como hizo anteriormente, cree la transformación desde el estimador agregando la siguiente línea de código en el método `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="4f17f-242">As you did previously, create the transform from the estimator by adding the following line of code in the `DetectChangePoint()` method:</span></span>

    [!code-csharp[TrainModel2](./snippets/sales-anomaly-detection/csharp/Program.cs#TrainModel2)]

1. <span data-ttu-id="4f17f-243">Use el método `Transform()` para transformar los datos mediante la adición del código siguiente a `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="4f17f-243">Use the `Transform()` method to transform the data by adding the following code to `DetectChangePoint()`:</span></span>

    [!code-csharp[TransformData2](./snippets/sales-anomaly-detection/csharp/Program.cs#TransformData2)]

1. <span data-ttu-id="4f17f-244">Como hizo antes, convierta `transformedData` en `IEnumerable` fuertemente tipado para mostrar fácilmente mediante el método `CreateEnumerable()` con este código:</span><span class="sxs-lookup"><span data-stu-id="4f17f-244">As you did previously, convert your `transformedData` into a strongly typed `IEnumerable` for easier display using the `CreateEnumerable()`method with the following code:</span></span>

    [!code-csharp[CreateEnumerable2](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateEnumerable2)]

1. <span data-ttu-id="4f17f-245">Cree un encabezado de visualización con el siguiente código como la siguiente línea en el método `DetectChangePoint()`:</span><span class="sxs-lookup"><span data-stu-id="4f17f-245">Create a display header with the following code as the next line in the `DetectChangePoint()` method:</span></span>

    [!code-csharp[DisplayHeader2](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayHeader2)]

    <span data-ttu-id="4f17f-246">Se mostrará la siguiente información en los resultados de detección de puntos de cambio:</span><span class="sxs-lookup"><span data-stu-id="4f17f-246">You'll display the following information in your change point detection results:</span></span>

    * <span data-ttu-id="4f17f-247">`Alert` indica una alerta de punto de cambio para determinado punto de datos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-247">`Alert` indicates a change point alert for a given data point.</span></span>
    * <span data-ttu-id="4f17f-248">`Score` es el valor `ProductSales` para determinado punto de datos en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="4f17f-248">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
    * <span data-ttu-id="4f17f-249">`P-Value` La "P" significa probabilidad.</span><span class="sxs-lookup"><span data-stu-id="4f17f-249">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="4f17f-250">Cuanto más se acerque el valor P a 0, más probable es que el punto de datos sea una anomalía.</span><span class="sxs-lookup"><span data-stu-id="4f17f-250">The closer the P-value is to 0, the more likely the data point is an anomaly.</span></span>
    * <span data-ttu-id="4f17f-251">`Martingale value` se usa para identificar cuán "extraño" es un punto de datos, en función de la secuencia de valores de P.</span><span class="sxs-lookup"><span data-stu-id="4f17f-251">`Martingale value` is used to identify how "weird" a data point is, based on the sequence of P-values.</span></span>

1. <span data-ttu-id="4f17f-252">Itere en `predictions` `IEnumerable` y muestre los resultados con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="4f17f-252">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

    [!code-csharp[DisplayResults2](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayResults2)]

1. <span data-ttu-id="4f17f-253">Agregue la llamada siguiente al método `DetectChangepoint()` en el método `Main()`:</span><span class="sxs-lookup"><span data-stu-id="4f17f-253">Add the following call to the `DetectChangepoint()`method in the `Main()` method:</span></span>

    [!code-csharp[CallDetectChangepoint](./snippets/sales-anomaly-detection/csharp/Program.cs#CallDetectChangepoint)]

## <a name="change-point-detection-results"></a><span data-ttu-id="4f17f-254">Resultados de la detección de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="4f17f-254">Change point detection results</span></span>

<span data-ttu-id="4f17f-255">Los resultados deberían ser similares a los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="4f17f-255">Your results should be similar to the following.</span></span> <span data-ttu-id="4f17f-256">Durante el procesamiento, se muestran mensajes.</span><span class="sxs-lookup"><span data-stu-id="4f17f-256">During processing, messages are displayed.</span></span> <span data-ttu-id="4f17f-257">Puede ver las advertencias o mensajes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4f17f-257">You may see warnings, or processing messages.</span></span> <span data-ttu-id="4f17f-258">Algunos de los mensajes se han quitado de los resultados siguientes para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="4f17f-258">Some messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="4f17f-259">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="4f17f-259">Congratulations!</span></span> <span data-ttu-id="4f17f-260">Ya ha creado correctamente los modelos de aprendizaje automático para detectar anomalías de picos y puntos de cambio en los datos de ventas.</span><span class="sxs-lookup"><span data-stu-id="4f17f-260">You've now successfully built machine learning models for detecting spikes and change point anomalies in sales data.</span></span>

<span data-ttu-id="4f17f-261">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).</span><span class="sxs-lookup"><span data-stu-id="4f17f-261">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

<span data-ttu-id="4f17f-262">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="4f17f-262">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="4f17f-263">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="4f17f-263">Load the data</span></span>
> * <span data-ttu-id="4f17f-264">Entrenar el modelo para la detección de anomalías de picos</span><span class="sxs-lookup"><span data-stu-id="4f17f-264">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="4f17f-265">Detectar anomalías de picos con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="4f17f-265">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="4f17f-266">Entrenar el modelo para la detección de anomalías de puntos de cambio</span><span class="sxs-lookup"><span data-stu-id="4f17f-266">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="4f17f-267">Detectar anomalías de puntos de cambio con el modelo entrenado</span><span class="sxs-lookup"><span data-stu-id="4f17f-267">Detect change point anomalies with the trained mode</span></span>

## <a name="next-steps"></a><span data-ttu-id="4f17f-268">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4f17f-268">Next steps</span></span>

<span data-ttu-id="4f17f-269">Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo de detección de anomalías de datos de estacionalidad.</span><span class="sxs-lookup"><span data-stu-id="4f17f-269">Check out the Machine Learning samples GitHub repository to explore a seasonality data anomaly detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="4f17f-270">Repositorio dotnet/machinelearning-samples de GitHub</span><span class="sxs-lookup"><span data-stu-id="4f17f-270">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls)

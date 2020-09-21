---
title: 'Tutorial: Previsión de la demanda de alquiler de bicicletas: serie temporal'
description: En este tutorial se muestra cómo prever la demanda de un servicio de alquiler de bicicletas mediante el análisis de serie temporal de variable única y ML.NET.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 51041f5a9076ad360a84cc39704aedb50b77d40a
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679395"
---
# <a name="tutorial-forecast-bike-rental-service-demand-with-time-series-analysis-and-mlnet"></a><span data-ttu-id="9d54f-103">Tutorial: Previsión de la demanda de servicio de alquiler de bicicletas con análisis de serie temporal y ML.NET</span><span class="sxs-lookup"><span data-stu-id="9d54f-103">Tutorial: Forecast bike rental service demand with time series analysis and ML.NET</span></span>

<span data-ttu-id="9d54f-104">Obtenga información sobre cómo prever la demanda de un servicio de alquiler de bicicletas mediante el análisis de serie temporal de variable única en los datos almacenados en una base de datos SQL Server con ML.NET.</span><span class="sxs-lookup"><span data-stu-id="9d54f-104">Learn how to forecast demand for a bike rental service using univariate time series analysis on data stored in a SQL Server database with ML.NET.</span></span>

<span data-ttu-id="9d54f-105">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="9d54f-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="9d54f-106">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="9d54f-106">Understand the problem</span></span>
> * <span data-ttu-id="9d54f-107">Cargar datos desde una base de datos</span><span class="sxs-lookup"><span data-stu-id="9d54f-107">Load data from a database</span></span>
> * <span data-ttu-id="9d54f-108">Crear un modelo de previsión</span><span class="sxs-lookup"><span data-stu-id="9d54f-108">Create a forecasting model</span></span>
> * <span data-ttu-id="9d54f-109">Evaluar un modelo de previsión</span><span class="sxs-lookup"><span data-stu-id="9d54f-109">Evaluate forecasting model</span></span>
> * <span data-ttu-id="9d54f-110">Guardar un modelo de previsión</span><span class="sxs-lookup"><span data-stu-id="9d54f-110">Save a forecasting model</span></span>
> * <span data-ttu-id="9d54f-111">Usar un modelo de previsión</span><span class="sxs-lookup"><span data-stu-id="9d54f-111">Use a forecasting model</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d54f-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9d54f-112">Prerequisites</span></span>

- <span data-ttu-id="9d54f-113">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="9d54f-113">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="time-series-forecasting-sample-overview"></a><span data-ttu-id="9d54f-114">Información general de un ejemplo de previsión de serie temporal</span><span class="sxs-lookup"><span data-stu-id="9d54f-114">Time series forecasting sample overview</span></span>

<span data-ttu-id="9d54f-115">Este ejemplo es una **aplicación de consola de .NET Core de C#** que prevé la demanda de alquileres de bicicletas con un algoritmo de análisis de serie temporal de variable única conocido como "análisis de un solo espectro".</span><span class="sxs-lookup"><span data-stu-id="9d54f-115">This sample is a **C# .NET Core console application** that forecasts demand for bike rentals using a univariate time series analysis algorithm known as Singular Spectrum Analysis.</span></span> <span data-ttu-id="9d54f-116">El código de este ejemplo se puede encontrar en el [repositorio dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="9d54f-116">The code for this sample can be found on the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository on GitHub.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="9d54f-117">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="9d54f-117">Understand the problem</span></span>

<span data-ttu-id="9d54f-118">Para ejecutar una operación eficaz, la administración de inventario desempeña un rol clave.</span><span class="sxs-lookup"><span data-stu-id="9d54f-118">In order to run an efficient operation, inventory management plays a key role.</span></span> <span data-ttu-id="9d54f-119">Tener en existencia una cantidad excesiva de un producto significa que los productos no vendidos que se encuentran en las estanterías no generan ingresos.</span><span class="sxs-lookup"><span data-stu-id="9d54f-119">Having too much of a product in stock means unsold products sitting on the shelves not generating any revenue.</span></span> <span data-ttu-id="9d54f-120">Tener una cantidad reducida de un producto hace que se pierdan ventas y que los clientes compren a la competencia.</span><span class="sxs-lookup"><span data-stu-id="9d54f-120">Having too little product leads to lost sales and customers purchasing from competitors.</span></span> <span data-ttu-id="9d54f-121">Por lo tanto, la pregunta constante es ¿cuál es la cantidad óptima de inventario que debe mantenerse a mano?</span><span class="sxs-lookup"><span data-stu-id="9d54f-121">Therefore, the constant question is, what is the optimal amount of inventory to keep on hand?</span></span> <span data-ttu-id="9d54f-122">El análisis de serie temporal lo ayuda a proporcionar una respuesta a estas preguntas examinando los datos históricos, identificando patrones y usando esta información para prever valores en el futuro.</span><span class="sxs-lookup"><span data-stu-id="9d54f-122">Time-series analysis helps provide an answer to these questions by looking at historical data, identifying patterns, and using this information to forecast values some time in the future.</span></span>

<span data-ttu-id="9d54f-123">La técnica para analizar los datos que usa este tutorial es el análisis de serie temporal de variable única.</span><span class="sxs-lookup"><span data-stu-id="9d54f-123">The technique for analyzing data used in this tutorial is univariate time-series analysis.</span></span> <span data-ttu-id="9d54f-124">El análisis de serie temporal de variante única examina una única observación numérica durante un período de tiempo a intervalos específicos, como las ventas mensuales.</span><span class="sxs-lookup"><span data-stu-id="9d54f-124">Univariate time-series analysis takes a look at a single numerical observation over a period of time at specific intervals such as monthly sales.</span></span>

<span data-ttu-id="9d54f-125">El algoritmo que se usa en este tutorial es el [análisis de un solo espectro (SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf).</span><span class="sxs-lookup"><span data-stu-id="9d54f-125">The algorithm used in this tutorial is [Singular Spectrum Analysis(SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf).</span></span> <span data-ttu-id="9d54f-126">SSA sirve para descomponer una serie temporal en un conjunto de componentes principales.</span><span class="sxs-lookup"><span data-stu-id="9d54f-126">SSA works by decomposing a time-series into a set of principal components.</span></span> <span data-ttu-id="9d54f-127">Estos componentes se pueden interpretar como partes de una señal que corresponde a tendencias, ruido, estacionalidad y muchos otros factores.</span><span class="sxs-lookup"><span data-stu-id="9d54f-127">These components can be interpreted as the parts of a signal that correspond to trends, noise, seasonality, and many other factors.</span></span> <span data-ttu-id="9d54f-128">Después, estos componentes se reconstruyen y se usan para pronosticar valores en el futuro.</span><span class="sxs-lookup"><span data-stu-id="9d54f-128">Then, these components are reconstructed and used to forecast values some time in the future.</span></span>

## <a name="create-console-application"></a><span data-ttu-id="9d54f-129">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="9d54f-129">Create console application</span></span>

1. <span data-ttu-id="9d54f-130">Cree una **aplicación de consola de .NET Core de C#** denominada "BikeDemandForecasting".</span><span class="sxs-lookup"><span data-stu-id="9d54f-130">Create a new **C# .NET Core console application** called "BikeDemandForecasting".</span></span>
1. <span data-ttu-id="9d54f-131">Instale el paquete NuGet versión **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="9d54f-131">Install **Microsoft.ML** version NuGet package</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    1. <span data-ttu-id="9d54f-132">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="9d54f-132">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="9d54f-133">Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar** y busque **Microsoft.ML**.</span><span class="sxs-lookup"><span data-stu-id="9d54f-133">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**.</span></span>
    1. <span data-ttu-id="9d54f-134">Active la casilla **Incluir versión preliminar**.</span><span class="sxs-lookup"><span data-stu-id="9d54f-134">Check the **Include prerelease** checkbox.</span></span>
    1. <span data-ttu-id="9d54f-135">Seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="9d54f-135">Select the **Install** button.</span></span>
    1. <span data-ttu-id="9d54f-136">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo Aceptación de la licencia en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="9d54f-136">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>
    1. <span data-ttu-id="9d54f-137">Repita estos pasos para **System.Data.SqlClient** y **Microsoft.ML.TimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="9d54f-137">Repeat these steps for **System.Data.SqlClient** and **Microsoft.ML.TimeSeries**.</span></span>

### <a name="prepare-and-understand-the-data"></a><span data-ttu-id="9d54f-138">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="9d54f-138">Prepare and understand the data</span></span>

1. <span data-ttu-id="9d54f-139">Cree un directorio denominado *Data*.</span><span class="sxs-lookup"><span data-stu-id="9d54f-139">Create a directory called *Data*.</span></span>
1. <span data-ttu-id="9d54f-140">Descargue el [archivo de base de datos *DailyDemand.mdf*](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) y guárdelo en el directorio *Data*.</span><span class="sxs-lookup"><span data-stu-id="9d54f-140">Download the [*DailyDemand.mdf* database file](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) and save it to the *Data* directory.</span></span>

> [!NOTE]
> <span data-ttu-id="9d54f-141">Los datos que se usan en este tutorial provienen del conjunto de datos [UCI Bike Sharing Dataset](http://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset).</span><span class="sxs-lookup"><span data-stu-id="9d54f-141">The data used in this tutorial comes from the [UCI Bike Sharing Dataset](http://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset).</span></span> <span data-ttu-id="9d54f-142">Fanaee-T, Hadi, and Gama, Joao, "Event labeling combining ensemble detectors and background knowledge", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [vínculo web](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).</span><span class="sxs-lookup"><span data-stu-id="9d54f-142">Fanaee-T, Hadi, and Gama, Joao, 'Event labeling combining ensemble detectors and background knowledge', Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [Web Link](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).</span></span>

<span data-ttu-id="9d54f-143">El conjunto de datos original contiene varias columnas correspondientes a la estacionalidad y al clima.</span><span class="sxs-lookup"><span data-stu-id="9d54f-143">The original dataset contains several columns corresponding to seasonality and weather.</span></span> <span data-ttu-id="9d54f-144">Con el fin de ser breves y como el algoritmo que se usa en este tutorial solo requiere los valores de una columna numérica única, el conjunto de datos original se ha condensado para incluir solo las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d54f-144">For brevity and because the algorithm used in this tutorial only requires the values from a single numerical column, the original dataset has been condensed to include only the following columns:</span></span>

- <span data-ttu-id="9d54f-145">**dteday**: la fecha de la observación.</span><span class="sxs-lookup"><span data-stu-id="9d54f-145">**dteday**: The date of the observation.</span></span>
- <span data-ttu-id="9d54f-146">**year**: el año codificado de la observación (0=2011, 1=2012).</span><span class="sxs-lookup"><span data-stu-id="9d54f-146">**year**: The encoded year of the observation (0=2011, 1=2012).</span></span>
- <span data-ttu-id="9d54f-147">**cnt**: el número total de alquileres de bicicletas para ese día.</span><span class="sxs-lookup"><span data-stu-id="9d54f-147">**cnt**: The total number of bike rentals for that day.</span></span>

<span data-ttu-id="9d54f-148">El conjunto de datos original se asigna a una tabla de base de datos con el esquema siguiente en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9d54f-148">The original dataset is mapped to a database table with the following schema in a SQL Server database.</span></span>

```sql
CREATE TABLE [Rentals] (
    [RentalDate] DATE NOT NULL,
    [Year] INT NOT NULL,
    [TotalRentals] INT NOT NULL
);
```

<span data-ttu-id="9d54f-149">A continuación se muestra un ejemplo de los datos:</span><span class="sxs-lookup"><span data-stu-id="9d54f-149">The following is a sample of the data:</span></span>

| <span data-ttu-id="9d54f-150">RentalDate</span><span class="sxs-lookup"><span data-stu-id="9d54f-150">RentalDate</span></span> | <span data-ttu-id="9d54f-151">Año</span><span class="sxs-lookup"><span data-stu-id="9d54f-151">Year</span></span> | <span data-ttu-id="9d54f-152">TotalRentals</span><span class="sxs-lookup"><span data-stu-id="9d54f-152">TotalRentals</span></span> |
| --- | --- | --- |
|<span data-ttu-id="9d54f-153">1/1/2011</span><span class="sxs-lookup"><span data-stu-id="9d54f-153">1/1/2011</span></span>|<span data-ttu-id="9d54f-154">0</span><span class="sxs-lookup"><span data-stu-id="9d54f-154">0</span></span>|<span data-ttu-id="9d54f-155">985</span><span class="sxs-lookup"><span data-stu-id="9d54f-155">985</span></span>|
|<span data-ttu-id="9d54f-156">1/2/2011</span><span class="sxs-lookup"><span data-stu-id="9d54f-156">1/2/2011</span></span>|<span data-ttu-id="9d54f-157">0</span><span class="sxs-lookup"><span data-stu-id="9d54f-157">0</span></span>|<span data-ttu-id="9d54f-158">801</span><span class="sxs-lookup"><span data-stu-id="9d54f-158">801</span></span>|
|<span data-ttu-id="9d54f-159">1/3/2011</span><span class="sxs-lookup"><span data-stu-id="9d54f-159">1/3/2011</span></span>|<span data-ttu-id="9d54f-160">0</span><span class="sxs-lookup"><span data-stu-id="9d54f-160">0</span></span>|<span data-ttu-id="9d54f-161">1349</span><span class="sxs-lookup"><span data-stu-id="9d54f-161">1349</span></span>|

### <a name="create-input-and-output-classes"></a><span data-ttu-id="9d54f-162">Creación de las clases de entrada y salida</span><span class="sxs-lookup"><span data-stu-id="9d54f-162">Create input and output classes</span></span>

1. <span data-ttu-id="9d54f-163">Abra el archivo *Program.cs* y reemplace las instrucciones `using` existentes por las siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d54f-163">Open *Program.cs* file and replace the existing `using` statements with the following:</span></span>

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L1-L8)]

1. <span data-ttu-id="9d54f-164">Cree la clase `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="9d54f-164">Create `ModelInput` class.</span></span> <span data-ttu-id="9d54f-165">Debajo de la clase `Program`, agregue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9d54f-165">Below the `Program` class, add the following code.</span></span>

    [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L120-L127)]

    <span data-ttu-id="9d54f-166">La clase `ModelInput` contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d54f-166">The `ModelInput` class contains the following columns:</span></span>

    - <span data-ttu-id="9d54f-167">**RentalDate**: la fecha de la observación.</span><span class="sxs-lookup"><span data-stu-id="9d54f-167">**RentalDate**: The date of the observation.</span></span>
    - <span data-ttu-id="9d54f-168">**Year**: el año codificado de la observación (0=2011, 1=2012).</span><span class="sxs-lookup"><span data-stu-id="9d54f-168">**Year**: The encoded year of the observation (0=2011, 1=2012).</span></span>
    - <span data-ttu-id="9d54f-169">**TotalRentals**: el número total de alquileres de bicicletas para ese día.</span><span class="sxs-lookup"><span data-stu-id="9d54f-169">**TotalRentals**: The total number of bike rentals for that day.</span></span>

1. <span data-ttu-id="9d54f-170">Cree la clase `ModelOutput` debajo de la clase `ModelInput` recién creada.</span><span class="sxs-lookup"><span data-stu-id="9d54f-170">Create `ModelOutput` class below the newly created `ModelInput` class.</span></span>

    [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L129-L136)]

    <span data-ttu-id="9d54f-171">La clase `ModelOutput` contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d54f-171">The `ModelOutput` class contains the following columns:</span></span>

    - <span data-ttu-id="9d54f-172">**ForecastedRentals**: los valores de predicción del período previsto.</span><span class="sxs-lookup"><span data-stu-id="9d54f-172">**ForecastedRentals**: The predicted values for the forecasted period.</span></span>
    - <span data-ttu-id="9d54f-173">**LowerBoundRentals**: los valores mínimos de predicción del período previsto.</span><span class="sxs-lookup"><span data-stu-id="9d54f-173">**LowerBoundRentals**: The predicted minimum values for the forecasted period.</span></span>
    - <span data-ttu-id="9d54f-174">**UpperBoundRentals**: los valores máximos de predicción del período previsto.</span><span class="sxs-lookup"><span data-stu-id="9d54f-174">**UpperBoundRentals**: The predicted maximum values for the forecasted period.</span></span>

### <a name="define-paths-and-initialize-variables"></a><span data-ttu-id="9d54f-175">Definición de rutas de acceso e inicialización de variables</span><span class="sxs-lookup"><span data-stu-id="9d54f-175">Define paths and initialize variables</span></span>

1. <span data-ttu-id="9d54f-176">Dentro del método `Main`, defina las variables para almacenar la ubicación de los datos, la cadena de conexión y dónde guardar el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="9d54f-176">Inside the `Main` method, define variables to store the location of your data, connection string, and where to save the trained model.</span></span>

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L16-L19)]

1. <span data-ttu-id="9d54f-177">Inicialice la variable `mlContext` con una instancia nueva de [`MLContext`](xref:Microsoft.ML.MLContext) mediante la incorporación de la línea siguiente en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="9d54f-177">Initialize the `mlContext` variable with a new instance of [`MLContext`](xref:Microsoft.ML.MLContext) by adding the following line to the `Main` method.</span></span>

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L21)]

    <span data-ttu-id="9d54f-178">La clase [`MLContext`](xref:Microsoft.ML.MLContext) es un punto inicial para todas las operaciones de ML.NET. Al inicializar mlContext, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos.</span><span class="sxs-lookup"><span data-stu-id="9d54f-178">The [`MLContext`](xref:Microsoft.ML.MLContext) class is a starting point for all ML.NET operations, and initializing mlContext creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="9d54f-179">Como concepto, se parece a `DBContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="9d54f-179">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="9d54f-180">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="9d54f-180">Load the data</span></span>

1. <span data-ttu-id="9d54f-181">Cree `DatabaseLoader` que cargue los registros de tipo `ModelInput`.</span><span class="sxs-lookup"><span data-stu-id="9d54f-181">Create `DatabaseLoader` that loads records of type `ModelInput`.</span></span>

    [!code-csharp [CreateDBLoader](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L23)]

1. <span data-ttu-id="9d54f-182">Defina la consulta para cargar los datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9d54f-182">Define the query to load the data from the database.</span></span>

    [!code-csharp [DefineSQLQuery](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L25)]

    <span data-ttu-id="9d54f-183">Los algoritmos de ML.NET esperan que los datos sean de tipo [`Single`](xref:System.Single).</span><span class="sxs-lookup"><span data-stu-id="9d54f-183">ML.NET algorithms expect data to be of type [`Single`](xref:System.Single).</span></span> <span data-ttu-id="9d54f-184">Por lo tanto, los valores numéricos que provienen de la base de datos que no son de tipo [`Real`](xref:System.Data.SqlDbType), un valor de punto flotante de precisión sencilla, se deben convertir en [`Real`](xref:System.Data.SqlDbType).</span><span class="sxs-lookup"><span data-stu-id="9d54f-184">Therefore, numerical values coming from the database that are not of type [`Real`](xref:System.Data.SqlDbType), a single-precision floating-point value, have to be converted to [`Real`](xref:System.Data.SqlDbType).</span></span>

    <span data-ttu-id="9d54f-185">Las columnas `Year` y `TotalRental` son tipos enteros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9d54f-185">The `Year` and `TotalRental` columns are both integer types in the database.</span></span> <span data-ttu-id="9d54f-186">Con la función integrada `CAST`, ambos se convierten en `Real`.</span><span class="sxs-lookup"><span data-stu-id="9d54f-186">Using the `CAST` built-in function, they are both cast to `Real`.</span></span>

1. <span data-ttu-id="9d54f-187">Cree un `DatabaseSource` para conectarse a la base de datos y ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="9d54f-187">Create a `DatabaseSource` to connect to the database and execute the query.</span></span>

    [!code-csharp [CreateDBSource](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L27-L29)]

1. <span data-ttu-id="9d54f-188">Cargue los datos en un `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="9d54f-188">Load the data into an `IDataView`.</span></span>

    [!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L31)]

1. <span data-ttu-id="9d54f-189">El conjunto de datos contiene datos de dos años.</span><span class="sxs-lookup"><span data-stu-id="9d54f-189">The dataset contains two years worth of data.</span></span> <span data-ttu-id="9d54f-190">Solo se usan los datos del primer año para el entrenamiento, el segundo año se mantiene para comparar los valores reales con el pronóstico generado por el modelo.</span><span class="sxs-lookup"><span data-stu-id="9d54f-190">Only data from the first year is used for training, the second year is held out to compare the actual values against the forecast produced by the model.</span></span> <span data-ttu-id="9d54f-191">Filtre los datos con la transformación [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A).</span><span class="sxs-lookup"><span data-stu-id="9d54f-191">Filter the data using the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A) transform.</span></span>

    [!code-csharp [SplitData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L33-L34)]

    <span data-ttu-id="9d54f-192">Para el primer año, se seleccionan solo los valores de la columna `Year` menores que 1 al establecer el parámetro `upperBound` en 1.</span><span class="sxs-lookup"><span data-stu-id="9d54f-192">For the first year, only the values in the `Year` column less than 1 are selected by setting the `upperBound` parameter to 1.</span></span> <span data-ttu-id="9d54f-193">A la inversa, para el segundo año, se seleccionan los valores mayores o iguales que 1 al establecer el parámetro `lowerBound` en 1.</span><span class="sxs-lookup"><span data-stu-id="9d54f-193">Conversely, for the second year, values greater than or equal to 1 are selected by setting the `lowerBound` parameter to 1.</span></span>

## <a name="define-time-series-analysis-pipeline"></a><span data-ttu-id="9d54f-194">Definición de la canalización de análisis de serie temporal</span><span class="sxs-lookup"><span data-stu-id="9d54f-194">Define time series analysis pipeline</span></span>

1. <span data-ttu-id="9d54f-195">Defina una canalización que use [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) para pronosticar valores en un conjunto de datos de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="9d54f-195">Define a pipeline that uses the [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) to forecast values in a time-series dataset.</span></span>

    [!code-csharp [DefinePipeline](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L36-L45)]

    <span data-ttu-id="9d54f-196">`forecastingPipeline` toma 365 puntos de datos para el primer año y muestrea o divide el conjunto de datos de serie temporal en intervalos de 30 días (mensualmente) según lo especificado en el parámetro `seriesLength`.</span><span class="sxs-lookup"><span data-stu-id="9d54f-196">The `forecastingPipeline` takes 365 data points for the first year and samples or splits the time-series dataset into 30-day (monthly) intervals as specified by the `seriesLength` parameter.</span></span> <span data-ttu-id="9d54f-197">Cada uno de estos ejemplos se analiza durante una ventana semanal o de 7 días.</span><span class="sxs-lookup"><span data-stu-id="9d54f-197">Each of these samples is analyzed through weekly or a 7-day window.</span></span> <span data-ttu-id="9d54f-198">A la hora de determinar cuál es el valor de previsión para el período siguiente, se usan los valores de los siete días anteriores para realizar una predicción.</span><span class="sxs-lookup"><span data-stu-id="9d54f-198">When determining what the forecasted value for the next period(s) is, the values from previous seven days are used to make a prediction.</span></span> <span data-ttu-id="9d54f-199">El modelo se establece para pronosticar siete períodos en el futuro, tal como se define en el parámetro `horizon`.</span><span class="sxs-lookup"><span data-stu-id="9d54f-199">The model is set to forecast seven periods into the future as defined by the `horizon` parameter.</span></span> <span data-ttu-id="9d54f-200">Como una previsión es una estimación informada, no siempre es 100  precisa.</span><span class="sxs-lookup"><span data-stu-id="9d54f-200">Because a forecast is an informed guess, it's not always 100% accurate.</span></span> <span data-ttu-id="9d54f-201">Por lo tanto, es conveniente conocer el intervalo de valores en los mejores y peores escenarios, tal como se define en los límites superior e inferior.</span><span class="sxs-lookup"><span data-stu-id="9d54f-201">Therefore, it's good to know the range of values in the best and worst-case scenarios as defined by the upper and lower bounds.</span></span> <span data-ttu-id="9d54f-202">En este caso, el nivel de confianza de los límites inferior y superior se establece en 95 %.</span><span class="sxs-lookup"><span data-stu-id="9d54f-202">In this case, the level of confidence for the lower and upper bounds is set to 95%.</span></span> <span data-ttu-id="9d54f-203">El nivel de confianza se puede aumentar o reducir en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="9d54f-203">The confidence level can be increased or decreased accordingly.</span></span> <span data-ttu-id="9d54f-204">Cuanto mayor sea el valor, más amplio será el intervalo entre los límites superior e inferior para lograr el nivel de confianza deseado.</span><span class="sxs-lookup"><span data-stu-id="9d54f-204">The higher the value, the wider the range is between the upper and lower bounds to achieve the desired level of confidence.</span></span>

1. <span data-ttu-id="9d54f-205">Use el método [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit%2A) para entrenar el modelo y ajustar los datos a la `forecastingPipeline` definida previamente.</span><span class="sxs-lookup"><span data-stu-id="9d54f-205">Use the [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit%2A) method to train the model and fit the data to the previously defined `forecastingPipeline`.</span></span>

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L47)]

## <a name="evaluate-the-model"></a><span data-ttu-id="9d54f-206">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="9d54f-206">Evaluate the model</span></span>

<span data-ttu-id="9d54f-207">Evalúe el rendimiento del modelo al prever los datos del año siguiente y comparándolos con los valores reales.</span><span class="sxs-lookup"><span data-stu-id="9d54f-207">Evaluate how well the model performs by forecasting next year's data and comparing it against the actual values.</span></span>

1. <span data-ttu-id="9d54f-208">Debajo del método `Main`, cree un método de utilidad denominado `Evaluate`.</span><span class="sxs-lookup"><span data-stu-id="9d54f-208">Below the `Main` method, create a new utility method called `Evaluate`.</span></span>

    ```csharp
    static void Evaluate(IDataView testData, ITransformer model, MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="9d54f-209">Dentro del método `Evaluate`, prevea los datos del segundo año a través del método [`Transform`](xref:Microsoft.ML.ITransformer.Transform%2A) con el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="9d54f-209">Inside the `Evaluate` method, forecast the second year's data by using the [`Transform`](xref:Microsoft.ML.ITransformer.Transform%2A) method with the trained model.</span></span>

    [!code-csharp [EvaluateForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L62)]

1. <span data-ttu-id="9d54f-210">Obtenga los valores reales de los datos a través del método [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A).</span><span class="sxs-lookup"><span data-stu-id="9d54f-210">Get the actual values from the data by using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method.</span></span>

    [!code-csharp [GetActualRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L65-L67)]

1. <span data-ttu-id="9d54f-211">Use el método [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) para obtener los valores de previsión.</span><span class="sxs-lookup"><span data-stu-id="9d54f-211">Get the forecast values by using the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method.</span></span>

    [!code-csharp [GetForecastRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L70-L72)]

1. <span data-ttu-id="9d54f-212">Calcule la diferencia entre los valores reales y los de previsión, lo que se conoce a menudo como "error".</span><span class="sxs-lookup"><span data-stu-id="9d54f-212">Calculate the difference between the actual and forecast values, commonly referred to as the error.</span></span>

    [!code-csharp [CalculateError](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L75)]

1. <span data-ttu-id="9d54f-213">Para medir el rendimiento, calcule los valores de error medio absoluto y medio y error cuadrático medio.</span><span class="sxs-lookup"><span data-stu-id="9d54f-213">Measure performance by computing the Mean Absolute Error and Root Mean Squared Error values.</span></span>

    [!code-csharp [CalculateMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L78-L79)]

    <span data-ttu-id="9d54f-214">Para evaluar el rendimiento, se usan las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d54f-214">To evaluate performance, the following metrics are used:</span></span>

    - <span data-ttu-id="9d54f-215">**Error medio absoluto**: mide la cercanía de las predicciones respecto del valor real.</span><span class="sxs-lookup"><span data-stu-id="9d54f-215">**Mean Absolute Error**: Measures how close predictions are to the actual value.</span></span> <span data-ttu-id="9d54f-216">Este valor va de 0 a infinito.</span><span class="sxs-lookup"><span data-stu-id="9d54f-216">This value ranges between 0 and infinity.</span></span> <span data-ttu-id="9d54f-217">Cuanto más se acerque a 0, mejor es la calidad del modelo.</span><span class="sxs-lookup"><span data-stu-id="9d54f-217">The closer to 0, the better the quality of the model.</span></span>
    - <span data-ttu-id="9d54f-218">**Error cuadrático medio**: resume el error del modelo.</span><span class="sxs-lookup"><span data-stu-id="9d54f-218">**Root Mean Squared Error**: Summarizes the error in the model.</span></span> <span data-ttu-id="9d54f-219">Este valor va de 0 a infinito.</span><span class="sxs-lookup"><span data-stu-id="9d54f-219">This value ranges between 0 and infinity.</span></span> <span data-ttu-id="9d54f-220">Cuanto más se acerque a 0, mejor es la calidad del modelo.</span><span class="sxs-lookup"><span data-stu-id="9d54f-220">The closer to 0, the better the quality of the model.</span></span>

1. <span data-ttu-id="9d54f-221">Genere las métricas en la consola.</span><span class="sxs-lookup"><span data-stu-id="9d54f-221">Output the metrics to the console.</span></span>

    [!code-csharp [OutputMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L82-L85)]

1. <span data-ttu-id="9d54f-222">Use el método `Evaluate` dentro del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="9d54f-222">Use the `Evaluate` method inside the `Main` method.</span></span>

    [!code-csharp [EvaluateModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L49)]

## <a name="save-the-model"></a><span data-ttu-id="9d54f-223">Guardado del modelo</span><span class="sxs-lookup"><span data-stu-id="9d54f-223">Save the model</span></span>

<span data-ttu-id="9d54f-224">Si está satisfecho con el modelo, guárdelo para usarlo más adelante en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9d54f-224">If you're satisfied with your model, save it for later use in other applications.</span></span>

1. <span data-ttu-id="9d54f-225">En el método `Main`, cree un [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="9d54f-225">In the `Main` method, create a [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602).</span></span> <span data-ttu-id="9d54f-226">[`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) es un método útil para hacer predicciones únicas.</span><span class="sxs-lookup"><span data-stu-id="9d54f-226">[`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) is a convenience method to make single predictions.</span></span>

    [!code-csharp [CreateTimeSeriesEngine](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L51)]

1. <span data-ttu-id="9d54f-227">Guarde el modelo en un archivo denominado `MLModel.zip`, según lo especificado en la variable `modelPath` definida anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9d54f-227">Save the model to a file called `MLModel.zip` as specified by the previously defined `modelPath` variable.</span></span> <span data-ttu-id="9d54f-228">Use el método [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint%2A) para guardar el modelo.</span><span class="sxs-lookup"><span data-stu-id="9d54f-228">Use the [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint%2A) method to save the model.</span></span>

    [!code-csharp [SaveModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L52)]

## <a name="use-the-model-to-forecast-demand"></a><span data-ttu-id="9d54f-229">Uso del modelo para pronosticar la demanda</span><span class="sxs-lookup"><span data-stu-id="9d54f-229">Use the model to forecast demand</span></span>

1. <span data-ttu-id="9d54f-230">Debajo del método `Evaluate`, cree un método de utilidad denominado `Forecast`.</span><span class="sxs-lookup"><span data-stu-id="9d54f-230">Below the `Evaluate` method, create a new utility method called `Forecast`.</span></span>

    ```csharp
    static void Forecast(IDataView testData, int horizon, TimeSeriesPredictionEngine<ModelInput, ModelOutput> forecaster, MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="9d54f-231">En el método `Forecast`, use el método [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict%2A) para pronosticar los alquileres durante los próximos siete días.</span><span class="sxs-lookup"><span data-stu-id="9d54f-231">Inside the `Forecast` method, use the [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict%2A) method to forecast rentals for the next seven days.</span></span>

    [!code-csharp [SingleForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L91)]

1. <span data-ttu-id="9d54f-232">Alinee los valores reales y los valores de previsión durante siete períodos.</span><span class="sxs-lookup"><span data-stu-id="9d54f-232">Align the actual and forecast values for seven periods.</span></span>

    [!code-csharp [GetForecastOutput](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L93-L108)]

1. <span data-ttu-id="9d54f-233">Recorra en iteración la salida del pronóstico y muéstrela en la consola.</span><span class="sxs-lookup"><span data-stu-id="9d54f-233">Iterate through the forecast output and display it on the console.</span></span>

    [!code-csharp [DisplayForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L111-L116)]

## <a name="run-the-application"></a><span data-ttu-id="9d54f-234">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="9d54f-234">Run the application</span></span>

1. <span data-ttu-id="9d54f-235">En el método `Main`, llame al método `Forecast`.</span><span class="sxs-lookup"><span data-stu-id="9d54f-235">Inside the `Main` method, call the `Forecast` method.</span></span>

    [!code-csharp [BuildForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L54)]

1. <span data-ttu-id="9d54f-236">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9d54f-236">Run the application.</span></span> <span data-ttu-id="9d54f-237">En la consola debería aparecer una salida similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="9d54f-237">Output similar to that below should appear on the console.</span></span> <span data-ttu-id="9d54f-238">Por motivos de brevedad, la salida se ha resumido.</span><span class="sxs-lookup"><span data-stu-id="9d54f-238">For brevity, the output has been condensed.</span></span>

    ```text
    Evaluation Metrics
    ---------------------
    Mean Absolute Error: 726.416
    Root Mean Squared Error: 987.658

    Rental Forecast
    ---------------------
    Date: 1/1/2012
    Actual Rentals: 2294
    Lower Estimate: 1197.842
    Forecast: 2334.443
    Upper Estimate: 3471.044

    Date: 1/2/2012
    Actual Rentals: 1951
    Lower Estimate: 1148.412
    Forecast: 2360.861
    Upper Estimate: 3573.309
    ```

<span data-ttu-id="9d54f-239">La inspección de los valores reales y previstos muestra las relaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d54f-239">Inspection of the actual and forecasted values shows the following relationships:</span></span>

![Comparación de valores reales y valores previstos](./media/time-series-demand-forecasting/forecast.png)

<span data-ttu-id="9d54f-241">Aunque los valores pronosticados no predicen el número exacto de alquileres, sí proporcionan un intervalo más acotado de valores que permite que una operación optimice el uso de los recursos.</span><span class="sxs-lookup"><span data-stu-id="9d54f-241">While the forecasted values are not predicting the exact number of rentals, they provide a more narrow range of values that allows an operation to optimize their use of resources.</span></span>

<span data-ttu-id="9d54f-242">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="9d54f-242">Congratulations!</span></span> <span data-ttu-id="9d54f-243">Creó correctamente un modelo de Machine Learning de serie temporal para predecir la demanda de alquileres de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="9d54f-243">You've now successfully built a time series machine learning model to forecast bike rental demand.</span></span>

<span data-ttu-id="9d54f-244">Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand).</span><span class="sxs-lookup"><span data-stu-id="9d54f-244">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9d54f-245">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9d54f-245">Next steps</span></span>

- [<span data-ttu-id="9d54f-246">Tareas de aprendizaje automático en ML.NET</span><span class="sxs-lookup"><span data-stu-id="9d54f-246">Machine learning tasks in ML.NET</span></span>](../resources/tasks.md)
- [<span data-ttu-id="9d54f-247">Mejora de la precisión del modelo</span><span class="sxs-lookup"><span data-stu-id="9d54f-247">Improve model accuracy</span></span>](../resources/improve-machine-learning-model-ml-net.md)

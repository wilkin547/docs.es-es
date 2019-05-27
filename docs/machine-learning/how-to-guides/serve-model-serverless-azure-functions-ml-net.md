---
title: Implementación de un modelo en Azure Functions
description: Publicación del modelo de Machine Learning de Análisis de sentimiento de ML.NET para la predicción en Internet a través de Azure Functions
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 9e62d8826227aed07451387cc733d27094327f99
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645103"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="24e32-103">Implementación de un modelo en Azure Functions</span><span class="sxs-lookup"><span data-stu-id="24e32-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="24e32-104">Aprenda cómo implementar un modelo de Machine Learning de ML.NET previamente entrenado para realizar predicciones por HTTP a través de un entorno sin servidor de Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="24e32-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="24e32-105">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="24e32-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24e32-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="24e32-106">Prerequisites</span></span>

- <span data-ttu-id="24e32-107">[Visual Studio 2017 15.6 o versión posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" y el "desarrollo de Azure" instalados.</span><span class="sxs-lookup"><span data-stu-id="24e32-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- [<span data-ttu-id="24e32-108">Herramientas de Azure Functions</span><span class="sxs-lookup"><span data-stu-id="24e32-108">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="24e32-109">PowerShell</span><span class="sxs-lookup"><span data-stu-id="24e32-109">Powershell</span></span>
- <span data-ttu-id="24e32-110">Modelo previamente entrenado.</span><span class="sxs-lookup"><span data-stu-id="24e32-110">Pre-trained model.</span></span> <span data-ttu-id="24e32-111">Use el [tutorial de análisis de sentimiento de ML.NET](../tutorials/sentiment-analysis.md) para generar su propio modelo o descargue este [modelo de Machine Learning de análisis de sentimiento entrenado previamente](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).</span><span class="sxs-lookup"><span data-stu-id="24e32-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="24e32-112">Creación de un proyecto de Azure Functions</span><span class="sxs-lookup"><span data-stu-id="24e32-112">Create Azure Functions project</span></span>

1. <span data-ttu-id="24e32-113">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="24e32-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="24e32-114">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="24e32-114">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="24e32-115">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **Cloud**.</span><span class="sxs-lookup"><span data-stu-id="24e32-115">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="24e32-116">A continuación, seleccione la plantilla de proyecto **Azure Functions**.</span><span class="sxs-lookup"><span data-stu-id="24e32-116">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="24e32-117">En el cuadro de texto **Nombre**, escriba "SentimentAnalysisFunctionsApp" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="24e32-117">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="24e32-118">En el cuadro de diálogo **Nuevo proyecto**, abra el menú desplegable que se encuentra sobre las opciones del proyecto y seleccione **Azure Functions v2 (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="24e32-118">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="24e32-119">Luego, seleccione el proyecto **Desencadenador HTTP** y luego haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="24e32-119">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="24e32-120">En el proyecto, cree un directorio denominado *MLModels* para guardar el modelo:</span><span class="sxs-lookup"><span data-stu-id="24e32-120">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="24e32-121">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="24e32-121">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="24e32-122">Escriba "MLModels" y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="24e32-122">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="24e32-123">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="24e32-123">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="24e32-124">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="24e32-124">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="24e32-125">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="24e32-125">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="24e32-126">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="24e32-126">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="24e32-127">Instale el **paquete NuGet Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="24e32-127">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="24e32-128">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="24e32-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="24e32-129">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.Extensions.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="24e32-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="24e32-130">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="24e32-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="24e32-131">Incorporación del modelo entrenado previamente en el proyecto</span><span class="sxs-lookup"><span data-stu-id="24e32-131">Add pre-trained model to project</span></span>

1. <span data-ttu-id="24e32-132">Copie el modelo precompilado en la carpeta *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="24e32-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="24e32-133">En el Explorador de soluciones, haga clic con el botón derecho en el archivo del modelo precompilado y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="24e32-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="24e32-134">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="24e32-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="24e32-135">Creación de una función de Azure para analizar sentimientos</span><span class="sxs-lookup"><span data-stu-id="24e32-135">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="24e32-136">Cree una clase para predecir sentimientos.</span><span class="sxs-lookup"><span data-stu-id="24e32-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="24e32-137">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="24e32-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="24e32-138">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="24e32-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="24e32-139">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Función de Azure** y cambie el campo **Nombre** a *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="24e32-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="24e32-140">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="24e32-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="24e32-141">En el cuadro de diálogo **Nueva función de Azure**, seleccione **Desencadenador HTTP**.</span><span class="sxs-lookup"><span data-stu-id="24e32-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="24e32-142">Luego haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="24e32-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="24e32-143">El archivo *AnalyzeSentiment.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="24e32-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="24e32-144">Agregue la siguiente instrucción `using` a la parte superior de *AnalyzeSentiment.cs*:</span><span class="sxs-lookup"><span data-stu-id="24e32-144">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

    ```csharp
    using System;
    using System.IO;
    using System.Threading.Tasks;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Extensions.Http;
    using Microsoft.AspNetCore.Http;
    using Microsoft.Extensions.Logging;
    using Newtonsoft.Json;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="24e32-145">De forma predeterminada, la clase `AnalyzeSentiment` es `static`.</span><span class="sxs-lookup"><span data-stu-id="24e32-145">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="24e32-146">Asegúrese de quitar la palabra clave `static` de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="24e32-146">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="24e32-147">Creación de modelos de datos</span><span class="sxs-lookup"><span data-stu-id="24e32-147">Create data models</span></span>

<span data-ttu-id="24e32-148">Debe crear algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="24e32-148">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="24e32-149">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="24e32-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="24e32-150">Cree un directorio denominado *DataModels* en el proyecto para guardar los modelos de datos: En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="24e32-150">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="24e32-151">Escriba "DataModels" y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="24e32-151">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="24e32-152">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="24e32-152">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="24e32-153">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="24e32-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="24e32-154">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="24e32-154">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="24e32-155">Se abre el archivo *SentimentData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="24e32-155">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="24e32-156">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="24e32-156">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="24e32-157">Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="24e32-157">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
    ```csharp
    public class SentimentData
    {
        [LoadColumn(0)]
        public string SentimentText;

        [LoadColumn(1)]
        [ColumnName("Label")]
        public bool Sentiment;
    }
    ```

4. <span data-ttu-id="24e32-158">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="24e32-158">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="24e32-159">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="24e32-159">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="24e32-160">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="24e32-160">Then, select the **Add** button.</span></span> <span data-ttu-id="24e32-161">El archivo *SentimentPrediction.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="24e32-161">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="24e32-162">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="24e32-162">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="24e32-163">Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="24e32-163">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="24e32-164">`SentimentPrediction` hereda de `SentimentData` el cual proporciona acceso a los datos originales en la propiedad `SentimentText`, así como la salida generada por el modelo.</span><span class="sxs-lookup"><span data-stu-id="24e32-164">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="24e32-165">Registro del servicio PredictionEnginePool</span><span class="sxs-lookup"><span data-stu-id="24e32-165">Register PredictionEnginePool service</span></span>

<span data-ttu-id="24e32-166">Para realizar una sola predicción, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="24e32-166">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="24e32-167">Para poder usar [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) en la aplicación, debe crearlo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="24e32-167">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="24e32-168">En ese caso, un procedimiento recomendado que se debe considerar es la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="24e32-168">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="24e32-169">En el vínculo siguiente se proporciona más información si quiere aprender sobre la [inserción de dependencias](https://en.wikipedia.org/wiki/Dependency_injection).</span><span class="sxs-lookup"><span data-stu-id="24e32-169">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="24e32-170">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="24e32-170">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="24e32-171">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="24e32-171">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="24e32-172">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="24e32-172">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="24e32-173">Se abre el archivo *Startup.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="24e32-173">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="24e32-174">Agregue la instrucción using siguiente en la parte superior del archivo *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="24e32-174">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="24e32-175">Quite el código existente debajo de las instrucciones using y agregue el código siguiente al archivo *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="24e32-175">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

    ```csharp
    [assembly: WebJobsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        class Startup : IWebJobsStartup
        {
            public void Configure(IWebJobsBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile("MLModels/sentiment_model.zip");
            }
        }
    }
    ```

<span data-ttu-id="24e32-176">En un nivel alto, este código inicializa los objetos y servicios de manera automática cuando lo solicita la aplicación en lugar de tener que hacerlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="24e32-176">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="24e32-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="24e32-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="24e32-178">Para mejorar el rendimiento y la seguridad para subprocesos, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos `PredictionEngine` para el uso de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="24e32-178">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="register-startup-as-an-azure-functions-extension"></a><span data-ttu-id="24e32-179">Registro de Startup como una extensión de Azure Functions</span><span class="sxs-lookup"><span data-stu-id="24e32-179">Register Startup as an Azure Functions extension</span></span>

<span data-ttu-id="24e32-180">Para poder usar `Startup` en la aplicación, deberá registrarlo como una extensión de Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="24e32-180">In order to use `Startup` in your application, you need to register it as an Azure Functions extension.</span></span> <span data-ttu-id="24e32-181">Cree un nuevo archivo denominado *extensions.json* en el proyecto si aún no existe uno.</span><span class="sxs-lookup"><span data-stu-id="24e32-181">Create a new file called *extensions.json* in your project if one does not already exist.</span></span>

1. <span data-ttu-id="24e32-182">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="24e32-182">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="24e32-183">En el cuadro de diálogo **Nuevo elemento**, seleccione el nodo **Visual C#** seguido del nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="24e32-183">In the **New Item** dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="24e32-184">A continuación, seleccione la opción del **archivo Json**.</span><span class="sxs-lookup"><span data-stu-id="24e32-184">Then select the **Json File** option.</span></span> <span data-ttu-id="24e32-185">En el cuadro de texto **Nombre**, escriba "extensions.json" y después seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="24e32-185">In the **Name** text box, type "extensions.json" and then select the **OK** button.</span></span>

    <span data-ttu-id="24e32-186">El archivo *extensions.json* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="24e32-186">The *extensions.json* file opens in the code editor.</span></span> <span data-ttu-id="24e32-187">Agregue el contenido siguiente a *extensions.json*:</span><span class="sxs-lookup"><span data-stu-id="24e32-187">Add the following content to *extensions.json*:</span></span>
    
    ```json
    {
      "extensions": [
        {
          "name": "Startup",
          "typename": "SentimentAnalysisFunctionsApp.Startup, SentimentAnalysisFunctionsApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"
        }
      ]
    }
    ```

1. <span data-ttu-id="24e32-188">En el Explorador de soluciones, haga clic con el botón derecho en el archivo *extensions.json* y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="24e32-188">In Solution Explorer, right-click your *extensions.json* file and select **Properties**.</span></span> <span data-ttu-id="24e32-189">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="24e32-189">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="24e32-190">Carga del modelo en la función</span><span class="sxs-lookup"><span data-stu-id="24e32-190">Load the model into the function</span></span>

<span data-ttu-id="24e32-191">Inserte el código siguiente dentro de la clase *AnalyzeSentiment*:</span><span class="sxs-lookup"><span data-stu-id="24e32-191">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="24e32-192">Este código asigna `PredictionEnginePool` al pasarlo al constructor de la función que se obtiene a través de una inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="24e32-192">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="24e32-193">Uso del modelo para realizar predicciones</span><span class="sxs-lookup"><span data-stu-id="24e32-193">Use the model to make predictions</span></span>

<span data-ttu-id="24e32-194">Reemplace la implementación existente del método *Run* en la clase *AnalyzeSentiment* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="24e32-194">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
[FunctionName("AnalyzeSentiment")]
public async Task<IActionResult> Run(
[HttpTrigger(AuthorizationLevel.Function, "post", Route = null)] HttpRequest req,
ILogger log)
{
    log.LogInformation("C# HTTP trigger function processed a request.");

    //Parse HTTP Request Body
    string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
    SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);
    
    //Make Prediction
    SentimentPrediction prediction = _predictionEnginePool.Predict(data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

<span data-ttu-id="24e32-195">Cuando se ejecuta el método `Run`, los datos entrantes de la solicitud HTTP se deserializan y se usan como entrada en el `PredictionEnginePool`.</span><span class="sxs-lookup"><span data-stu-id="24e32-195">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="24e32-196">A continuación, se llama al método `Predict` para generar una predicción y devolver el resultado al usuario.</span><span class="sxs-lookup"><span data-stu-id="24e32-196">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="24e32-197">Prueba local</span><span class="sxs-lookup"><span data-stu-id="24e32-197">Test locally</span></span>

<span data-ttu-id="24e32-198">Ahora que está todo configurado, es momento de probar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="24e32-198">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="24e32-199">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="24e32-199">Run the application</span></span>
1. <span data-ttu-id="24e32-200">Abra PowerShell y escriba el código en el símbolo del sistema, donde PORT es el puerto en que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="24e32-200">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="24e32-201">Por lo general, se trata del puerto 7071.</span><span class="sxs-lookup"><span data-stu-id="24e32-201">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="24e32-202">Si se realiza correctamente, la salida debería ser similar al texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="24e32-202">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="24e32-203">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="24e32-203">Congratulations!</span></span> <span data-ttu-id="24e32-204">Publicó correctamente el modelo para realizar predicciones en Internet mediante una función de Azure.</span><span class="sxs-lookup"><span data-stu-id="24e32-204">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="24e32-205">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="24e32-205">Next Steps</span></span>

- [<span data-ttu-id="24e32-206">Implementación en Azure</span><span class="sxs-lookup"><span data-stu-id="24e32-206">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)

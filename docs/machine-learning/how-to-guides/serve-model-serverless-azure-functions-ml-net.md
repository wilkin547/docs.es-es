---
title: Implementación de un modelo en Azure Functions
description: Publicación del modelo de Machine Learning de Análisis de sentimiento de ML.NET para la predicción en Internet a través de Azure Functions
ms.date: 08/20/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 96b62017994da5b7b209c441b3e7fb760cad5201
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666666"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="b3542-103">Implementación de un modelo en Azure Functions</span><span class="sxs-lookup"><span data-stu-id="b3542-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="b3542-104">Aprenda cómo implementar un modelo de Machine Learning de ML.NET previamente entrenado para realizar predicciones por HTTP a través de un entorno sin servidor de Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="b3542-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="b3542-105">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="b3542-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3542-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b3542-106">Prerequisites</span></span>

- <span data-ttu-id="b3542-107">[Visual Studio 2017 15.6 o versión posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" y el "desarrollo de Azure" instalados.</span><span class="sxs-lookup"><span data-stu-id="b3542-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- <span data-ttu-id="b3542-108">Paquete NuGet Microsoft.NET.Sdk.Functions, versión 1.0.28 y posterior.</span><span class="sxs-lookup"><span data-stu-id="b3542-108">Microsoft.NET.Sdk.Functions NuGet Package version 1.0.28+.</span></span>
- [<span data-ttu-id="b3542-109">Herramientas de Azure Functions</span><span class="sxs-lookup"><span data-stu-id="b3542-109">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="b3542-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3542-110">Powershell</span></span>
- <span data-ttu-id="b3542-111">Modelo previamente entrenado.</span><span class="sxs-lookup"><span data-stu-id="b3542-111">Pre-trained model.</span></span> <span data-ttu-id="b3542-112">Use el [tutorial de análisis de sentimiento de ML.NET](../tutorials/sentiment-analysis.md) para generar su propio modelo o descargue este [modelo de Machine Learning de análisis de sentimiento entrenado previamente](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).</span><span class="sxs-lookup"><span data-stu-id="b3542-112">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="b3542-113">Creación de un proyecto de Azure Functions</span><span class="sxs-lookup"><span data-stu-id="b3542-113">Create Azure Functions project</span></span>

1. <span data-ttu-id="b3542-114">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="b3542-114">Open Visual Studio 2017.</span></span> <span data-ttu-id="b3542-115">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="b3542-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="b3542-116">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **Cloud**.</span><span class="sxs-lookup"><span data-stu-id="b3542-116">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="b3542-117">A continuación, seleccione la plantilla de proyecto **Azure Functions**.</span><span class="sxs-lookup"><span data-stu-id="b3542-117">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="b3542-118">En el cuadro de texto **Nombre**, escriba "SentimentAnalysisFunctionsApp" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b3542-118">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="b3542-119">En el cuadro de diálogo **Nuevo proyecto**, abra el menú desplegable que se encuentra sobre las opciones del proyecto y seleccione **Azure Functions v2 (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="b3542-119">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="b3542-120">Luego, seleccione el proyecto **Desencadenador HTTP** y luego haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b3542-120">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="b3542-121">En el proyecto, cree un directorio denominado *MLModels* para guardar el modelo:</span><span class="sxs-lookup"><span data-stu-id="b3542-121">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="b3542-122">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="b3542-122">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="b3542-123">Escriba "MLModels" y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b3542-123">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="b3542-124">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="b3542-124">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="b3542-125">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="b3542-125">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="b3542-126">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="b3542-126">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="b3542-127">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="b3542-127">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="b3542-128">Instalar el **paquete NuGet Microsoft.Azure.Functions.Extensions**:</span><span class="sxs-lookup"><span data-stu-id="b3542-128">Install the **Microsoft.Azure.Functions.Extensions NuGet Package**:</span></span>

    <span data-ttu-id="b3542-129">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="b3542-129">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="b3542-130">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.Azure.Functions.Extensions**, seleccione ese paquete en la lista y seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="b3542-130">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Azure.Functions.Extensions**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="b3542-131">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="b3542-131">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="b3542-132">Instale el **paquete NuGet Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="b3542-132">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="b3542-133">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="b3542-133">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="b3542-134">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.Extensions.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="b3542-134">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="b3542-135">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="b3542-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="b3542-136">Actualice el **paquete NuGet Microsoft.NET.Sdk.Functions** a la versión 1.0.28+:</span><span class="sxs-lookup"><span data-stu-id="b3542-136">Update the **Microsoft.NET.Sdk.Functions NuGet Package** to version 1.0.28+:</span></span>

    <span data-ttu-id="b3542-137">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="b3542-137">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="b3542-138">Elija "nuget.org" como el origen del paquete, seleccione la pestaña Instalado, busque **Microsoft.NET.Sdk.Functions**, seleccione ese paquete en la lista, seleccione 1.0.28 o posterior en la lista desplegable Versión y seleccione el botón **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="b3542-138">Choose "nuget.org" as the Package source, select the Installed tab, search for **Microsoft.NET.Sdk.Functions**, select that package in the list, select 1.0.28 or later from the Version dropdown, and select the **Update** button.</span></span> <span data-ttu-id="b3542-139">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="b3542-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="b3542-140">Incorporación del modelo entrenado previamente en el proyecto</span><span class="sxs-lookup"><span data-stu-id="b3542-140">Add pre-trained model to project</span></span>

1. <span data-ttu-id="b3542-141">Copie el modelo precompilado en la carpeta *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="b3542-141">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="b3542-142">En el Explorador de soluciones, haga clic con el botón derecho en el archivo del modelo precompilado y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b3542-142">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="b3542-143">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="b3542-143">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="b3542-144">Creación de una función de Azure para analizar sentimientos</span><span class="sxs-lookup"><span data-stu-id="b3542-144">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="b3542-145">Cree una clase para predecir sentimientos.</span><span class="sxs-lookup"><span data-stu-id="b3542-145">Create a class to predict sentiment.</span></span> <span data-ttu-id="b3542-146">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="b3542-146">Add a new class to your project:</span></span>

1. <span data-ttu-id="b3542-147">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b3542-147">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="b3542-148">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Función de Azure** y cambie el campo **Nombre** a *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="b3542-148">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="b3542-149">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b3542-149">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="b3542-150">En el cuadro de diálogo **Nueva función de Azure**, seleccione **Desencadenador HTTP**.</span><span class="sxs-lookup"><span data-stu-id="b3542-150">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="b3542-151">Luego haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b3542-151">Then, select the **OK** button.</span></span>

    <span data-ttu-id="b3542-152">El archivo *AnalyzeSentiment.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="b3542-152">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="b3542-153">Agregue la siguiente instrucción `using` a la parte superior de *AnalyzeSentiment.cs*:</span><span class="sxs-lookup"><span data-stu-id="b3542-153">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

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

    <span data-ttu-id="b3542-154">De forma predeterminada, la clase `AnalyzeSentiment` es `static`.</span><span class="sxs-lookup"><span data-stu-id="b3542-154">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="b3542-155">Asegúrese de quitar la palabra clave `static` de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="b3542-155">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="b3542-156">Creación de modelos de datos</span><span class="sxs-lookup"><span data-stu-id="b3542-156">Create data models</span></span>

<span data-ttu-id="b3542-157">Debe crear algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="b3542-157">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="b3542-158">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="b3542-158">Add a new class to your project:</span></span>

1. <span data-ttu-id="b3542-159">Cree un directorio denominado *DataModels* en el proyecto para guardar los modelos de datos: En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="b3542-159">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="b3542-160">Escriba "DataModels" y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b3542-160">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="b3542-161">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b3542-161">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="b3542-162">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="b3542-162">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="b3542-163">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b3542-163">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="b3542-164">Se abre el archivo *SentimentData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="b3542-164">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="b3542-165">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="b3542-165">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="b3542-166">Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="b3542-166">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
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

4. <span data-ttu-id="b3542-167">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b3542-167">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="b3542-168">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="b3542-168">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="b3542-169">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b3542-169">Then, select the **Add** button.</span></span> <span data-ttu-id="b3542-170">El archivo *SentimentPrediction.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="b3542-170">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="b3542-171">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="b3542-171">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="b3542-172">Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="b3542-172">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="b3542-173">`SentimentPrediction` hereda de `SentimentData` el cual proporciona acceso a los datos originales en la propiedad `SentimentText`, así como la salida generada por el modelo.</span><span class="sxs-lookup"><span data-stu-id="b3542-173">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="b3542-174">Registro del servicio PredictionEnginePool</span><span class="sxs-lookup"><span data-stu-id="b3542-174">Register PredictionEnginePool service</span></span>

<span data-ttu-id="b3542-175">Para realizar una sola predicción, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="b3542-175">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="b3542-176">Para poder usar [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) en la aplicación, debe crearlo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b3542-176">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="b3542-177">En ese caso, un procedimiento recomendado que se debe considerar es la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="b3542-177">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="b3542-178">En el vínculo siguiente se proporciona más información si quiere aprender sobre la [inserción de dependencias](https://en.wikipedia.org/wiki/Dependency_injection).</span><span class="sxs-lookup"><span data-stu-id="b3542-178">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="b3542-179">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b3542-179">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="b3542-180">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="b3542-180">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="b3542-181">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b3542-181">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="b3542-182">Se abre el archivo *Startup.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="b3542-182">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="b3542-183">Agregue la instrucción using siguiente en la parte superior del archivo *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="b3542-183">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.Functions.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="b3542-184">Quite el código existente debajo de las instrucciones using y agregue el código siguiente al archivo *Startup.cs*:</span><span class="sxs-lookup"><span data-stu-id="b3542-184">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

    ```csharp
    [assembly: FunctionsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        public class Startup : FunctionsStartup
        {
            public override void Configure(IFunctionsHostBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile("MLModels/sentiment_model.zip");
            }
        }
    }
    ```

<span data-ttu-id="b3542-185">En un nivel alto, este código inicializa los objetos y servicios de manera automática cuando lo solicita la aplicación en lugar de tener que hacerlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="b3542-185">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="b3542-186">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="b3542-186">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="b3542-187">Para mejorar el rendimiento y la seguridad para subprocesos, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos `PredictionEngine` para el uso de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b3542-187">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="b3542-188">Carga del modelo en la función</span><span class="sxs-lookup"><span data-stu-id="b3542-188">Load the model into the function</span></span>

<span data-ttu-id="b3542-189">Inserte el código siguiente dentro de la clase *AnalyzeSentiment*:</span><span class="sxs-lookup"><span data-stu-id="b3542-189">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="b3542-190">Este código asigna `PredictionEnginePool` al pasarlo al constructor de la función que se obtiene a través de una inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="b3542-190">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="b3542-191">Uso del modelo para realizar predicciones</span><span class="sxs-lookup"><span data-stu-id="b3542-191">Use the model to make predictions</span></span>

<span data-ttu-id="b3542-192">Reemplace la implementación existente del método *Run* en la clase *AnalyzeSentiment* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3542-192">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

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

<span data-ttu-id="b3542-193">Cuando se ejecuta el método `Run`, los datos entrantes de la solicitud HTTP se deserializan y se usan como entrada en el `PredictionEnginePool`.</span><span class="sxs-lookup"><span data-stu-id="b3542-193">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="b3542-194">A continuación, se llama al método `Predict` para generar una predicción y devolver el resultado al usuario.</span><span class="sxs-lookup"><span data-stu-id="b3542-194">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="b3542-195">Prueba local</span><span class="sxs-lookup"><span data-stu-id="b3542-195">Test locally</span></span>

<span data-ttu-id="b3542-196">Ahora que está todo configurado, es momento de probar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b3542-196">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="b3542-197">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="b3542-197">Run the application</span></span>
1. <span data-ttu-id="b3542-198">Abra PowerShell y escriba el código en el símbolo del sistema, donde PORT es el puerto en que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b3542-198">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="b3542-199">Por lo general, se trata del puerto 7071.</span><span class="sxs-lookup"><span data-stu-id="b3542-199">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="b3542-200">Si se realiza correctamente, la salida debería ser similar al texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3542-200">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="b3542-201">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="b3542-201">Congratulations!</span></span> <span data-ttu-id="b3542-202">Publicó correctamente el modelo para realizar predicciones en Internet mediante una función de Azure.</span><span class="sxs-lookup"><span data-stu-id="b3542-202">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3542-203">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b3542-203">Next Steps</span></span>

- [<span data-ttu-id="b3542-204">Implementación en Azure</span><span class="sxs-lookup"><span data-stu-id="b3542-204">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)

---
title: Implementación del modelo ML.NET en Azure Functions
description: Publicación del modelo de Machine Learning de Análisis de sentimiento de ML.NET para la predicción en Internet a través de Azure Functions
ms.date: 03/08/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4681b37da64097dd8e537b4c956917277ecff96b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330641"
---
# <a name="how-to-use-mlnet-model-in-azure-functions"></a><span data-ttu-id="9f83d-103">Uso del modelo de ML.NET en Azure Functions</span><span class="sxs-lookup"><span data-stu-id="9f83d-103">How-To: Use ML.NET Model in Azure Functions</span></span>

<span data-ttu-id="9f83d-104">En esta guía se muestra cómo se pueden hacer predicciones individuales mediante un modelo de Machine Learning de ML.NET precompilado a través de Internet en un entorno sin servidor como Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="9f83d-104">This how-to shows how individual predictions can be made using a pre-built ML.NET machine learning model through the internet in a serverless environment such as Azure Functions.</span></span>

> [!NOTE]
> <span data-ttu-id="9f83d-105">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="9f83d-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="9f83d-106">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="9f83d-106">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="9f83d-107">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-107">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="9f83d-108">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="9f83d-108">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9f83d-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9f83d-109">Prerequisites</span></span>

- <span data-ttu-id="9f83d-110">[Visual Studio 2017 15.6 o versión posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" y el "desarrollo de Azure" instalados.</span><span class="sxs-lookup"><span data-stu-id="9f83d-110">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span> 
- [<span data-ttu-id="9f83d-111">Herramientas de Azure Functions</span><span class="sxs-lookup"><span data-stu-id="9f83d-111">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="9f83d-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f83d-112">Powershell</span></span>
- <span data-ttu-id="9f83d-113">Modelo previamente entrenado.</span><span class="sxs-lookup"><span data-stu-id="9f83d-113">Pre-trained model.</span></span> 
    - <span data-ttu-id="9f83d-114">Use el [tutorial de Análisis de sentimiento de ML.NET](../tutorials/sentiment-analysis.md) para compilar su propio modelo.</span><span class="sxs-lookup"><span data-stu-id="9f83d-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="9f83d-115">Descargue este [modelo de Machine Learning de Análisis de sentimiento previamente entrenado](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).</span><span class="sxs-lookup"><span data-stu-id="9f83d-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="9f83d-116">Creación de un proyecto de Azure Functions</span><span class="sxs-lookup"><span data-stu-id="9f83d-116">Create Azure Functions Project</span></span>

1. <span data-ttu-id="9f83d-117">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="9f83d-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="9f83d-118">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="9f83d-118">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="9f83d-119">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **Cloud**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-119">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="9f83d-120">A continuación, seleccione la plantilla de proyecto **Azure Functions**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-120">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="9f83d-121">En el cuadro de texto **Nombre**, escriba "SentimentAnalysisFunctionsApp" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-121">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="9f83d-122">En el cuadro de diálogo **Nuevo proyecto**, abra el menú desplegable que se encuentra sobre las opciones del proyecto y seleccione **Azure Functions v2 (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-122">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="9f83d-123">Luego, seleccione el proyecto **Desencadenador HTTP** y luego haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-123">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="9f83d-124">En el proyecto, cree un directorio denominado *MLModels* para guardar el modelo:</span><span class="sxs-lookup"><span data-stu-id="9f83d-124">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="9f83d-125">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="9f83d-126">Escriba "MLModels" y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="9f83d-126">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="9f83d-127">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="9f83d-127">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="9f83d-128">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="9f83d-129">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="9f83d-130">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="9f83d-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-built-model-to-project"></a><span data-ttu-id="9f83d-131">Incorporación del modelo precompilado en el proyecto</span><span class="sxs-lookup"><span data-stu-id="9f83d-131">Add Pre-built Model To Project</span></span>

1. <span data-ttu-id="9f83d-132">Copie el modelo precompilado en la carpeta *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="9f83d-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="9f83d-133">En el Explorador de soluciones, haga clic con el botón derecho en el archivo del modelo precompilado y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="9f83d-134">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-function-to-analyze-sentiment"></a><span data-ttu-id="9f83d-135">Creación de una función para analizar sentimientos</span><span class="sxs-lookup"><span data-stu-id="9f83d-135">Create Function to Analyze Sentiment</span></span>

<span data-ttu-id="9f83d-136">Cree una clase para predecir sentimientos.</span><span class="sxs-lookup"><span data-stu-id="9f83d-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="9f83d-137">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="9f83d-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="9f83d-138">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="9f83d-139">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Función de Azure** y cambie el campo **Nombre** a *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="9f83d-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="9f83d-140">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="9f83d-141">En el cuadro de diálogo **Nueva función de Azure**, seleccione **Desencadenador HTTP**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="9f83d-142">Luego haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="9f83d-143">El archivo *AnalyzeSentiment.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="9f83d-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="9f83d-144">Agregue la siguiente instrucción `using` a la parte superior de *GitHubIssueData.cs*:</span><span class="sxs-lookup"><span data-stu-id="9f83d-144">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

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
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using Microsoft.ML.Data;
using MLNETServerless.DataModels;
```

### <a name="create-data-models"></a><span data-ttu-id="9f83d-145">Creación de modelos de datos</span><span class="sxs-lookup"><span data-stu-id="9f83d-145">Create Data Models</span></span>

<span data-ttu-id="9f83d-146">Debe crear algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="9f83d-146">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="9f83d-147">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="9f83d-147">Add a new class to your project:</span></span>

1. <span data-ttu-id="9f83d-148">Cree un directorio denominado *DataModels* en el proyecto para guardar los modelos de datos: En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-148">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="9f83d-149">Escriba "DataModels" y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="9f83d-149">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="9f83d-150">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-150">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="9f83d-151">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="9f83d-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="9f83d-152">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-152">Then, select the **Add** button.</span></span> <span data-ttu-id="9f83d-153">Se abre el archivo *SentimentData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="9f83d-153">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="9f83d-154">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="9f83d-154">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="9f83d-155">Quite la definición de clase existente y agregue el código siguiente al archivo SentimentData.cs:</span><span class="sxs-lookup"><span data-stu-id="9f83d-155">Remove the existing class definition and add the following code to the SentimentData.cs file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }
}
```

4. <span data-ttu-id="9f83d-156">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-156">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="9f83d-157">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="9f83d-157">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="9f83d-158">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9f83d-158">Then, select the **Add** button.</span></span> <span data-ttu-id="9f83d-159">El archivo *SentimentPrediction.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="9f83d-159">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="9f83d-160">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="9f83d-160">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="9f83d-161">Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="9f83d-161">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

### <a name="add-prediction-logic"></a><span data-ttu-id="9f83d-162">Incorporación de la lógica de predicción</span><span class="sxs-lookup"><span data-stu-id="9f83d-162">Add Prediction Logic</span></span>

<span data-ttu-id="9f83d-163">Reemplace la implementación existente del método *Run* en la clase *AnalyzeSentiment* por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9f83d-163">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
    public static async Task<IActionResult> Run(
        [HttpTrigger(AuthorizationLevel.Function,"post", Route = null)] HttpRequest req,
        ILogger log)
    {
        log.LogInformation("C# HTTP trigger function processed a request.");

        //Create Context
        MLContext mlContext = new MLContext();

        //Load Model
        using (var fs = File.OpenRead("MLModels/sentiment_model.zip"))
        {
            model = mlContext.Model.Load(fs);
        }

        //Parse HTTP Request Body
        string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
        SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

        //Create Prediction Engine
        PredictionEngine<SentimentData, SentimentPrediction> predictionEngine = model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);

        //Make Prediction
        SentimentPrediction prediction = predictionEngine.Predict(data);

        //Convert prediction to string
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        //Return Prediction
        return (ActionResult)new OkObjectResult(isToxic);
    }
}
```

## <a name="test-locally"></a><span data-ttu-id="9f83d-164">Prueba local</span><span class="sxs-lookup"><span data-stu-id="9f83d-164">Test Locally</span></span>

<span data-ttu-id="9f83d-165">Ahora que está todo configurado, es momento de probar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="9f83d-165">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="9f83d-166">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="9f83d-166">Run the application</span></span>
1. <span data-ttu-id="9f83d-167">Abra PowerShell y escriba el código en el símbolo del sistema, donde PORT es el puerto en que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9f83d-167">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="9f83d-168">Por lo general, se trata del puerto 7071.</span><span class="sxs-lookup"><span data-stu-id="9f83d-168">Typically the port is 7071.</span></span> 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="9f83d-169">Si se realiza correctamente, la salida debería ser similar al texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="9f83d-169">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="9f83d-170">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="9f83d-170">Congratulations!</span></span> <span data-ttu-id="9f83d-171">Publicó correctamente el modelo para realizar predicciones en Internet mediante una función de Azure.</span><span class="sxs-lookup"><span data-stu-id="9f83d-171">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9f83d-172">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9f83d-172">Next Steps</span></span>

- [<span data-ttu-id="9f83d-173">Implementación en Azure</span><span class="sxs-lookup"><span data-stu-id="9f83d-173">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
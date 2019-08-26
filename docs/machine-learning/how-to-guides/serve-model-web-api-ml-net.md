---
title: Implementación de un modelo en una ASP.NET Core Web API
description: Publicación del modelo de Machine Learning de Análisis de sentimiento de ML.NET en Internet mediante ASP.NET Core Web API
ms.date: 08/20/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: e1dcc719738a2beb3e63463245d4721c5298cf85
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666662"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="aaf67-103">Implementación de un modelo en una ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="aaf67-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="aaf67-104">Aprenda cómo publicar un modelo de Machine Learning de ML.NET entrenado previamente en la Web a través de una ASP.NET Core Web API.</span><span class="sxs-lookup"><span data-stu-id="aaf67-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="aaf67-105">Publicar un modelo a través de una API web permite predicciones mediante métodos HTTP estándar.</span><span class="sxs-lookup"><span data-stu-id="aaf67-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="aaf67-106">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="aaf67-106">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aaf67-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aaf67-107">Prerequisites</span></span>

- <span data-ttu-id="aaf67-108">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="aaf67-108">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="aaf67-109">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aaf67-109">Powershell.</span></span>
- <span data-ttu-id="aaf67-110">Modelo previamente entrenado.</span><span class="sxs-lookup"><span data-stu-id="aaf67-110">Pre-trained model.</span></span> <span data-ttu-id="aaf67-111">Use el [tutorial de análisis de sentimiento de ML.NET](../tutorials/sentiment-analysis.md) para generar su propio modelo o descargue este [modelo de Machine Learning de análisis de sentimiento entrenado previamente](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).</span><span class="sxs-lookup"><span data-stu-id="aaf67-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="aaf67-112">Creación de un proyecto de ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="aaf67-112">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="aaf67-113">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="aaf67-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="aaf67-114">Seleccione **Archivo > Nuevo > Proyecto** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="aaf67-114">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="aaf67-115">En el cuadro de diálogo Nuevo proyecto, seleccione el nodo **Visual C#** seguido del nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="aaf67-115">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="aaf67-116">Seleccione la plantilla de proyecto **Aplicación web de ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="aaf67-116">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="aaf67-117">En el cuadro de texto **Nombre**, escriba "SentimentAnalysisWebAPI" y haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aaf67-117">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="aaf67-118">En la ventana que muestra los distintos tipos de proyectos de ASP.NET Core, seleccione **API** y haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aaf67-118">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="aaf67-119">Cree un directorio denominado *MLModels* en el proyecto para guardar los archivos del modelo de Machine Learning precompilado:</span><span class="sxs-lookup"><span data-stu-id="aaf67-119">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="aaf67-120">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione Agregar > Nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="aaf67-120">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="aaf67-121">Escriba "MLModels" y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="aaf67-121">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="aaf67-122">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="aaf67-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="aaf67-123">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="aaf67-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="aaf67-124">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón Instalar.</span><span class="sxs-lookup"><span data-stu-id="aaf67-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="aaf67-125">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo Aceptación de la licencia en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="aaf67-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="aaf67-126">Instale el **paquete NuGet Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="aaf67-126">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="aaf67-127">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="aaf67-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="aaf67-128">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.Extensions.ML**, seleccione ese paquete en la lista y haga clic en el botón "Instalar".</span><span class="sxs-lookup"><span data-stu-id="aaf67-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="aaf67-129">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo Aceptación de la licencia en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="aaf67-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="aaf67-130">Incorporación del modelo a un proyecto de ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="aaf67-130">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="aaf67-131">Copie el modelo precompilado al directorio *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="aaf67-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="aaf67-132">En el Explorador de soluciones, haga clic con el botón derecho en el archivo ZIP del modelo y seleccione Propiedades.</span><span class="sxs-lookup"><span data-stu-id="aaf67-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="aaf67-133">En Avanzadas, cambie el valor de Copiar en el directorio de salida por Copiar si es posterior.</span><span class="sxs-lookup"><span data-stu-id="aaf67-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="aaf67-134">Creación de modelos de datos</span><span class="sxs-lookup"><span data-stu-id="aaf67-134">Create data models</span></span>

<span data-ttu-id="aaf67-135">Debe crear algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="aaf67-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="aaf67-136">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="aaf67-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="aaf67-137">Cree un directorio denominado *DataModels* en el proyecto para guardar los modelos de datos:</span><span class="sxs-lookup"><span data-stu-id="aaf67-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="aaf67-138">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione Agregar > Nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="aaf67-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="aaf67-139">Escriba "DataModels" y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="aaf67-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="aaf67-140">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione Agregar > Nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="aaf67-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="aaf67-141">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="aaf67-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="aaf67-142">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="aaf67-142">Then, select the **Add** button.</span></span> <span data-ttu-id="aaf67-143">Se abre el archivo *SentimentData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="aaf67-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="aaf67-144">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="aaf67-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="aaf67-145">Quite la definición de clase existente y agregue el código siguiente al archivo **SentimentData.cs**:</span><span class="sxs-lookup"><span data-stu-id="aaf67-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>
    
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

4. <span data-ttu-id="aaf67-146">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="aaf67-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="aaf67-147">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="aaf67-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="aaf67-148">Luego, haga clic en el botón Agregar.</span><span class="sxs-lookup"><span data-stu-id="aaf67-148">Then, select the Add button.</span></span> <span data-ttu-id="aaf67-149">El archivo *SentimentPrediction.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="aaf67-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="aaf67-150">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="aaf67-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="aaf67-151">Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="aaf67-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>
    
    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="aaf67-152">`SentimentPrediction` hereda de `SentimentData`.</span><span class="sxs-lookup"><span data-stu-id="aaf67-152">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="aaf67-153">Así resulta más fácil ver los datos originales en la propiedad `SentimentText` junto con la salida generada por el modelo.</span><span class="sxs-lookup"><span data-stu-id="aaf67-153">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span> 

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="aaf67-154">Registro de PredictionEngine para usarlo en la aplicación</span><span class="sxs-lookup"><span data-stu-id="aaf67-154">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="aaf67-155">Para realizar una sola predicción, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="aaf67-155">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="aaf67-156">Para poder usar [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) en la aplicación, debe crearlo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="aaf67-156">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="aaf67-157">En ese caso, un procedimiento recomendado que se debe considerar es la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="aaf67-157">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="aaf67-158">En el vínculo siguiente se proporciona más información si quiere aprender sobre la [inserción de dependencias en ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="aaf67-158">The following link provides more information if you want to learn about [dependency injection in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="aaf67-159">Abra la clase *Startup.cs* y agregue la siguiente instrucción using en la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="aaf67-159">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="aaf67-160">Agregue el código siguiente al método *ConfigureServices*:</span><span class="sxs-lookup"><span data-stu-id="aaf67-160">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile("MLModels/sentiment_model.zip");
    }
    ```

<span data-ttu-id="aaf67-161">En un nivel alto, este código inicializa los objetos y servicios de manera automática cuando lo solicita la aplicación en lugar de tener que hacerlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="aaf67-161">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="aaf67-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="aaf67-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="aaf67-163">Para mejorar el rendimiento y la seguridad para subprocesos, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos `PredictionEngine` para el uso de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aaf67-163">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> <span data-ttu-id="aaf67-164">Lea la siguiente entrada de blog para obtener más información acerca de la [creación y el uso de grupos de objetos `PredictionEngine` en ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span><span class="sxs-lookup"><span data-stu-id="aaf67-164">Read the following blog post to learn more about [creating and using `PredictionEngine` object pools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span>  

## <a name="create-predict-controller"></a><span data-ttu-id="aaf67-165">Creación de controlador de predicción</span><span class="sxs-lookup"><span data-stu-id="aaf67-165">Create Predict controller</span></span>

<span data-ttu-id="aaf67-166">Para procesar las solicitudes HTTP entrantes, cree un controlador.</span><span class="sxs-lookup"><span data-stu-id="aaf67-166">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="aaf67-167">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *Controladores* y seleccione **Agregar > Controlador**.</span><span class="sxs-lookup"><span data-stu-id="aaf67-167">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="aaf67-168">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **API Controller Empty** (Controlador de API vacío) y seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="aaf67-168">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="aaf67-169">En el símbolo del sistema, cambie el campo **Nombre del controlador** a *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="aaf67-169">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="aaf67-170">Luego, haga clic en el botón Agregar.</span><span class="sxs-lookup"><span data-stu-id="aaf67-170">Then, select the Add button.</span></span> <span data-ttu-id="aaf67-171">El archivo *PredictController.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="aaf67-171">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="aaf67-172">Agregue la instrucción using siguiente en la parte superior del archivo *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="aaf67-172">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="aaf67-173">Quite la definición de clase existente y agregue el código siguiente al archivo *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="aaf67-173">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>
    
    ```csharp
    public class PredictController : ControllerBase
    {
        private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

        public PredictController(PredictionEnginePool<SentimentData,SentimentPrediction> predictionEnginePool)
        {
            _predictionEnginePool = predictionEnginePool;
        }

        [HttpPost]
        public ActionResult<string> Post([FromBody] SentimentData input)
        {
            if(!ModelState.IsValid)
            {
                return BadRequest();
            }

            SentimentPrediction prediction = _predictionEnginePool.Predict(input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

<span data-ttu-id="aaf67-174">Este código asigna `PredictionEnginePool` al pasarlo al constructor del controlador que se obtiene a través de una inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="aaf67-174">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="aaf67-175">Después, el método `Post` del controlador `Predict` usa `PredictionEnginePool` para hacer predicciones y devolver los resultados al usuario si la operación se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="aaf67-175">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="aaf67-176">Prueba local de Web API</span><span class="sxs-lookup"><span data-stu-id="aaf67-176">Test web API locally</span></span>

<span data-ttu-id="aaf67-177">Una vez que todo está configurado, es momento de probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aaf67-177">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="aaf67-178">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aaf67-178">Run the application.</span></span>
1. <span data-ttu-id="aaf67-179">Abra PowerShell y escriba el código siguiente, donde PORT es el puerto donde escuchar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aaf67-179">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="aaf67-180">Si se realiza correctamente, la salida debería ser similar al texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaf67-180">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="aaf67-181">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="aaf67-181">Congratulations!</span></span> <span data-ttu-id="aaf67-182">Publicó correctamente el modelo para realizar predicciones en Internet mediante una ASP.NET Core Web API.</span><span class="sxs-lookup"><span data-stu-id="aaf67-182">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aaf67-183">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="aaf67-183">Next Steps</span></span>

- [<span data-ttu-id="aaf67-184">Implementación en Azure</span><span class="sxs-lookup"><span data-stu-id="aaf67-184">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)

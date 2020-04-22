---
title: Implementación de un modelo en una ASP.NET Core Web API
description: Publicación del modelo de Machine Learning de Análisis de sentimiento de ML.NET en Internet mediante ASP.NET Core Web API
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: 3f1ca48ab29b04931961b52743bb6c7fab70b06d
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608080"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="c52cc-103">Implementación de un modelo en una ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="c52cc-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="c52cc-104">Aprenda cómo publicar un modelo de Machine Learning de ML.NET entrenado previamente en la Web a través de una ASP.NET Core Web API.</span><span class="sxs-lookup"><span data-stu-id="c52cc-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="c52cc-105">Publicar un modelo a través de una API web permite predicciones mediante métodos HTTP estándar.</span><span class="sxs-lookup"><span data-stu-id="c52cc-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c52cc-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c52cc-106">Prerequisites</span></span>

- <span data-ttu-id="c52cc-107">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="c52cc-107">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="c52cc-108">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c52cc-108">Powershell.</span></span>
- <span data-ttu-id="c52cc-109">Modelo previamente entrenado.</span><span class="sxs-lookup"><span data-stu-id="c52cc-109">Pre-trained model.</span></span> <span data-ttu-id="c52cc-110">Use el [tutorial de análisis de sentimiento de ML.NET](../tutorials/sentiment-analysis.md) para generar su propio modelo o descargue este [modelo de Machine Learning de análisis de sentimiento entrenado previamente](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).</span><span class="sxs-lookup"><span data-stu-id="c52cc-110">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="c52cc-111">Creación de un proyecto de ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="c52cc-111">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="c52cc-112">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="c52cc-112">Open Visual Studio 2017.</span></span> <span data-ttu-id="c52cc-113">Seleccione **Archivo > Nuevo > Proyecto** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="c52cc-113">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="c52cc-114">En el cuadro de diálogo Nuevo proyecto, seleccione el nodo **Visual C#** seguido del nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="c52cc-114">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="c52cc-115">Seleccione la plantilla de proyecto **Aplicación web de ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="c52cc-115">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="c52cc-116">En el cuadro de texto **Nombre**, escriba "SentimentAnalysisWebAPI" y haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c52cc-116">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="c52cc-117">En la ventana que muestra los distintos tipos de proyectos de ASP.NET Core, seleccione **API** y haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c52cc-117">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="c52cc-118">Cree un directorio denominado *MLModels* en el proyecto para guardar los archivos del modelo de Machine Learning precompilado:</span><span class="sxs-lookup"><span data-stu-id="c52cc-118">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="c52cc-119">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione Agregar > Nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="c52cc-119">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="c52cc-120">Escriba "MLModels" y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="c52cc-120">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="c52cc-121">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="c52cc-121">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="c52cc-122">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="c52cc-122">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="c52cc-123">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón Instalar.</span><span class="sxs-lookup"><span data-stu-id="c52cc-123">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="c52cc-124">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo Aceptación de la licencia en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="c52cc-124">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="c52cc-125">Instale el **paquete NuGet Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="c52cc-125">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="c52cc-126">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="c52cc-126">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="c52cc-127">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.Extensions.ML**, seleccione ese paquete en la lista y haga clic en el botón "Instalar".</span><span class="sxs-lookup"><span data-stu-id="c52cc-127">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="c52cc-128">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo Aceptación de la licencia en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="c52cc-128">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="c52cc-129">Incorporación del modelo a un proyecto de ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="c52cc-129">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="c52cc-130">Copie el modelo precompilado al directorio *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="c52cc-130">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="c52cc-131">En el Explorador de soluciones, haga clic con el botón derecho en el archivo ZIP del modelo y seleccione Propiedades.</span><span class="sxs-lookup"><span data-stu-id="c52cc-131">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="c52cc-132">En Avanzadas, cambie el valor de Copiar en el directorio de salida por Copiar si es posterior.</span><span class="sxs-lookup"><span data-stu-id="c52cc-132">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="c52cc-133">Creación de modelos de datos</span><span class="sxs-lookup"><span data-stu-id="c52cc-133">Create data models</span></span>

<span data-ttu-id="c52cc-134">Debe crear algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="c52cc-134">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="c52cc-135">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="c52cc-135">Add a new class to your project:</span></span>

1. <span data-ttu-id="c52cc-136">Cree un directorio denominado *DataModels* en el proyecto para guardar los modelos de datos:</span><span class="sxs-lookup"><span data-stu-id="c52cc-136">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="c52cc-137">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione Agregar > Nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="c52cc-137">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="c52cc-138">Escriba "DataModels" y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="c52cc-138">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="c52cc-139">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione Agregar > Nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="c52cc-139">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="c52cc-140">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="c52cc-140">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="c52cc-141">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c52cc-141">Then, select the **Add** button.</span></span> <span data-ttu-id="c52cc-142">Se abre el archivo *SentimentData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="c52cc-142">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="c52cc-143">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="c52cc-143">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="c52cc-144">Quite la definición de clase existente y agregue el código siguiente al archivo **SentimentData.cs**:</span><span class="sxs-lookup"><span data-stu-id="c52cc-144">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

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

4. <span data-ttu-id="c52cc-145">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="c52cc-145">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="c52cc-146">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="c52cc-146">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="c52cc-147">Luego, haga clic en el botón Agregar.</span><span class="sxs-lookup"><span data-stu-id="c52cc-147">Then, select the Add button.</span></span> <span data-ttu-id="c52cc-148">El archivo *SentimentPrediction.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="c52cc-148">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="c52cc-149">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="c52cc-149">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="c52cc-150">Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="c52cc-150">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="c52cc-151">`SentimentPrediction` hereda de `SentimentData`.</span><span class="sxs-lookup"><span data-stu-id="c52cc-151">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="c52cc-152">Así resulta más fácil ver los datos originales en la propiedad `SentimentText` junto con la salida generada por el modelo.</span><span class="sxs-lookup"><span data-stu-id="c52cc-152">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span>

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="c52cc-153">Registro de PredictionEngine para usarlo en la aplicación</span><span class="sxs-lookup"><span data-stu-id="c52cc-153">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="c52cc-154">Para hacer una sola predicción, debe crear un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="c52cc-154">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="c52cc-155">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c52cc-155">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="c52cc-156">Además, tiene que crear una instancia de ella en cualquier lugar en que se necesite dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c52cc-156">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="c52cc-157">A medida que crece la aplicación, este proceso puede volverse difícil de administrar.</span><span class="sxs-lookup"><span data-stu-id="c52cc-157">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="c52cc-158">Para mejorar el rendimiento y la seguridad para subprocesos, use una combinación de inserción de dependencias y el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c52cc-158">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="c52cc-159">En el vínculo siguiente se proporciona más información si quiere aprender sobre la [inserción de dependencias en ASP.NET Core](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="c52cc-159">The following link provides more information if you want to learn more about [dependency injection in ASP.NET Core](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="c52cc-160">Abra la clase *Startup.cs* y agregue la siguiente instrucción using en la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="c52cc-160">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="c52cc-161">Agregue el código siguiente al método *ConfigureServices*:</span><span class="sxs-lookup"><span data-stu-id="c52cc-161">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
        .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
    ```

<span data-ttu-id="c52cc-162">En un nivel alto, este código inicializa los objetos y servicios de manera automática para su uso más adelante cuando lo solicite la aplicación en lugar de tener que hacerlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="c52cc-162">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span>

<span data-ttu-id="c52cc-163">Los modelos de Machine Learning no son estáticos.</span><span class="sxs-lookup"><span data-stu-id="c52cc-163">Machine learning models are not static.</span></span> <span data-ttu-id="c52cc-164">A medida que haya nuevos datos de entrenamiento disponibles, el modelo se vuelve a entrenar y a implementar.</span><span class="sxs-lookup"><span data-stu-id="c52cc-164">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="c52cc-165">Una manera de obtener la versión más reciente del modelo en la aplicación es volver a implementar toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c52cc-165">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="c52cc-166">Sin embargo, esto implica un tiempo de inactividad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c52cc-166">However, this introduces application downtime.</span></span> <span data-ttu-id="c52cc-167">El servicio `PredictionEnginePool` proporciona un mecanismo para volver a cargar un modelo actualizado sin dejar inactiva su aplicación.</span><span class="sxs-lookup"><span data-stu-id="c52cc-167">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span>

<span data-ttu-id="c52cc-168">Establezca el parámetro `watchForChanges` en `true` y el `PredictionEnginePool` inicia un [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) que escucha las notificaciones de cambios en el sistema de archivos y genera eventos cuando se produce un cambio en el archivo.</span><span class="sxs-lookup"><span data-stu-id="c52cc-168">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="c52cc-169">Este solicita al `PredictionEnginePool` que vuelva a cargar automáticamente el modelo.</span><span class="sxs-lookup"><span data-stu-id="c52cc-169">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="c52cc-170">El modelo se identifica mediante el parámetro `modelName`, por lo que se puede volver a cargar más de un modelo por aplicación tras el cambio.</span><span class="sxs-lookup"><span data-stu-id="c52cc-170">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span>

> [!TIP]
> <span data-ttu-id="c52cc-171">Como alternativa, puede usar el método `FromUri` al trabajar con modelos almacenados de manera remota.</span><span class="sxs-lookup"><span data-stu-id="c52cc-171">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="c52cc-172">En lugar de ver si hay eventos modificados de archivo, `FromUri` sondea la ubicación remota en busca de cambios.</span><span class="sxs-lookup"><span data-stu-id="c52cc-172">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="c52cc-173">El intervalo de sondeo predeterminado es de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="c52cc-173">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="c52cc-174">Puede aumentar o disminuir el intervalo de sondeo en función de los requisitos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c52cc-174">You can increase or decrease the polling interval based on your application's requirements.</span></span> <span data-ttu-id="c52cc-175">En el ejemplo de código siguiente, `PredictionEnginePool` sondea el modelo almacenado en el URI especificado cada minuto.</span><span class="sxs-lookup"><span data-stu-id="c52cc-175">In the code sample below, the `PredictionEnginePool` polls the model stored at the specified URI every minute.</span></span>
>
>```csharp
>services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="create-predict-controller"></a><span data-ttu-id="c52cc-176">Creación de controlador de predicción</span><span class="sxs-lookup"><span data-stu-id="c52cc-176">Create Predict controller</span></span>

<span data-ttu-id="c52cc-177">Para procesar las solicitudes HTTP entrantes, cree un controlador.</span><span class="sxs-lookup"><span data-stu-id="c52cc-177">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="c52cc-178">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *Controladores* y seleccione **Agregar > Controlador**.</span><span class="sxs-lookup"><span data-stu-id="c52cc-178">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="c52cc-179">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **API Controller Empty** (Controlador de API vacío) y seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c52cc-179">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="c52cc-180">En el símbolo del sistema, cambie el campo **Nombre del controlador** a *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="c52cc-180">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="c52cc-181">Luego, haga clic en el botón Agregar.</span><span class="sxs-lookup"><span data-stu-id="c52cc-181">Then, select the Add button.</span></span> <span data-ttu-id="c52cc-182">El archivo *PredictController.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="c52cc-182">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="c52cc-183">Agregue la instrucción using siguiente en la parte superior del archivo *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="c52cc-183">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="c52cc-184">Quite la definición de clase existente y agregue el código siguiente al archivo *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="c52cc-184">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

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

            SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

<span data-ttu-id="c52cc-185">Este código asigna `PredictionEnginePool` al pasarlo al constructor del controlador que se obtiene a través de una inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="c52cc-185">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="c52cc-186">Luego, el método `Post` del controlador `Predict` usa `PredictionEnginePool` para hacer predicciones con el `SentimentAnalysisModel` registrado en la clase `Startup` y devuelve los resultados al usuario si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="c52cc-186">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="c52cc-187">Prueba local de Web API</span><span class="sxs-lookup"><span data-stu-id="c52cc-187">Test web API locally</span></span>

<span data-ttu-id="c52cc-188">Una vez que todo está configurado, es momento de probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c52cc-188">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="c52cc-189">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c52cc-189">Run the application.</span></span>
1. <span data-ttu-id="c52cc-190">Abra PowerShell y escriba el código siguiente, donde PORT es el puerto donde escuchar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c52cc-190">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="c52cc-191">Si se realiza correctamente, la salida debería ser similar al texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="c52cc-191">If successful, the output should look similar to the text below:</span></span>

    ```powershell
    Negative
    ```

<span data-ttu-id="c52cc-192">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="c52cc-192">Congratulations!</span></span> <span data-ttu-id="c52cc-193">Publicó correctamente el modelo para realizar predicciones en Internet mediante una ASP.NET Core Web API.</span><span class="sxs-lookup"><span data-stu-id="c52cc-193">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c52cc-194">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c52cc-194">Next Steps</span></span>

- [<span data-ttu-id="c52cc-195">Implementación en Azure</span><span class="sxs-lookup"><span data-stu-id="c52cc-195">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)

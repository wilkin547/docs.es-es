---
title: Implementación de un modelo en una ASP.NET Core Web API
description: Publicación del modelo de Machine Learning de Análisis de sentimiento de ML.NET en Internet mediante ASP.NET Core Web API
ms.date: 09/11/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: b85d77900c5d9227ecc6fe81b8a8d68171dd9ef5
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774519"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="f9701-103">Implementación de un modelo en una ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="f9701-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="f9701-104">Aprenda cómo publicar un modelo de Machine Learning de ML.NET entrenado previamente en la Web a través de una ASP.NET Core Web API.</span><span class="sxs-lookup"><span data-stu-id="f9701-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="f9701-105">Publicar un modelo a través de una API web permite predicciones mediante métodos HTTP estándar.</span><span class="sxs-lookup"><span data-stu-id="f9701-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="f9701-106">La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="f9701-106">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f9701-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f9701-107">Prerequisites</span></span>

- <span data-ttu-id="f9701-108">[Visual Studio 2017, versión 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="f9701-108">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="f9701-109">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9701-109">Powershell.</span></span>
- <span data-ttu-id="f9701-110">Modelo previamente entrenado.</span><span class="sxs-lookup"><span data-stu-id="f9701-110">Pre-trained model.</span></span> <span data-ttu-id="f9701-111">Use el [tutorial de análisis de sentimiento de ML.NET](../tutorials/sentiment-analysis.md) para generar su propio modelo o descargue este [modelo de Machine Learning de análisis de sentimiento entrenado previamente](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).</span><span class="sxs-lookup"><span data-stu-id="f9701-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="f9701-112">Creación de un proyecto de ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="f9701-112">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="f9701-113">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f9701-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="f9701-114">Seleccione **Archivo > Nuevo > Proyecto** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="f9701-114">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="f9701-115">En el cuadro de diálogo Nuevo proyecto, seleccione el nodo **Visual C#** seguido del nodo **Web**.</span><span class="sxs-lookup"><span data-stu-id="f9701-115">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="f9701-116">Seleccione la plantilla de proyecto **Aplicación web de ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="f9701-116">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="f9701-117">En el cuadro de texto **Nombre**, escriba "SentimentAnalysisWebAPI" y haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9701-117">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="f9701-118">En la ventana que muestra los distintos tipos de proyectos de ASP.NET Core, seleccione **API** y haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9701-118">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="f9701-119">Cree un directorio denominado *MLModels* en el proyecto para guardar los archivos del modelo de Machine Learning precompilado:</span><span class="sxs-lookup"><span data-stu-id="f9701-119">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="f9701-120">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione Agregar > Nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="f9701-120">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="f9701-121">Escriba "MLModels" y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="f9701-121">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="f9701-122">Instale el **paquete NuGet Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="f9701-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="f9701-123">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="f9701-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f9701-124">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón Instalar.</span><span class="sxs-lookup"><span data-stu-id="f9701-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="f9701-125">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo Aceptación de la licencia en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="f9701-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="f9701-126">Instale el **paquete NuGet Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="f9701-126">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="f9701-127">En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="f9701-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f9701-128">Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.Extensions.ML**, seleccione ese paquete en la lista y haga clic en el botón "Instalar".</span><span class="sxs-lookup"><span data-stu-id="f9701-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="f9701-129">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo Aceptación de la licencia en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="f9701-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="f9701-130">Incorporación del modelo a un proyecto de ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="f9701-130">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="f9701-131">Copie el modelo precompilado al directorio *MLModels*.</span><span class="sxs-lookup"><span data-stu-id="f9701-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="f9701-132">En el Explorador de soluciones, haga clic con el botón derecho en el archivo ZIP del modelo y seleccione Propiedades.</span><span class="sxs-lookup"><span data-stu-id="f9701-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="f9701-133">En Avanzadas, cambie el valor de Copiar en el directorio de salida por Copiar si es posterior.</span><span class="sxs-lookup"><span data-stu-id="f9701-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="f9701-134">Creación de modelos de datos</span><span class="sxs-lookup"><span data-stu-id="f9701-134">Create data models</span></span>

<span data-ttu-id="f9701-135">Debe crear algunas clases para los datos de entrada y las predicciones.</span><span class="sxs-lookup"><span data-stu-id="f9701-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="f9701-136">Agregue una nueva clase a su proyecto:</span><span class="sxs-lookup"><span data-stu-id="f9701-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="f9701-137">Cree un directorio denominado *DataModels* en el proyecto para guardar los modelos de datos:</span><span class="sxs-lookup"><span data-stu-id="f9701-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="f9701-138">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione Agregar > Nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="f9701-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="f9701-139">Escriba "DataModels" y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="f9701-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="f9701-140">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione Agregar > Nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="f9701-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="f9701-141">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="f9701-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="f9701-142">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9701-142">Then, select the **Add** button.</span></span> <span data-ttu-id="f9701-143">Se abre el archivo *SentimentData.cs* en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="f9701-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="f9701-144">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentData.cs*:</span><span class="sxs-lookup"><span data-stu-id="f9701-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="f9701-145">Quite la definición de clase existente y agregue el código siguiente al archivo **SentimentData.cs**:</span><span class="sxs-lookup"><span data-stu-id="f9701-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

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

4. <span data-ttu-id="f9701-146">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="f9701-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="f9701-147">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="f9701-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="f9701-148">Luego, haga clic en el botón Agregar.</span><span class="sxs-lookup"><span data-stu-id="f9701-148">Then, select the Add button.</span></span> <span data-ttu-id="f9701-149">El archivo *SentimentPrediction.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="f9701-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="f9701-150">Agregue la instrucción using siguiente en la parte superior del archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="f9701-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="f9701-151">Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentPrediction.cs*:</span><span class="sxs-lookup"><span data-stu-id="f9701-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="f9701-152">`SentimentPrediction` hereda de `SentimentData`.</span><span class="sxs-lookup"><span data-stu-id="f9701-152">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="f9701-153">Así resulta más fácil ver los datos originales en la propiedad `SentimentText` junto con la salida generada por el modelo.</span><span class="sxs-lookup"><span data-stu-id="f9701-153">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span>

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="f9701-154">Registro de PredictionEngine para usarlo en la aplicación</span><span class="sxs-lookup"><span data-stu-id="f9701-154">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="f9701-155">Para hacer una sola predicción, debe crear un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span><span class="sxs-lookup"><span data-stu-id="f9701-155">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="f9701-156">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f9701-156">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="f9701-157">Además, tiene que crear una instancia de ella en cualquier lugar en que se necesite dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9701-157">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="f9701-158">A medida que crece la aplicación, este proceso puede volverse difícil de administrar.</span><span class="sxs-lookup"><span data-stu-id="f9701-158">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="f9701-159">Para mejorar el rendimiento y la seguridad para subprocesos, use una combinación de inserción de dependencias y el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9701-159">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="f9701-160">En el vínculo siguiente se proporciona más información si quiere aprender sobre la [inserción de dependencias en ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="f9701-160">The following link provides more information if you want to learn more about [dependency injection in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="f9701-161">Abra la clase *Startup.cs* y agregue la siguiente instrucción using en la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="f9701-161">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="f9701-162">Agregue el código siguiente al método *ConfigureServices*:</span><span class="sxs-lookup"><span data-stu-id="f9701-162">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
    }
    ```

<span data-ttu-id="f9701-163">En un nivel alto, este código inicializa los objetos y servicios de manera automática para su uso más adelante cuando lo solicite la aplicación en lugar de tener que hacerlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="f9701-163">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span>

<span data-ttu-id="f9701-164">Los modelos de Machine Learning no son estáticos.</span><span class="sxs-lookup"><span data-stu-id="f9701-164">Machine learning models are not static.</span></span> <span data-ttu-id="f9701-165">A medida que haya nuevos datos de entrenamiento disponibles, el modelo se vuelve a entrenar y a implementar.</span><span class="sxs-lookup"><span data-stu-id="f9701-165">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="f9701-166">Una manera de obtener la versión más reciente del modelo en la aplicación es volver a implementar toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9701-166">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="f9701-167">Sin embargo, esto implica un tiempo de inactividad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9701-167">However, this introduces application downtime.</span></span> <span data-ttu-id="f9701-168">El servicio `PredictionEnginePool` proporciona un mecanismo para volver a cargar un modelo actualizado sin dejar inactiva su aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9701-168">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span>

<span data-ttu-id="f9701-169">Establezca el parámetro `watchForChanges` en `true` y el `PredictionEnginePool` inicia un [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) que escucha las notificaciones de cambios en el sistema de archivos y genera eventos cuando se produce un cambio en el archivo.</span><span class="sxs-lookup"><span data-stu-id="f9701-169">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="f9701-170">Este solicita al `PredictionEnginePool` que vuelva a cargar automáticamente el modelo.</span><span class="sxs-lookup"><span data-stu-id="f9701-170">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="f9701-171">El modelo se identifica mediante el parámetro `modelName`, por lo que se puede volver a cargar más de un modelo por aplicación tras el cambio.</span><span class="sxs-lookup"><span data-stu-id="f9701-171">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span>

> [!TIP]
> <span data-ttu-id="f9701-172">Como alternativa, puede usar el método `FromUri` al trabajar con modelos almacenados de manera remota.</span><span class="sxs-lookup"><span data-stu-id="f9701-172">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="f9701-173">En lugar de ver si hay eventos modificados de archivo, `FromUri` sondea la ubicación remota en busca de cambios.</span><span class="sxs-lookup"><span data-stu-id="f9701-173">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="f9701-174">El intervalo de sondeo predeterminado es de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="f9701-174">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="f9701-175">Puede aumentar o disminuir el intervalo de sondeo en función de los requisitos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9701-175">You can increase or decrease the polling interval based on your application's requirements.</span></span> <span data-ttu-id="f9701-176">En el ejemplo de código siguiente, `PredictionEnginePool` sondea el modelo almacenado en el URI especificado cada minuto.</span><span class="sxs-lookup"><span data-stu-id="f9701-176">In the code sample below, the `PredictionEnginePool` polls the model stored at the specified URI every minute.</span></span>
>
>```csharp
>builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="create-predict-controller"></a><span data-ttu-id="f9701-177">Creación de controlador de predicción</span><span class="sxs-lookup"><span data-stu-id="f9701-177">Create Predict controller</span></span>

<span data-ttu-id="f9701-178">Para procesar las solicitudes HTTP entrantes, cree un controlador.</span><span class="sxs-lookup"><span data-stu-id="f9701-178">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="f9701-179">En el Explorador de soluciones, haga clic con el botón derecho en el directorio *Controladores* y seleccione **Agregar > Controlador**.</span><span class="sxs-lookup"><span data-stu-id="f9701-179">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="f9701-180">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **API Controller Empty** (Controlador de API vacío) y seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f9701-180">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="f9701-181">En el símbolo del sistema, cambie el campo **Nombre del controlador** a *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="f9701-181">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="f9701-182">Luego, haga clic en el botón Agregar.</span><span class="sxs-lookup"><span data-stu-id="f9701-182">Then, select the Add button.</span></span> <span data-ttu-id="f9701-183">El archivo *PredictController.cs* se abre en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="f9701-183">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="f9701-184">Agregue la instrucción using siguiente en la parte superior del archivo *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="f9701-184">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="f9701-185">Quite la definición de clase existente y agregue el código siguiente al archivo *PredictController.cs*:</span><span class="sxs-lookup"><span data-stu-id="f9701-185">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

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

<span data-ttu-id="f9701-186">Este código asigna `PredictionEnginePool` al pasarlo al constructor del controlador que se obtiene a través de una inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="f9701-186">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="f9701-187">Luego, el método `Post` del controlador `Predict` usa `PredictionEnginePool` para hacer predicciones con el `SentimentAnalysisModel` registrado en la clase `Startup` y devuelve los resultados al usuario si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="f9701-187">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="f9701-188">Prueba local de Web API</span><span class="sxs-lookup"><span data-stu-id="f9701-188">Test web API locally</span></span>

<span data-ttu-id="f9701-189">Una vez que todo está configurado, es momento de probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9701-189">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="f9701-190">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9701-190">Run the application.</span></span>
1. <span data-ttu-id="f9701-191">Abra PowerShell y escriba el código siguiente, donde PORT es el puerto donde escuchar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9701-191">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="f9701-192">Si se realiza correctamente, la salida debería ser similar al texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9701-192">If successful, the output should look similar to the text below:</span></span>

    ```powershell
    Negative
    ```

<span data-ttu-id="f9701-193">Felicidades.</span><span class="sxs-lookup"><span data-stu-id="f9701-193">Congratulations!</span></span> <span data-ttu-id="f9701-194">Publicó correctamente el modelo para realizar predicciones en Internet mediante una ASP.NET Core Web API.</span><span class="sxs-lookup"><span data-stu-id="f9701-194">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f9701-195">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f9701-195">Next Steps</span></span>

- [<span data-ttu-id="f9701-196">Implementación en Azure</span><span class="sxs-lookup"><span data-stu-id="f9701-196">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)

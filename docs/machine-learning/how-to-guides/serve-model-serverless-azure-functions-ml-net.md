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
# <a name="deploy-a-model-to-azure-functions"></a>Implementación de un modelo en Azure Functions

Aprenda cómo implementar un modelo de Machine Learning de ML.NET previamente entrenado para realizar predicciones por HTTP a través de un entorno sin servidor de Azure Functions.

> [!NOTE]
> La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2017 15.6 o versión posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" y el "desarrollo de Azure" instalados.
- [Herramientas de Azure Functions](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- PowerShell
- Modelo previamente entrenado. Use el [tutorial de análisis de sentimiento de ML.NET](../tutorials/sentiment-analysis.md) para generar su propio modelo o descargue este [modelo de Machine Learning de análisis de sentimiento entrenado previamente](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).

## <a name="create-azure-functions-project"></a>Creación de un proyecto de Azure Functions

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **Cloud**. A continuación, seleccione la plantilla de proyecto **Azure Functions**. En el cuadro de texto **Nombre**, escriba "SentimentAnalysisFunctionsApp" y después haga clic en el botón **Aceptar**.
1. En el cuadro de diálogo **Nuevo proyecto**, abra el menú desplegable que se encuentra sobre las opciones del proyecto y seleccione **Azure Functions v2 (.NET Core)**. Luego, seleccione el proyecto **Desencadenador HTTP** y luego haga clic en el botón **Aceptar**.
1. En el proyecto, cree un directorio denominado *MLModels* para guardar el modelo:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "MLModels" y presione ENTRAR.

1. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

1. Instale el **paquete NuGet Microsoft.Extensions.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.Extensions.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

## <a name="add-pre-trained-model-to-project"></a>Incorporación del modelo entrenado previamente en el proyecto

1. Copie el modelo precompilado en la carpeta *MLModels*.
1. En el Explorador de soluciones, haga clic con el botón derecho en el archivo del modelo precompilado y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

## <a name="create-azure-function-to-analyze-sentiment"></a>Creación de una función de Azure para analizar sentimientos

Cree una clase para predecir sentimientos. Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Función de Azure** y cambie el campo **Nombre** a *AnalyzeSentiment.cs*. A continuación, seleccione el botón **Agregar**.

1. En el cuadro de diálogo **Nueva función de Azure**, seleccione **Desencadenador HTTP**. Luego haga clic en el botón **Aceptar**.

    El archivo *AnalyzeSentiment.cs* se abre en el editor de código. Agregue la siguiente instrucción `using` a la parte superior de *AnalyzeSentiment.cs*:

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

    De forma predeterminada, la clase `AnalyzeSentiment` es `static`. Asegúrese de quitar la palabra clave `static` de la definición de clase.

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a>Creación de modelos de datos

Debe crear algunas clases para los datos de entrada y las predicciones. Agregue una nueva clase a su proyecto:

1. Cree un directorio denominado *DataModels* en el proyecto para guardar los modelos de datos: En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nueva carpeta**. Escriba "DataModels" y presione ENTRAR.
2. En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.
3. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*. A continuación, seleccione el botón **Agregar**. 

    Se abre el archivo *SentimentData.cs* en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *SentimentData.cs*:

    ```csharp
    using Microsoft.ML.Data;
    ```

    Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentData.cs*:
    
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

4. En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.
5. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentPrediction.cs*. A continuación, seleccione el botón **Agregar**. El archivo *SentimentPrediction.cs* se abre en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *SentimentPrediction.cs*:

    ```csharp
    using Microsoft.ML.Data;
    ```

    Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentPrediction.cs*:

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    `SentimentPrediction` hereda de `SentimentData` el cual proporciona acceso a los datos originales en la propiedad `SentimentText`, así como la salida generada por el modelo.

## <a name="register-predictionenginepool-service"></a>Registro del servicio PredictionEnginePool

Para realizar una sola predicción, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602). Para poder usar [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) en la aplicación, debe crearlo cuando sea necesario. En ese caso, un procedimiento recomendado que se debe considerar es la inserción de dependencias.

En el vínculo siguiente se proporciona más información si quiere aprender sobre la [inserción de dependencias](https://en.wikipedia.org/wiki/Dependency_injection).

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *Startup.cs*. A continuación, seleccione el botón **Agregar**. 

    Se abre el archivo *Startup.cs* en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *Startup.cs*:

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    Quite el código existente debajo de las instrucciones using y agregue el código siguiente al archivo *Startup.cs*:

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

En un nivel alto, este código inicializa los objetos y servicios de manera automática cuando lo solicita la aplicación en lugar de tener que hacerlo manualmente.

> [!WARNING]
> [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos. Para mejorar el rendimiento y la seguridad para subprocesos, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos `PredictionEngine` para el uso de la aplicación. 

## <a name="register-startup-as-an-azure-functions-extension"></a>Registro de Startup como una extensión de Azure Functions

Para poder usar `Startup` en la aplicación, deberá registrarlo como una extensión de Azure Functions. Cree un nuevo archivo denominado *extensions.json* en el proyecto si aún no existe uno.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Nuevo elemento**, seleccione el nodo **Visual C#** seguido del nodo **Web**. A continuación, seleccione la opción del **archivo Json**. En el cuadro de texto **Nombre**, escriba "extensions.json" y después seleccione el botón **Aceptar**.

    El archivo *extensions.json* se abre en el editor de código. Agregue el contenido siguiente a *extensions.json*:
    
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

1. En el Explorador de soluciones, haga clic con el botón derecho en el archivo *extensions.json* y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

## <a name="load-the-model-into-the-function"></a>Carga del modelo en la función

Inserte el código siguiente dentro de la clase *AnalyzeSentiment*:

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

Este código asigna `PredictionEnginePool` al pasarlo al constructor de la función que se obtiene a través de una inserción de dependencias.

## <a name="use-the-model-to-make-predictions"></a>Uso del modelo para realizar predicciones

Reemplace la implementación existente del método *Run* en la clase *AnalyzeSentiment* por el código siguiente:

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

Cuando se ejecuta el método `Run`, los datos entrantes de la solicitud HTTP se deserializan y se usan como entrada en el `PredictionEnginePool`. A continuación, se llama al método `Predict` para generar una predicción y devolver el resultado al usuario. 

## <a name="test-locally"></a>Prueba local

Ahora que está todo configurado, es momento de probar la aplicación:

1. Ejecutar la aplicación
1. Abra PowerShell y escriba el código en el símbolo del sistema, donde PORT es el puerto en que se ejecuta la aplicación. Por lo general, se trata del puerto 7071.

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    Si se realiza correctamente, la salida debería ser similar al texto siguiente:
    
    ```powershell
    Negative
    ```

¡Enhorabuena! Publicó correctamente el modelo para realizar predicciones en Internet mediante una función de Azure.

## <a name="next-steps"></a>Pasos siguientes

- [Implementación en Azure](/azure/azure-functions/functions-develop-vs#publish-to-azure)

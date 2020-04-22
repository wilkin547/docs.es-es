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
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a>Implementación de un modelo en una ASP.NET Core Web API

Aprenda cómo publicar un modelo de Machine Learning de ML.NET entrenado previamente en la Web a través de una ASP.NET Core Web API. Publicar un modelo a través de una API web permite predicciones mediante métodos HTTP estándar.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.
- PowerShell.
- Modelo previamente entrenado. Use el [tutorial de análisis de sentimiento de ML.NET](../tutorials/sentiment-analysis.md) para generar su propio modelo o descargue este [modelo de Machine Learning de análisis de sentimiento entrenado previamente](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).

## <a name="create-aspnet-core-web-api-project"></a>Creación de un proyecto de ASP.NET Core Web API

1. Abra Visual Studio 2017. Seleccione **Archivo > Nuevo > Proyecto** en la barra de menús. En el cuadro de diálogo Nuevo proyecto, seleccione el nodo **Visual C#** seguido del nodo **Web**. Seleccione la plantilla de proyecto **Aplicación web de ASP.NET Core**. En el cuadro de texto **Nombre**, escriba "SentimentAnalysisWebAPI" y haga clic en el botón **Aceptar**.

1. En la ventana que muestra los distintos tipos de proyectos de ASP.NET Core, seleccione **API** y haga clic en el botón **Aceptar**.

1. Cree un directorio denominado *MLModels* en el proyecto para guardar los archivos del modelo de Machine Learning precompilado:

    En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione Agregar > Nueva carpeta. Escriba "MLModels" y presione ENTRAR.

1. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón Instalar. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo Aceptación de la licencia en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

1. Instale el **paquete NuGet Microsoft.Extensions.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.Extensions.ML**, seleccione ese paquete en la lista y haga clic en el botón "Instalar". Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo Aceptación de la licencia en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

### <a name="add-model-to-aspnet-core-web-api-project"></a>Incorporación del modelo a un proyecto de ASP.NET Core Web API

1. Copie el modelo precompilado al directorio *MLModels*.
1. En el Explorador de soluciones, haga clic con el botón derecho en el archivo ZIP del modelo y seleccione Propiedades. En Avanzadas, cambie el valor de Copiar en el directorio de salida por Copiar si es posterior.

## <a name="create-data-models"></a>Creación de modelos de datos

Debe crear algunas clases para los datos de entrada y las predicciones. Agregue una nueva clase a su proyecto:

1. Cree un directorio denominado *DataModels* en el proyecto para guardar los modelos de datos:

    En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione Agregar > Nueva carpeta. Escriba "DataModels" y presione **ENTRAR**.

2. En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione Agregar > Nuevo elemento.
3. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*. A continuación, seleccione el botón **Agregar**. Se abre el archivo *SentimentData.cs* en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *SentimentData.cs*:

    ```csharp
    using Microsoft.ML.Data;
    ```

    Quite la definición de clase existente y agregue el código siguiente al archivo **SentimentData.cs**:

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
5. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentPrediction.cs*. Luego, haga clic en el botón Agregar. El archivo *SentimentPrediction.cs* se abre en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *SentimentPrediction.cs*:

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

    `SentimentPrediction` hereda de `SentimentData`. Así resulta más fácil ver los datos originales en la propiedad `SentimentText` junto con la salida generada por el modelo.

## <a name="register-predictionenginepool-for-use-in-the-application"></a>Registro de PredictionEngine para usarlo en la aplicación

Para hacer una sola predicción, debe crear un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602). [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos. Además, tiene que crear una instancia de ella en cualquier lugar en que se necesite dentro de la aplicación. A medida que crece la aplicación, este proceso puede volverse difícil de administrar. Para mejorar el rendimiento y la seguridad para subprocesos, use una combinación de inserción de dependencias y el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.

En el vínculo siguiente se proporciona más información si quiere aprender sobre la [inserción de dependencias en ASP.NET Core](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).

1. Abra la clase *Startup.cs* y agregue la siguiente instrucción using en la parte superior del archivo:

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. Agregue el código siguiente al método *ConfigureServices*:

    ```csharp
    services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
        .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
    ```

En un nivel alto, este código inicializa los objetos y servicios de manera automática para su uso más adelante cuando lo solicite la aplicación en lugar de tener que hacerlo manualmente.

Los modelos de Machine Learning no son estáticos. A medida que haya nuevos datos de entrenamiento disponibles, el modelo se vuelve a entrenar y a implementar. Una manera de obtener la versión más reciente del modelo en la aplicación es volver a implementar toda la aplicación. Sin embargo, esto implica un tiempo de inactividad de la aplicación. El servicio `PredictionEnginePool` proporciona un mecanismo para volver a cargar un modelo actualizado sin dejar inactiva su aplicación.

Establezca el parámetro `watchForChanges` en `true` y el `PredictionEnginePool` inicia un [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) que escucha las notificaciones de cambios en el sistema de archivos y genera eventos cuando se produce un cambio en el archivo. Este solicita al `PredictionEnginePool` que vuelva a cargar automáticamente el modelo.

El modelo se identifica mediante el parámetro `modelName`, por lo que se puede volver a cargar más de un modelo por aplicación tras el cambio.

> [!TIP]
> Como alternativa, puede usar el método `FromUri` al trabajar con modelos almacenados de manera remota. En lugar de ver si hay eventos modificados de archivo, `FromUri` sondea la ubicación remota en busca de cambios. El intervalo de sondeo predeterminado es de 5 minutos. Puede aumentar o disminuir el intervalo de sondeo en función de los requisitos de la aplicación. En el ejemplo de código siguiente, `PredictionEnginePool` sondea el modelo almacenado en el URI especificado cada minuto.
>
>```csharp
>services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="create-predict-controller"></a>Creación de controlador de predicción

Para procesar las solicitudes HTTP entrantes, cree un controlador.

1. En el Explorador de soluciones, haga clic con el botón derecho en el directorio *Controladores* y seleccione **Agregar > Controlador**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **API Controller Empty** (Controlador de API vacío) y seleccione **Agregar**.
1. En el símbolo del sistema, cambie el campo **Nombre del controlador** a *PredictController.cs*. Luego, haga clic en el botón Agregar. El archivo *PredictController.cs* se abre en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *PredictController.cs*:

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    Quite la definición de clase existente y agregue el código siguiente al archivo *PredictController.cs*:

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

Este código asigna `PredictionEnginePool` al pasarlo al constructor del controlador que se obtiene a través de una inserción de dependencias. Luego, el método `Post` del controlador `Predict` usa `PredictionEnginePool` para hacer predicciones con el `SentimentAnalysisModel` registrado en la clase `Startup` y devuelve los resultados al usuario si se realiza correctamente.

## <a name="test-web-api-locally"></a>Prueba local de Web API

Una vez que todo está configurado, es momento de probar la aplicación.

1. Ejecute la aplicación.
1. Abra PowerShell y escriba el código siguiente, donde PORT es el puerto donde escuchar la aplicación.

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    Si se realiza correctamente, la salida debería ser similar al texto siguiente:

    ```powershell
    Negative
    ```

¡Enhorabuena! Publicó correctamente el modelo para realizar predicciones en Internet mediante una ASP.NET Core Web API.

## <a name="next-steps"></a>Pasos siguientes

- [Implementación en Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)

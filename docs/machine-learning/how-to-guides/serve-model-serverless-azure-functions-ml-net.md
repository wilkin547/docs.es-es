---
title: Implementación de un modelo en Azure Functions
description: Publicación del modelo de Machine Learning de Análisis de sentimiento de ML.NET para la predicción en Internet a través de Azure Functions
ms.date: 02/21/2020
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 33afd568bb12b855a3888bec31f2e9bbc3c720da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "77628675"
---
# <a name="deploy-a-model-to-azure-functions"></a>Implementación de un modelo en Azure Functions

Aprenda cómo implementar un modelo de Machine Learning de ML.NET previamente entrenado para realizar predicciones por HTTP a través de un entorno sin servidor de Azure Functions.

> [!NOTE]
> En este ejemplo se ejecuta una versión preliminar del servicio `PredictionEnginePool`.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2017, versión 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" y el "desarrollo de Azure" instalados.
- [Herramientas de Azure Functions](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- PowerShell
- Modelo previamente entrenado. Use el [tutorial de análisis de sentimiento de ML.NET](../tutorials/sentiment-analysis.md) para generar su propio modelo o descargue este [modelo de Machine Learning de análisis de sentimiento entrenado previamente](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).

## <a name="azure-functions-sample-overview"></a>Introducción a un ejemplo de Azure Functions

Este ejemplo es una **aplicación de desencadenador HTTP de C# de Azure Functions** que utiliza un modelo de clasificación binaria previamente entrenado para clasificar la opinión del texto como positiva o negativa. Azure Functions proporciona una manera sencilla de ejecutar pequeños fragmentos de código a escala en un entorno sin servidor administrado en la nube. El código de este ejemplo se puede encontrar en el [repositorio dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction) en GitHub.

## <a name="create-azure-functions-project"></a>Creación de un proyecto de Azure Functions

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **Cloud**. A continuación, seleccione la plantilla de proyecto **Azure Functions**. En el cuadro de texto **Nombre**, escriba "SentimentAnalysisFunctionsApp" y después haga clic en el botón **Aceptar**.
1. En el cuadro de diálogo **Nuevo proyecto**, abra el menú desplegable que se encuentra sobre las opciones del proyecto y seleccione **Azure Functions v2 (.NET Core)** . Luego, seleccione el proyecto **Desencadenador HTTP** y luego haga clic en el botón **Aceptar**.
1. En el proyecto, cree un directorio denominado *MLModels* para guardar el modelo:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "MLModels" y presione ENTRAR.

1. Instale el **paquete NuGet Microsoft.ML** versión **1.3.1**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

1. Instalar el **paquete NuGet Microsoft.Azure.Functions.Extensions**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.Azure.Functions.Extensions**, seleccione ese paquete en la lista y seleccione **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

1. Instale el **paquete NuGet Microsoft.Extensions.ML** versión **0.15.1**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.Extensions.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

1. Instale el **paquete de NuGet Microsoft.NET.Sdk.Functions**, versión **1.0.31**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como el origen del paquete, seleccione la pestaña Instalado, busque **Microsoft.NET.Sdk.Functions**, seleccione ese paquete en la lista, seleccione **1.0.31** en la lista desplegable Versión y, por último, seleccione el botón **Actualizar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

## <a name="add-pre-trained-model-to-project"></a>Incorporación del modelo entrenado previamente en el proyecto

1. Copie el modelo precompilado en la carpeta *MLModels*.
1. En el Explorador de soluciones, haga clic con el botón derecho en el archivo del modelo precompilado y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

## <a name="create-azure-function-to-analyze-sentiment"></a>Creación de una función de Azure para analizar sentimientos

Cree una clase para predecir sentimientos. Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Función de Azure** y cambie el campo **Nombre** a *AnalyzeSentiment.cs*. A continuación, seleccione el botón **Agregar**.

1. En el cuadro de diálogo **Nueva función de Azure**, seleccione **Desencadenador HTTP**. Luego haga clic en el botón **Aceptar**.

    El archivo *AnalyzeSentiment.cs* se abre en el editor de código. Agregue la siguiente instrucción `using` a la parte superior de *AnalyzeSentiment.cs*:

    [!code-csharp [AnalyzeUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L1-L11)]

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

    [!code-csharp [SentimentDataUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L1)]

    Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentData.cs*:

    [!code-csharp [SentimentData](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L5-L13)]

4. En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.
5. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentPrediction.cs*. A continuación, seleccione el botón **Agregar**. El archivo *SentimentPrediction.cs* se abre en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *SentimentPrediction.cs*:

    [!code-csharp [SentimentPredictionUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L1)]

    Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentPrediction.cs*:

    [!code-csharp [SentimentPrediction](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L5-L14)]

    `SentimentPrediction` hereda de `SentimentData` el cual proporciona acceso a los datos originales en la propiedad `SentimentText`, así como la salida generada por el modelo.

## <a name="register-predictionenginepool-service"></a>Registro del servicio PredictionEnginePool

Para hacer una sola predicción, debe crear un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602). [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos. Además, tiene que crear una instancia de ella en cualquier lugar en que se necesite dentro de la aplicación. A medida que crece la aplicación, este proceso puede volverse difícil de administrar. Para mejorar el rendimiento y la seguridad para subprocesos, use una combinación de inserción de dependencias y el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.

En el vínculo siguiente se proporciona más información si quiere aprender más sobre la [inserción de dependencias](https://en.wikipedia.org/wiki/Dependency_injection).

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *Startup.cs*. A continuación, seleccione el botón **Agregar**.
1. Agregue las instrucciones using siguientes en la parte superior del archivo *Startup.cs*:

    [!code-csharp [StartupUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L1-L6)]

1. Quite el código existente debajo de las instrucciones using y agregue el código siguiente:

    ```csharp
    [assembly: FunctionsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        public class Startup : FunctionsStartup
        {

        }
    }
    ```

1. Defina variables para almacenar el entorno en el que se ejecuta la aplicación y la ruta de acceso del archivo donde se encuentra el modelo dentro de la clase `Startup`

    [!code-csharp [DefineStartupVars](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L13-L14)]

1. A continuación, cree un constructor para establecer los valores de las variables `_environment` y `_modelPath`. Cuando la aplicación se ejecuta localmente, el entorno predeterminado es *Development*.

    [!code-csharp [StartupCtor](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L16-L29)]

1. A continuación, agregue un nuevo método llamado `Configure` para registrar el servicio `PredictionEnginePool` debajo del constructor.

    [!code-csharp [ConfigureServices](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L31-L35)]

En un nivel alto, este código inicializa los objetos y servicios de manera automática para su uso más adelante cuando lo solicite la aplicación en lugar de tener que hacerlo manualmente.

Los modelos de Machine Learning no son estáticos. A medida que haya nuevos datos de entrenamiento disponibles, el modelo se vuelve a entrenar y a implementar. Una manera de obtener la versión más reciente del modelo en la aplicación es volver a implementar toda la aplicación. Sin embargo, esto implica un tiempo de inactividad de la aplicación. El servicio `PredictionEnginePool` proporciona un mecanismo para volver a cargar un modelo actualizado sin dejar inactiva su aplicación.

Establezca el parámetro `watchForChanges` en `true` y el `PredictionEnginePool` inicia un [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) que escucha las notificaciones de cambios en el sistema de archivos y genera eventos cuando se produce un cambio en el archivo. Este solicita al `PredictionEnginePool` que vuelva a cargar automáticamente el modelo.

El modelo se identifica mediante el parámetro `modelName`, por lo que se puede volver a cargar más de un modelo por aplicación tras el cambio.

> [!TIP]
> Como alternativa, puede usar el método `FromUri` al trabajar con modelos almacenados de manera remota. En lugar de ver si hay eventos modificados de archivo, `FromUri` sondea la ubicación remota en busca de cambios. El intervalo de sondeo predeterminado es de 5 minutos. Puede aumentar o disminuir el intervalo de sondeo en función de los requisitos de la aplicación. En el ejemplo de código siguiente, `PredictionEnginePool` sondea el modelo almacenado en el URI especificado cada minuto.
>
>```csharp
>builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="load-the-model-into-the-function"></a>Carga del modelo en la función

Inserte el código siguiente dentro de la clase *AnalyzeSentiment*:

[!code-csharp [AnalyzeCtor](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L18-L24)]

Este código asigna `PredictionEnginePool` al pasarlo al constructor de la función que se obtiene a través de una inserción de dependencias.

## <a name="use-the-model-to-make-predictions"></a>Uso del modelo para realizar predicciones

Reemplace la implementación existente del método *Run* en la clase *AnalyzeSentiment* por el código siguiente:

[!code-csharp [AnalyzeRunMethod](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L26-L45)]

Cuando se ejecuta el método `Run`, los datos entrantes de la solicitud HTTP se deserializan y se usan como entrada en el `PredictionEnginePool`. A continuación, se llama al método `Predict` para realizar predicciones con el `SentimentAnalysisModel` registrado en la clase `Startup` y devuelve los resultados al usuario si se realiza correctamente.

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

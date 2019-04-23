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
# <a name="how-to-use-mlnet-model-in-azure-functions"></a>Uso del modelo de ML.NET en Azure Functions

En esta guía se muestra cómo se pueden hacer predicciones individuales mediante un modelo de Machine Learning de ML.NET precompilado a través de Internet en un entorno sin servidor como Azure Functions.

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**. Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2017 15.6 o versión posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" y el "desarrollo de Azure" instalados. 
- [Herramientas de Azure Functions](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- PowerShell
- Modelo previamente entrenado. 
    - Use el [tutorial de Análisis de sentimiento de ML.NET](../tutorials/sentiment-analysis.md) para compilar su propio modelo.
    - Descargue este [modelo de Machine Learning de Análisis de sentimiento previamente entrenado](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).

## <a name="create-azure-functions-project"></a>Creación de un proyecto de Azure Functions

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **Cloud**. A continuación, seleccione la plantilla de proyecto **Azure Functions**. En el cuadro de texto **Nombre**, escriba "SentimentAnalysisFunctionsApp" y después haga clic en el botón **Aceptar**.
1. En el cuadro de diálogo **Nuevo proyecto**, abra el menú desplegable que se encuentra sobre las opciones del proyecto y seleccione **Azure Functions v2 (.NET Core)**. Luego, seleccione el proyecto **Desencadenador HTTP** y luego haga clic en el botón **Aceptar**.
1. En el proyecto, cree un directorio denominado *MLModels* para guardar el modelo:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "MLModels" y presione ENTRAR.

1. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

## <a name="add-pre-built-model-to-project"></a>Incorporación del modelo precompilado en el proyecto

1. Copie el modelo precompilado en la carpeta *MLModels*.
1. En el Explorador de soluciones, haga clic con el botón derecho en el archivo del modelo precompilado y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

## <a name="create-function-to-analyze-sentiment"></a>Creación de una función para analizar sentimientos

Cree una clase para predecir sentimientos. Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Función de Azure** y cambie el campo **Nombre** a *AnalyzeSentiment.cs*. A continuación, seleccione el botón **Agregar**.

1. En el cuadro de diálogo **Nueva función de Azure**, seleccione **Desencadenador HTTP**. Luego haga clic en el botón **Aceptar**.

    El archivo *AnalyzeSentiment.cs* se abre en el editor de código. Agregue la siguiente instrucción `using` a la parte superior de *GitHubIssueData.cs*:

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

### <a name="create-data-models"></a>Creación de modelos de datos

Debe crear algunas clases para los datos de entrada y las predicciones. Agregue una nueva clase a su proyecto:

1. Cree un directorio denominado *DataModels* en el proyecto para guardar los modelos de datos: En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nueva carpeta**. Escriba "DataModels" y presione ENTRAR.
2. En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.
3. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*. A continuación, seleccione el botón **Agregar**. Se abre el archivo *SentimentData.cs* en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *SentimentData.cs*:

```csharp
using Microsoft.ML.Data;
```

Quite la definición de clase existente y agregue el código siguiente al archivo SentimentData.cs:

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }
}
```

4. En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione **Agregar > Nuevo elemento**.
5. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentPrediction.cs*. A continuación, seleccione el botón **Agregar**. El archivo *SentimentPrediction.cs* se abre en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *SentimentPrediction.cs*:

```csharp
using Microsoft.ML.Data;
```

Quite la definición de clase existente y agregue el código siguiente al archivo *SentimentPrediction.cs*:

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

### <a name="add-prediction-logic"></a>Incorporación de la lógica de predicción

Reemplace la implementación existente del método *Run* en la clase *AnalyzeSentiment* por el código siguiente:

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

## <a name="test-locally"></a>Prueba local

Ahora que está todo configurado, es momento de probar la aplicación:

1. Ejecutar la aplicación
1. Abra PowerShell y escriba el código en el símbolo del sistema, donde PORT es el puerto en que se ejecuta la aplicación. Por lo general, se trata del puerto 7071. 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

Si se realiza correctamente, la salida debería ser similar al texto siguiente:

```powershell
Toxic
```

¡Enhorabuena! Publicó correctamente el modelo para realizar predicciones en Internet mediante una función de Azure.

## <a name="next-steps"></a>Pasos siguientes

- [Implementación en Azure](/azure/azure-functions/functions-develop-vs#publish-to-azure)
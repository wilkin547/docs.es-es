---
title: Publicación de un modelo de Machine Learning en ASP.NET Core Web API
description: Publicación del modelo de Machine Learning de Análisis de sentimiento de ML.NET en Internet mediante ASP.NET Core Web API
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 07b751caff8ef0ca9a23bed68ddf88feb7b5ae4f
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "57856711"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a>Publicación de un modelo de Machine Learning a través de ASP.NET Core Web API

En esta guía se muestra cómo publicar un modelo de Machine Learning de ML.NET precompilado en la Web a través de una ASP.NET Core Web API. De esta forma se permite que los usuarios accedan a la API para obtener predicciones a través de métodos HTTP estándar.

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**. Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.
- PowerShell.
- Modelo previamente entrenado.
    - Use el [tutorial de Análisis de sentimiento de ML.NET](../tutorials/sentiment-analysis.md) para compilar su propio modelo.
    - Descargue este [modelo de Machine Learning de Análisis de sentimiento previamente entrenado](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip).

## <a name="create-aspnet-core-web-api-project"></a>Creación de un proyecto de ASP.NET Core Web API

1. Abra Visual Studio 2017. Seleccione **Archivo > Nuevo > Proyecto** en la barra de menús. En el cuadro de diálogo Nuevo proyecto, seleccione el nodo **Visual C#** seguido del nodo **Web**. Seleccione la plantilla de proyecto **Aplicación web de ASP.NET Core**. En el cuadro de texto **Nombre**, escriba "SentimentAnalysisWebAPI" y haga clic en el botón **Aceptar**.
1. En la ventana que muestra los distintos tipos de proyectos de ASP.NET Core, seleccione **API** y haga clic en el botón **Aceptar**.
1. Cree un directorio denominado *MLModels* en el proyecto para guardar los archivos del modelo de Machine Learning precompilado:

    En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione Agregar > Nueva carpeta. Escriba "MLModels" y presione ENTRAR.

1. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón Instalar. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo Aceptación de la licencia en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

### <a name="add-model-to-aspnet-core-web-api-project"></a>Incorporación del modelo a un proyecto de ASP.NET Core Web API

1. Copie el modelo precompilado al directorio *MLModels*.
1. En el Explorador de soluciones, haga clic con el botón derecho en el archivo ZIP del modelo y seleccione Propiedades. En Avanzadas, cambie el valor de Copiar en el directorio de salida por Copiar si es posterior.

## <a name="build-data-models"></a>Creación de modelos de datos

Debe crear algunas clases para los datos de entrada y las predicciones. Agregue una nueva clase a su proyecto:

1. Cree un directorio denominado *DataModels* en el proyecto para guardar los modelos de datos:

    En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione Agregar > Nueva carpeta. Escriba "DataModels" y presione **ENTRAR**.

2. En el Explorador de soluciones, haga clic con el botón derecho en el directorio *DataModels* y luego seleccione Agregar > Nuevo elemento.
3. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentData.cs*. A continuación, seleccione el botón **Agregar**. Se abre el archivo *SentimentData.cs* en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *SentimentData.cs*:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

Quite la definición de clase existente y agregue el código siguiente al archivo **SentimentData.cs**:

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
5. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *SentimentPrediction.cs*. Luego, haga clic en el botón Agregar. El archivo *SentimentPrediction.cs* se abre en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *SentimentPrediction.cs*:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
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

## <a name="create-prediction-service"></a>Creación del servicio de predicción

Para organizar y volver a usar la lógica de predicción en toda la aplicación, cree un servicio de predicción.

1. Cree un directorio denominado *Services* en el proyecto para contener servicios que usará la aplicación:

    En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nueva carpeta**. Escriba "Servicios" y presione **ENTRAR**.

1. En el Explorador de soluciones, haga clic con el botón derecho en el directorio *Servicios* y luego seleccione **Agregar > Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *PredictionService.cs*. A continuación, seleccione el botón **Agregar**. El archivo *PredictionService.cs* se abre en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *PredictionService.cs*:

```csharp
using System;
using System.IO;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
```

Quite la definición de clase existente y agregue el código siguiente al archivo *PredictionService.cs*:

```csharp
public class PredictionService
{
    private readonly PredictionEngine<SentimentData, SentimentPrediction> _predictionEngine;
    public PredictionService(PredictionEngine<SentimentData,SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine;
    }

    public string Predict(SentimentData input)
    {
        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return isToxic;

    }
}
```

## <a name="register-predictions-service-for-use-in-application"></a>Registro del servicio de predicciones para usarlo en una aplicación

Para usar el servicio de predicciones en la aplicación, deberá crearlo cada vez que sea necesario. En ese caso, un procedimiento recomendado que se debe considerar es la inserción de dependencias de ASP.NET Core.

En el vínculo siguiente se proporciona más información si quiere aprender sobre la [inserción de dependencias](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).

1. Abra la clase *Startup.cs* y agregue la siguiente instrucción using en la parte superior del archivo:

```csharp
using System.IO;
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Extensions.Configuration;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

1. Agregue las líneas de código siguientes al método *ConfigureServices*:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddSingleton<MLContext>();
    services.AddSingleton<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
    {
        MLContext mlContext = ctx.GetRequiredService<MLContext>();
        string modelFilePathName = "MLModels/sentiment_model.zip";

        //Load model from file
        ITransformer model;
        using (var stream = File.OpenRead(modelFilePathName))
        {
            model = mlContext.Model.Load(stream);
        }

        // Return prediction engine
        return model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);
    });
    services.AddSingleton<PredictionService>();
}
```

En un nivel alto, este código inicializa los objetos y servicios de manera automática cuando lo solicita la aplicación en lugar de tener que hacerlo manualmente.

## <a name="create-predict-controller"></a>Creación de controlador de predicción

Para procesar las solicitudes HTTP entrantes, necesita crear un controlador.

1. En el Explorador de soluciones, haga clic con el botón derecho en el directorio *Controladores* y seleccione **Agregar > Controlador**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **API Controller Empty** (Controlador de API vacío) y seleccione **Agregar**.
1. En el símbolo del sistema, cambie el campo **Nombre del controlador** a *PredictController.cs*. Luego, haga clic en el botón Agregar. El archivo *PredictController.cs* se abre en el editor de código. Agregue la instrucción using siguiente en la parte superior del archivo *PredictController.cs*:

```csharp
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

Quite la definición de clase existente y agregue el código siguiente al archivo *PredictController.cs*:

```csharp
public class PredictController : ControllerBase
{

    private readonly PredictionService _predictionService;

    public PredictController(PredictionService predictionService)
    {
        _predictionService = predictionService; //Define prediction service
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }
        return Ok(_predictionService.Predict(input));
    }

}
```

Esto asigna el servicio de predicción al pasarlo al constructor del controlador que se obtiene a través de una inserción de dependencias. A continuación, en el método POST de este controlador, el servicio de predicción se usa para hacer predicciones y devolver los resultados al usuario si se realiza correctamente.

## <a name="test-web-api-locally"></a>Prueba local de Web API

Una vez que todo está configurado, es momento de probar la aplicación.

1. Ejecute la aplicación.
1. Abra PowerShell y escriba el código siguiente, donde PORT es el puerto donde escuchar la aplicación.

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

Si se realiza correctamente, la salida debería ser similar al texto siguiente:

```powershell
Toxic
```

¡Enhorabuena! Publicó correctamente el modelo para realizar predicciones en Internet mediante una ASP.NET Core API.

## <a name="next-steps"></a>Pasos siguientes

- [Implementación en Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)
---
title: 'Tutorial: Análisis de sentimiento: clasificación binaria'
description: En este tutorial se muestra cómo crear una aplicación Razor Pages que clasifica los sentimientos de los comentarios del sitio web y toma las medidas oportunas. El clasificador binario de sentimientos usa el Generador de modelos en Visual Studio.
ms.date: 11/21/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 670c4dd1ac9da496f59d12d2e880cf269d64f309
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344961"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a>Tutorial: Análisis del sentimiento de los comentarios del sitio web en una aplicación web con el Generador de modelos de ML.NET

Aprenda a analizar el sentimiento de los comentarios en tiempo real dentro de una aplicación web.

En este tutorial se muestra cómo crear una aplicación Razor Pages de ASP.NET Core que clasifica los sentimientos de los comentarios del sitio web en tiempo real.

En este tutorial aprenderá a:

> [!div class="checklist"]
>
> - Crear una aplicación Razor Pages de ASP.NET Core
> - Preparar y entender los datos
> - Elección de un escenario
> - Carga de los datos
> - Entrenar el modelo
> - Evaluar el modelo
> - Usar el modelo para las predicciones

> [!NOTE]
> De momento, el Generador de modelos se encuentra en versión preliminar.

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples).

## <a name="pre-requisites"></a>Requisitos previos

Para obtener una lista de los requisitos previos e instrucciones de instalación, visite la [Guía de instalación del Generador de modelos](../how-to-guides/install-model-builder.md).

## <a name="create-a-razor-pages-application"></a>Creación de una aplicación Razor Pages

1. Cree una **aplicación Razor Pages de ASP.NET Core**.

    1. Abra Visual Studio y seleccione **Archivo > Nuevo > Proyecto** en la barra de menús.
    1. En el cuadro de diálogo Nuevo proyecto, seleccione el nodo **Visual C#** seguido del nodo **Web**.
    1. Seleccione la plantilla de proyecto **Aplicación web de ASP.NET Core**.
    1. En el cuadro de texto **Nombre**, escriba "SentimentRazor".
    1. Asegúrese de que **Colocar la solución y el proyecto en el mismo directorio** está **desactivado** (VS 2019) o que **Crear directorio para la solución** está **activado** (VS 2017).
    1. Seleccione el botón **Aceptar**.
    1. Elija **Aplicación web** en la ventana que muestra los distintos tipos de proyectos de ASP.NET Core y, luego, haga clic en el botón **Aceptar**.

## <a name="prepare-and-understand-the-data"></a>Preparar y entender los datos

Descargue el [conjunto de datos detox de Wikipedia](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv). Cuando se abra la página web, haga clic con el botón derecho en la página, seleccione **Guardar como** y guarde el archivo en cualquier parte del equipo.

Cada fila del conjunto de datos *wikipedia-detox-250-line-data.tsv* presenta una opinión distinta que un usuario deja en Wikipedia. La primera columna representa el sentimiento del texto (0 indica no tóxico, 1 indica tóxico) y la segunda columna representa el comentario que deja el usuario. Las columnas están separadas por tabulaciones. Los datos tienen un aspecto similar al siguiente:

| Opinión | SentimentText |
| :---: | :---: |
1 | ==RUDE== Dude, you are rude upload that carl picture back, or else. (Oye, vuelve a subir esa foto de Carl o te las verás conmigo).
1 | == OK! ==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!! (BUENO, ENTONCES VOY A VANDALIZAR ALGUNAS WIKI).
0 | I hope this helps. (Espero que esto ayude).

## <a name="choose-a-scenario"></a>Elección de un escenario

![Asistente para el generador de modelos en Visual Studio](./media/sentiment-analysis-model-builder/model-builder-screen.png)

Para entrenar el modelo, deberá seleccionarlo en la lista de escenarios de aprendizaje automático disponibles proporcionada por el Generador de modelos.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto *SentimentRazor* y seleccione **Agregar** > **Machine Learning**.
1. En este ejemplo, el escenario es el análisis de sentimiento. En el paso *Escenario* de la herramienta Generador de modelos, seleccione el escenario **Análisis de sentimiento**.

## <a name="load-the-data"></a>Carga de los datos

El Generador de modelos acepta datos de dos orígenes, una base de datos de SQL Server o un archivo local en formato `csv` o `tsv`.

1. En el paso de datos de la herramienta Generador de modelos, seleccione **Archivo** en la lista desplegable origen de datos.
1. Seleccione el botón junto al cuadro de texto **Seleccionar un archivo** y use el Explorador de archivos para examinar y seleccionar el archivo *wikipedia-detox-250-line-data.tsv*.
1. Elija **Sentimiento** en el menú desplegable **Column to Predict (Label)** (Columna para la predicción [etiqueta]).
1. Deje los valores predeterminados del menú desplegable **Input Columns (Features)** (Columnas de entrada [características]).
1. Seleccione el vínculo **Entrenar** para ir al paso siguiente en la herramienta Generador de modelos.

## <a name="train-the-model"></a>Entrenar el modelo

La tarea de aprendizaje automático que se usa para entrenar el modelo de análisis de opinión en este tutorial es la clasificación binaria. Durante el proceso de entrenamiento de modelos, el Generador de modelos entrena modelos independientes con diferentes opciones y algoritmos de clasificación binaria para encontrar el modelo con mejor rendimiento para el conjunto de datos.

El tiempo necesario para el entrenamiento del modelo es proporcional a la cantidad de datos. El generador de modelos selecciona automáticamente un valor predeterminado para **Tiempo de entrenamiento (segundos)** en función del tamaño del origen de datos.

1. Aunque el Generador de modelos establezca el valor de **Tiempo de entrenamiento (segundos)** en 10 segundos, debe aumentarlo a 30 segundos. El entrenamiento durante un período de tiempo más prolongado permite que el Generador de modelos explore un mayor número de algoritmos y combinación de parámetros en la búsqueda del mejor modelo.
1. Seleccione **Iniciar entrenamiento**.

    Durante el proceso de entrenamiento, los datos de progreso se muestran en la sección `Progress` del paso de entrenamiento.

    - En Estado se muestra el grado de finalización del proceso de entrenamiento.
    - En Mejor precisión se muestra la precisión del modelo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento. Una mayor precisión significa que el modelo realiza una predicción más correcta de los datos de prueba.
    - En Mejor algoritmo se muestra el nombre del algoritmo con mejor rendimiento que ha encontrado el Generador de modelos hasta el momento.
    - En Último algoritmo se muestra el nombre del algoritmo que ha usado más recientemente el Generador de modelos para entrenar el modelo.

1. Una vez que se complete el entrenamiento, seleccione el vínculo de **evaluación** para ir al paso siguiente.

## <a name="evaluate-the-model"></a>Evaluar el modelo

El resultado del paso de entrenamiento será un modelo que tenga el mejor rendimiento. En el paso de evaluación de la herramienta Generador de modelos, la sección de salida contendrá el algoritmo usado por el modelo con el mejor rendimiento en la entrada **Mejor modelo** junto con las métricas en **Modelo de mayor precisión**. Además de una tabla resumen que contiene los cinco mejores modelos y sus métricas.

Si no está satisfecho con las métricas de precisión, una forma sencilla de intentar mejorar la precisión del modelo es aumentar la cantidad de tiempo para entrenar el modelo o usar más datos. En caso contrario, seleccione el vínculo de **código** para ir al paso final de la herramienta Generador de modelos.

## <a name="add-the-code-to-make-predictions"></a>Incorporación del código para hacer predicciones

Se crearán dos proyectos como resultado del proceso de entrenamiento.

### <a name="reference-the-trained-model"></a>Referencia al modelo entrenado

1. En el paso de *código* de la herramienta Generador de modelos, seleccione **Agregar proyectos** para agregar los proyectos generados automáticamente a la solución.

    Los proyectos siguientes deben aparecer en el **Explorador de soluciones**:

    - *SentimentRazorML.ConsoleApp*: una aplicación de consola de .NET Core que contiene el entrenamiento del modelo y el código de predicción.
    - *SentimentRazorML.Model*: Una biblioteca de clases .NET Standard que contienen los modelos de datos que definen el esquema de entrada y salida de los datos del modelo, así como la versión guardada del modelo con mejor rendimiento durante el entrenamiento.

    En este tutorial, solo se usa el proyecto *SentimentRazorML.Model*, porque las predicciones se realizarán en la aplicación web *SentimentRazor* en lugar de hacerlo en la consola. Aunque *SentimentRazorML.ConsoleApp* no se usará para la puntuación, se puede usar para volver a entrenar el modelo con datos nuevos más adelante. No obstante, el reentrenamiento queda fuera del ámbito de este tutorial.

### <a name="configure-the-predictionengine-pool"></a>Configuración del grupo PredictionEngine

Para hacer una sola predicción, debe crear un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602). [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos. Además, tiene que crear una instancia de ella en cualquier lugar en que se necesite dentro de la aplicación. A medida que crece la aplicación, este proceso puede volverse difícil de administrar. Para mejorar el rendimiento y la seguridad para subprocesos, use una combinación de inserción de dependencias y el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación.

1. Instale el paquete *Microsoft.Extensions.ML* de NuGet:

    1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.
    1. Elija "nuget.org" como origen del paquete.
    1. Seleccione la pestaña **Examinar** y busque **Microsoft.Extensions.ML**.
    1. Seleccione el paquete en la lista y haga clic en el botón **Instalar**.
    1. Haga clic en el botón **Aceptar** en el cuadro de diálogo **Vista previa de los cambios**.
    1. Haga clic en el botón **Acepto** en el cuadro de diálogo **Aceptación de la licencia** si está de acuerdo con los términos de licencia de los paquetes que aparecen.

1. Abra el archivo *Startup.cs* en el proyecto *SentimentRazor*.
1. Agregue las instrucciones USING siguientes para hacer referencia al paquete de NuGet *Microsoft.Extensions.ML* y al proyecto *SentimentRazorML.Model*:

    ```csharp
    using System.IO;
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

1. Cree una variable global para almacenar la ubicación del archivo del modelo entrenado.

    ```csharp
    private readonly string _modelPath;
    ```

1. El archivo del modelo se almacena en el directorio de compilación junto con los archivos de ensamblado de la aplicación. Para facilitar el acceso, cree un método auxiliar llamado `GetAbsolutePath` después del método `Configure`.

    ```csharp
    public static string GetAbsolutePath(string relativePath)
    {
        FileInfo _dataRoot = new FileInfo(typeof(Program).Assembly.Location);
        string assemblyFolderPath = _dataRoot.Directory.FullName;

        string fullPath = Path.Combine(assemblyFolderPath, relativePath);
        return fullPath;
    }
    ```

1. Use el método `GetAbsolutePath` en el constructor de la clase `Startup` para establecer el `_modelPath`.

    ```csharp
    _modelPath = GetAbsolutePath("MLModel.zip");
    ```

1. Configure `PredictionEnginePool` para la aplicación en el método `ConfigureServices`:

    ```csharp
    services.AddPredictionEnginePool<ModelInput, ModelOutput>()
            .FromFile(_modelPath);
    ```

### <a name="create-sentiment-analysis-handler"></a>Creación de un controlador de análisis de sentimiento

Las predicciones se realizarán dentro de la página principal de la aplicación. Por tanto, se necesita un método que tome las entradas del usuario y use `PredictionEnginePool` para devolver una predicción.

1. Abra el archivo *Index.cshtml.cs* ubicado en el directorio *Pages* y agregue las instrucciones USING siguientes:

    ```csharp
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

    Para usar el `PredictionEnginePool` configurado en la clase `Startup`, debe insertarlo en el constructor del modelo donde quiere usarlo.

1. Agregue una variable para hacer referencia al `PredictionEnginePool` dentro de la clase `IndexModel`.

    ```csharp
    private readonly PredictionEnginePool<ModelInput, ModelOutput> _predictionEnginePool;
    ```

1. Cree un constructor en la clase `IndexModel` e inserte el servicio `PredictionEnginePool` en él.

    ```csharp
    public IndexModel(PredictionEnginePool<ModelInput, ModelOutput> predictionEnginePool)
    {
        _predictionEnginePool = predictionEnginePool;
    }
    ```

1. Cree un controlador de método que use `PredictionEnginePool` para hacer predicciones a partir de la información proporcionada por el usuario recibida desde la página web.

    1. Debajo del método `OnGet`, cree un método nuevo denominado `OnGetAnalyzeSentiment`.

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. Dentro del método `OnGetAnalyzeSentiment`, devuelva un sentimiento *neutral* si la información ingresada por el usuario es nula o está en blanco.

        ```csharp
        if (String.IsNullOrEmpty(text)) return Content("Neutral");
        ```

    1. Dada una entrada válida, cree una instancia nueva de `ModelInput`.

        ```csharp
        var input = new ModelInput { SentimentText = text };
        ```

    1. Use `PredictionEnginePool` para predecir el sentimiento.

        ```csharp
        var prediction = _predictionEnginePool.Predict(input);
        ```

    1. Convierta el valor `bool` de predicción en Tóxico o No tóxico con el código siguiente.

        ```csharp
        var sentiment = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";
        ```

    1. Por último, devuelva el sentimiento a la página web.

        ```csharp
        return Content(sentiment);
        ```

### <a name="configure-the-web-page"></a>Configuración de la página web

Los resultados que devuelve el `OnGetAnalyzeSentiment` se mostrarán de manera dinámica en la página web `Index`.

1. Abra el archivo *Index.cshtml* del directorio *Pages* y reemplace su contenido por el código siguiente:

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. A continuación, agregue el código de estilo CSS al final de la página *site.css* en el directorio *wwwroot\css*:

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. Después, agregue código para enviar entradas desde la página web al controlador `OnGetAnalyzeSentiment`.

    1. En el archivo *site.js* que se encuentra en el directorio *wwwroot\js*, cree una función llamada `getSentiment` para realizar una solicitud HTTP GET con la entrada del usuario al controlador `OnGetAnalyzeSentiment`.

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. A continuación, agregue otra función llamada `updateMarker` para actualizar dinámicamente la posición del marcador en la página web cuando se predice el sentimiento.

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. Cree una función de controlador de eventos llamada `updateSentiment` para obtener la entrada del usuario, envíela a la función `OnGetAnalyzeSentiment` mediante la función `getSentiment` y actualice el marcador con la función `updateMarker`.

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. Por último, registre el controlador de eventos y enlácelo al elemento `textarea` con el atributo `id=Message`.

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a>Ejecutar la aplicación

Ahora que la aplicación está configurada, ejecútela. Debería iniciarse en el explorador.

Cuando se inicie la aplicación, escriba *¡El Generador de modelos es genial!* en el área de texto. El sentimiento de predicción que aparece debe ser *Not Toxic* (No tóxico).

![Ventana en ejecución con la ventana de sentimiento de predicción](./media/sentiment-analysis-model-builder/web-app.png)

Si tiene que hacer referencia a los proyectos generados por el Generador de modelos más adelante en otra solución, puede encontrarlos en el directorio `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools`.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
>
> - Crear una aplicación Razor Pages de ASP.NET Core
> - Preparar y entender los datos
> - Elección de un escenario
> - Carga de los datos
> - Entrenar el modelo
> - Evaluar el modelo
> - Usar el modelo para las predicciones

### <a name="additional-resources"></a>Recursos adicionales

Para más información sobre los temas mencionados en este tutorial, visite estos recursos:

- [Escenarios del Generador de modelos](../automate-training-with-model-builder.md#scenarios)
- [Clasificación binaria](../resources/glossary.md#binary-classification)
- [Métricas del modelo de clasificación binaria](../resources/metrics.md#evaluation-metrics-for-binary-classification)

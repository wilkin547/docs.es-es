---
title: 'Tutorial: Clasificación de incidencias de soporte técnico (clasificación multiclase)'
description: Descubra cómo usar ML.NET en un escenario de clasificación multiclase para clasificar los problemas de GitHub y asignarlos a un área determinada.
ms.date: 01/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: f158b8dce81e00f652496cad4ec9217c516b3e9d
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739713"
---
# <a name="tutorial-categorize-support-issues-using-multiclass-classification-with-mlnet"></a>Tutorial: Clasificación multiclase de incidencias de soporte técnico con ML.NET

Este tutorial de ejemplo ilustra el uso de ML.NET para crear un clasificador de problemas de GitHub para entrenar un modelo que clasifica y predice la etiqueta de área para un problema de GitHub a través de una aplicación de consola de .NET Core con C# en Visual Studio.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> * Preparar los datos
> * Transformar los datos
> * Entrenar el modelo
> * Evaluar el modelo
> * Predecir con el modelo entrenado
> * Implementar y predecir con un modelo cargado

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.
* [Archivo de problemas de GitHub delimitado por pestañas (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).
* [Prueba de problemas de GitHub delimitado por pestañas (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

### <a name="create-a-project"></a>Crear un proyecto

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)** . En el cuadro de texto **Nombre**, escriba "GitHubIssueClassification" y, luego, seleccione el botón **Aceptar**.

2. Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Datos" y presione Entrar.

3. En el proyecto, cree un directorio denominado *Modelos* para guardar el modelo:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Modelos" y presione Entrar.

4. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML** y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

### <a name="prepare-your-data"></a>Preparar los datos

1. Descargue los conjuntos de datos [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) e [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) y guárdelos en la carpeta *Datos* que ha creado anteriormente. El primer conjunto de datos entrena el modelo de aprendizaje automático y el segundo puede usarse para evaluar su grado de precisión.

2. En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.tsv y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddUsings)]

Cree tres campos globales para contener las rutas de acceso a los archivos descargados recientemente y variables globales para `MLContext`,`DataView` y `PredictionEngine`:

* `_trainDataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.
* `_testDataPath` tiene la ruta de acceso al conjunto de datos utilizado para evaluar el modelo.
* `_modelPath` tiene la ruta de acceso donde se guarda el modelo entrenado.
* `_mlContext` es el elemento <xref:Microsoft.ML.MLContext> que proporciona el contexto de procesamiento.
* `_trainingDataView` es el elemento <xref:Microsoft.ML.IDataView> que se usa para procesar el conjunto de datos de entrenamiento.
* `_predEngine` es el elemento <xref:Microsoft.ML.PredictionEngine%602> que se usa para las predicciones únicas.

Agregue el código siguiente a la línea justo encima del método `Main` para especificar esas rutas de acceso y otras variables:

[!code-csharp[DeclareGlobalVariables](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DeclareGlobalVariables)]

Cree algunas clases para los datos de entrada y las predicciones. Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.

1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *GitHubIssueData.cs*. A continuación, seleccione el botón **Agregar**.

    Se abre el archivo *GitHubIssueData.cs* en el editor de código. Agregue la siguiente instrucción `using` a la parte superior de *GitHubIssueData.cs*:

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/GitHubIssueData.cs#AddUsings)]

Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `GitHubIssue` y `IssuePrediction`, al archivo *GitHubIssueData.cs*:

[!code-csharp[DeclareGlobalVariables](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/GitHubIssueData.cs#DeclareTypes)]

`label` es la columna que quiere predecir. Los valores de `Features` identificados son las entradas que se proporcionan al modelo para predecir la etiqueta.

Use [LoadColumnAttribute](xref:Microsoft.ML.Data.LoadColumnAttribute) para especificar los índices de las columnas de origen en el conjunto de datos.

`GitHubIssue` es la clase de conjunto de datos de entrada y contiene los siguientes campos de <xref:System.String>:

* `ID`, la primera columna (id. de problema de GitHub).
* `Area`, la segunda columna (la predicción para el entrenamiento).
* `Title`, la tercera columna (título del problema de GitHub) es el primer `feature` usado para predecir el `Area`
* `Description`, la cuarta columna es el segundo `feature` usado para predecir el `Area`

`IssuePrediction` es la clase usada para la predicción una vez entrenado el modelo. Tiene un solo elemento `string` (`Area`) y un atributo `PredictedLabel` `ColumnName`.  `PredictedLabel` se usa durante la predicción y la evaluación. Para la evaluación, se utiliza una entrada con los datos de entrenamiento, los valores de predicción y el modelo.

Todas las operaciones de ML.NET se inician en la clase [MLContext](xref:Microsoft.ML.MLContext). La inicialización de `mlContext` crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Es similar, conceptualmente, al `DBContext` en `Entity Framework`.

### <a name="initialize-variables-in-main"></a>Inicializar variables en Main

Inicialice la variante global `_mlContext` con una nueva instancia de `MLContext` usando una inicialización aleatoria (`seed: 0`) para obtener resultados repetibles o deterministas en varios entrenamientos.  Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:

[!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a>Carga de los datos

ML.NET utiliza la [clase IDataView](xref:Microsoft.ML.IDataView) como una forma flexible y eficiente de describir datos tabulares de texto o numéricos. `IDataView` puede cargar archivos de texto o en tiempo real (por ejemplo, una base de datos SQL o archivos de registro).

Para inicializar y cargar la variable global `_trainingDataView` con el fin de volver a usarla para la canalización, agregue el siguiente código después de la inicialización de `mlContext`:

[!code-csharp[LoadTrainData](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#LoadTrainData)]

[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo. Toma las variables de ruta de acceso de datos y devuelve `IDataView`.

Agregue lo siguiente como la siguiente línea de código en el método `Main`:

[!code-csharp[CallProcessData](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallProcessData)]

El método `ProcessData` ejecuta las tareas siguientes:

* Extrae y transforma los datos.
* Devuelve la canalización de procesamiento.

Cree el método `ProcessData`, justo después del método `Main`, mediante el código siguiente:

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a>Extraer características y transformar los datos

Como quiere predecir la etiqueta de GitHub de área para un `GitHubIssue`, utilice el método [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) para transformar la columna `Area` en una columna `Label` de tipo de clave numérico (un formato admitido por los algoritmos de clasificación) y agréguela como nueva columna de conjunto de datos:

[!code-csharp[MapValueToKey](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#MapValueToKey)]

Después, llame a `mlContext.Transforms.Text.FeaturizeText` que transforma las columnas de texto (`Title` y `Description`) en un vector numérico para cada una de nombre `TitleFeaturized` y `DescriptionFeaturized`. Anexe la caracterización para ambas columnas a la canalización usando el siguiente código:

[!code-csharp[FeaturizeText](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#FeaturizeText)]

El último paso de preparación de datos combina todas las columnas de característica en la columna **Características** con el método [Concatenate()](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A). De forma predeterminada, un algoritmo de aprendizaje solo procesa las características de la columna **Features**. Anexe esta transformación a la canalización usando el siguiente código:

[!code-csharp[Concatenate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Concatenate)]

 A continuación, anexe <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> para almacenar en caché el objeto DataView, de modo que pueda obtener un mayor rendimiento al iterar los datos varias veces con la caché, como se muestra en el código siguiente:

[!code-csharp[AppendCache](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AppendCache)]

> [!WARNING]
> Use AppendCacheCheckpoint para conjuntos de datos pequeños o medianos para reducir el tiempo de entrenamiento. NO lo use (quite. AppendCacheCheckpoint()) al tratar con grandes conjuntos de datos.

Devuelva la canalización al final del método `ProcessData`.

[!code-csharp[ReturnPipeline](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#ReturnPipeline)]

En este paso se controla el preprocesamiento y la caracterización. El uso de componentes adicionales disponibles en ML.NET permite conseguir mejores resultados con el modelo.

## <a name="build-and-train-the-model"></a>Creación y entrenamiento del modelo

Agregue la siguiente llamada al método `BuildAndTrainModel` como siguiente línea de código del método `Main`:

[!code-csharp[CallBuildAndTrainModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallBuildAndTrainModel)]

El método `BuildAndTrainModel` ejecuta las tareas siguientes:

* Crea la clase de algoritmo de entrenamiento.
* Entrena el modelo.
* Predice el área según los datos de entrenamiento.
* Devuelve el modelo.

Cree el método `BuildAndTrainModel`, justo después del método `Main`, mediante el código siguiente:

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

### <a name="about-the-classification-task"></a>Acerca de la tarea de clasificación

La clasificación es una tarea de aprendizaje automático que usa datos para **determinar** la categoría, el tipo o la clase de un elemento o fila de datos y suele ser uno de los siguientes tipos:

* Binario: A o B.
* Multiclase: varias categorías que se pueden predecir mediante el uso de un único modelo.

Para este tipo de problema, use un algoritmo de aprendizaje de clasificación multiclase, ya que la predicción de categoría de problema puede ser una de varias categorías (multiclase) en lugar de solo dos (binaria).

Anexe el algoritmo de aprendizaje automático a las definiciones de transformación de datos agregando lo siguiente como primera línea de código en `BuildAndTrainModel()`:

[!code-csharp[AddTrainer](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddTrainer)]

[SdcaMaximumEntropy](xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer) es el algoritmo de entrenamiento de clasificación multiclase. Se anexa a `pipeline` y acepta `Title` y `Description` (`Features`) caracterizados y los parámetros de entrada `Label` para aprender de los datos históricos.

### <a name="train-the-model"></a>Entrenar el modelo

Ajuste el modelo a los datos `splitTrainSet` y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `BuildAndTrainModel()`:

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#TrainModel)]

El método `Fit()` entrena el modelo transformando el conjunto de datos y aplicando el entrenamiento.

[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite pasar datos y luego realizar una predicción en una única instancia de datos. Agregue esto como siguiente línea en el método `BuildAndTrainModel()`:

[!code-csharp[CreatePredictionEngine1](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a>Predecir con el modelo entrenado

Agregue un problema de GitHub para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `GitHubIssue`:

[!code-csharp[CreateTestIssue1](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreateTestIssue1)]

El uso de la función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción en una sola fila de datos:

[!code-csharp[Predict](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a>Uso del modelo: resultados de la predicción

Muestre `GitHubIssue` y la predicción de la etiqueta `Area` correspondiente para compartir los resultados y actuar en consecuencia.  Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:

[!code-csharp[OutputPrediction](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a>Devolución del modelo entrenado para su uso para la evaluación

Devuelva el modelo al final del método `BuildAndTrainModel`.

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a>Evaluar el modelo

Ahora que ha creado y entrenado el modelo, debe evaluarlo con otro conjunto de datos para el control de calidad y la validación. En el método `Evaluate`, el modelo creado en `BuildAndTrainModel` se pasa para ser evaluado. Cree el método `Evaluate`, justo después de `BuildAndTrainModel`, como en el código siguiente:

```csharp
public static void Evaluate(DataViewSchema trainingDataViewSchema)
{

}
```

El método `Evaluate` ejecuta las tareas siguientes:

* Carga el conjunto de datos de prueba.
* Crea el evaluador multiclase.
* Evalúa el modelo y crea métricas.
* Muestra las métricas.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `BuildAndTrainModel`, utilizando el código siguiente:

[!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallEvaluate)]

Como hizo anteriormente con el conjunto de datos de entrenamiento, cargue el conjunto de datos de prueba agregando el código siguiente al método `Evaluate`:

[!code-csharp[LoadTestDataset](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#LoadTestDataset)]

El método [Evaluate()](xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A) calcula las métricas de calidad del modelo utilizando el conjunto de datos especificado. Devuelve un objeto <xref:Microsoft.ML.Data.MulticlassClassificationMetrics> que contiene las métricas totales calculadas por evaluadores de clasificación multiclase.
Para mostrar las métricas a fin de determinar la calidad del modelo, primero tendrá que obtenerlas.
Observe el uso del método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) de la variable global `_trainedModel` de aprendizaje automático (una [ITransformer](xref:Microsoft.ML.ITransformer)) que da entrada a las características y devuelve predicciones. Agregue el código siguiente al método `Evaluate` como la siguiente línea:

[!code-csharp[Evaluate](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#Evaluate)]

Las siguientes métricas se evalúan para la clasificación multiclase:

* Microprecisión: todos los pares de ejemplo y clase contribuyen del mismo modo a la métrica de precisión.  Quiere que la microprecisión esté lo más cerca posible de 1.

* Macroprecisión: todas las clases contribuyen del mismo modo a la métrica de precisión. Las clases minoritarias tienen el mismo peso que las clases más grandes. Quiere que la macroprecisión esté lo más cerca posible de 1.

* Pérdida de registro: vea [Pérdida de registro](../resources/glossary.md#log-loss). Le recomendamos que la pérdida logarítmica esté lo más cerca posible de 0.

* Reducción de la pérdida de registro: parte de [-inf, 1.00], donde 1.00 equivale a una predicción perfecta, y 0 indica una predicción aproximada. Le recomendamos que la reducción de la pérdida de registro esté lo más cerca posible de 1.

### <a name="displaying-the-metrics-for-model-validation"></a>Mostrar las métricas para la validación del modelo

Utilice el código siguiente para mostrar las métricas, compartir los resultados y, a continuación, trabajar con ellos:

[!code-csharp[DisplayMetrics](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DisplayMetrics)]

### <a name="save-the-model-to-a-file"></a>Guardar el modelo en un archivo

Una vez que esté satisfecho con el modelo, guárdelo en un archivo para hacer predicciones más adelante o en otra aplicación. Agregue el código siguiente al método `Evaluate` .

[!code-csharp[SnippetCallSaveModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetCallSaveModel)]

Cree el método `SaveModelAsFile` debajo del método `Evaluate`.

```csharp
private static void SaveModelAsFile(MLContext mlContext,DataViewSchema trainingDataViewSchema, ITransformer model)
{

}
```

Agregue el código siguiente al método `SaveModelAsFile`. Este código usa el método [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) para serializar y almacenar el modelo entrenado como archivo ZIP.

[!code-csharp[SnippetSaveModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetSaveModel)]

## <a name="deploy-and-predict-with-a-model"></a>Implementación y predicción con un modelo

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:

[!code-csharp[CallPredictIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CallPredictIssue)]

Cree el método `PredictIssue`, justo después del método `Evaluate` (y justo antes del método `SaveModelAsFile`) con el código siguiente:

```csharp
private static void PredictIssue()
{

}
```

El método `PredictIssue` ejecuta las tareas siguientes:

* Carga el modelo guardado
* Crea un único problema de datos de prueba.
* Predice el área según los datos de prueba.
* Combina datos de prueba y predicciones para la generación de informes.
* Muestra los resultados de la predicción.

Cargue el modelo guardado en la aplicación agregando el código siguiente al método `PredictIssue`:

[!code-csharp[SnippetLoadModel](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#SnippetLoadModel)]

Agregue un problema de GitHub para probar la predicción del modelo entrenado en el método `Predict` mediante la creación de una instancia de `GitHubIssue`:

[!code-csharp[AddTestIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#AddTestIssue)]

Como hizo anteriormente, cree una instancia de `PredictionEngine` con el código siguiente:

[!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#CreatePredictionEngine)]

[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos. Es aceptable usarlo en entornos de un solo subproceso o prototipo. Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación. Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

> [!NOTE]
> La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.

Use `PredictionEngine` para predecir la etiqueta de GitHub de área agregando el código siguiente al método `PredictIssue` para la predicción:

[!code-csharp[PredictIssue](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a>Uso del modelo cargado para la predicción

Muestre `Area` para poder categorizar el problema y actuar en consecuencia. Cree una visualización para los resultados mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:

[!code-csharp[DisplayResults](~/samples/snippets/machine-learning/GitHubIssueClassification/csharp/Program.cs#DisplayResults)]

## <a name="results"></a>Resultados

Los resultados deberían ser similares a los indicados a continuación. A medida que la canalización procesa, muestra mensajes. Puede ver las advertencias o mensajes de procesamiento. Estos mensajes se han quitado de los resultados siguientes para mayor claridad.

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.738
*       MacroAccuracy:    0.668
*       LogLoss:          .919
*       LogLossReduction: .643
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

¡Enhorabuena! Ya ha creado correctamente un modelo de aprendizaje automático para clasificar y predecir una etiqueta Área de un problema de GitHub. Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
>
> * Preparar los datos
> * Transformar los datos
> * Entrenar el modelo
> * Evaluar el modelo
> * Predecir con el modelo entrenado
> * Implementar y predecir con un modelo cargado

Siga con el siguiente tutorial para obtener más información
> [!div class="nextstepaction"]
> [Predictor de tarifa de taxi](predict-prices.md)

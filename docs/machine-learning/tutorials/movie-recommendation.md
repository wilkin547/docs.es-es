---
title: 'Tutorial: Creación de un recomendador de películas (factorización matricial)'
description: Este tutorial muestra cómo compilar una recomendación de películas con ML.NET en una consola de aplicación de .NET Core. Los pasos utilizan C# y Visual Studio 2019.
author: briacht
ms.date: 06/30/2020
ms.custom: mvc, title-hack-0516
ms.topic: tutorial
ms.openlocfilehash: 9171a6ca073e6296220ebcb874258b6893b2974f
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104875361"
---
# <a name="tutorial-build-a-movie-recommender-using-matrix-factorization-with-mlnet"></a>Tutorial: Creación de un recomendador de películas mediante factorización matricial con ML.NET

Este tutorial muestra cómo compilar una recomendación de películas con ML.NET en una consola de aplicación de .NET Core. Los pasos utilizan C# y Visual Studio 2019.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> * Seleccionar un algoritmo de Machine Learning
> * Preparar y cargar los datos
> * Compilar y entrenar un modelo
> * Evaluar un modelo
> * Implementar y consumir un modelo

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/main/machine-learning/tutorials/MovieRecommendation).

## <a name="machine-learning-workflow"></a>Flujo de trabajo del aprendizaje automático

Usará los pasos siguientes para realizar la tarea, así como cualquier otra tarea de ML.NET:

1. [Cargar los datos](#load-your-data)
2. [Compilar y entrenar el modelo](#build-and-train-your-model)
3. [Evaluar el modelo](#evaluate-your-model)
4. [Usar el modelo](#use-your-model)

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

## <a name="select-the-appropriate-machine-learning-task"></a>Seleccionar la tarea de aprendizaje automático adecuada

Hay varias maneras de enfocar los problemas vinculados a las recomendaciones, como recomendar una lista de películas o recomendar una lista de productos relacionados. En este caso, predecirá qué clasificación (de 1 a 5) asignará un usuario a una película concreta y recomendará esa película si es superior a un umbral definido (cuanto mayor sea la clasificación, más probable será que a un usuario le guste una película concreta).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

### <a name="create-a-project"></a>Crear un proyecto

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)** . En el cuadro de texto **Nombre**, escriba "MovieRecommender" y haga clic en el botón **Aceptar**.

2. Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Datos" y presione Entrar.

3. Instale los paquetes NuGet **Microsoft.ML** y **Microsoft.ML.Recommender**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione el paquete en la lista y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados. Repita estos pasos para **Microsoft.ML.Recommender**.

4. Agregue las instrucciones `using` siguientes en la parte superior del archivo *Program.cs*:

    [!code-csharp[UsingStatements](./snippets/movie-recommendation/csharp/Program.cs#UsingStatements "Add necessary usings")]

### <a name="download-your-data"></a>Descarga de los datos

1. Descargue los dos conjuntos de datos y guárdelos en la carpeta *Datos* que creó anteriormente:

   * Haga clic con el botón derecho en [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/main/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) y seleccione "Save Link (or Target) As…" ("Guardar vínculo (o destino) como…").
   * Haga clic con el botón derecho en [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/main/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) y seleccione "Save Link (or Target) As…" ("Guardar vínculo (o destino) como…").

     Asegúrese de guardar los archivos \*.csv en la carpeta *Datos*. Si los guarda en otro lugar, recuerde que debe mover los archivos \*.csv a la carpeta *Datos*.

2. En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.csv y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

   ![GIF de un usuario que selecciona Copiar si es posterior en VS.](./media/movie-recommendation/copy-to-output-if-newer.gif)

## <a name="load-your-data"></a>Carga de los datos

El primer paso en el proceso de ML.NET consiste en preparar y cargar los datos de entrenamiento y prueba del modelo.

Los datos de las clasificaciones de recomendación se dividen en conjuntos de datos `Train` y `Test`. Los datos `Train` se usan para ajustar el modelo, mientras que los datos `Test` sirven para realizar predicciones con el modelo entrenado y evaluar el rendimiento del modelo. Los datos `Train` y `Test` suelen dividirse con una proporción de 80/20.

A continuación se muestra una vista previa de los datos de los archivos \*.csv:

![Captura de pantalla de la vista previa del conjunto de datos CSV.](./media/movie-recommendation/csv-file-dataset-preview.png)

En los archivos \*.csv, hay cuatro columnas:

* `userId`
* `movieId`
* `rating`
* `timestamp`

En Machine Learning, las columnas que se usan para realizar una predicción se denominan [Features](../resources/glossary.md#feature) (Características), mientras que la columna con la predicción devuelta recibe el nombre de [Label](../resources/glossary.md#label) (Etiqueta).

En su caso, quiere predecir clasificaciones de películas, por lo que la columna de clasificación es `Label`. Las otras tres columnas (`userId`, `movieId` y `timestamp`) son `Features` que se usan para predecir la `Label`.

| Características      | Etiqueta         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |
| `timestamp`     |               |

Usted decide qué `Features` se usan para predecir la `Label`. También puede usar métodos como la [importancia de la característica de permutación](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md) para ayudar a seleccionar las mejores `Features`.

En este caso, debe eliminar la columna `timestamp` como `Feature` porque la marca de tiempo no afecta realmente a la manera en que un usuario clasifica una película determinada y, por tanto, no contribuye a realizar una predicción más exacta:

| Características      | Etiqueta         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |

Después, debe definir la estructura de datos para la clase de entrada.

Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nuevo elemento**.

2. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *MovieRatingData.cs*. A continuación, seleccione el botón **Agregar**.

Se abre el archivo *MovieRatingData.cs* en el editor de código. Agregue la siguiente instrucción `using` a la parte superior de *MovieRatingData.cs*:

```csharp
using Microsoft.ML.Data;
```

Cree una clase denominada `MovieRating`. Para ello, quite la definición de clase existente y agregue el siguiente código en *MovieRatingData.cs*:

[!code-csharp[MovieRatingClass](./snippets/movie-recommendation/csharp/MovieRatingData.cs#MovieRatingClass "Add the Movie Rating class")]

`MovieRating` especifica una clase de datos de entrada. El atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) especifica qué columnas (por índice de columna) del conjunto de datos se deben cargar. Las columnas `userId` y `movieId` son las `Features` (las entradas que proporcionará al modelo para predecir la `Label`), y la columna de clasificación es la `Label` que predecirá (la salida del modelo).

Cree otra clase (`MovieRatingPrediction`) para representar los resultados predichos. Para ello, agregue el código siguiente después de la clase `MovieRating` en *MovieRatingData.cs*:

[!code-csharp[PredictionClass](./snippets/movie-recommendation/csharp/MovieRatingData.cs#PredictionClass "Add the Movie Prediction Class")]

En *Program.cs*, reemplace `Console.WriteLine("Hello World!")` por el código siguiente dentro de `Main()`:

[!code-csharp[MLContext](./snippets/movie-recommendation/csharp/Program.cs#MLContext "Add MLContext")]

La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Como concepto, se parece a `DBContext` en Entity Framework.

Después de `Main()`, cree un método denominado `LoadData()`:

```csharp
public static (IDataView training, IDataView test) LoadData(MLContext mlContext)
{

}
```

> [!NOTE]
> Este método generará un error hasta que agregue una instrucción return en los pasos siguientes.

Inicialice las variables de ruta de acceso de datos, cargue los datos de los archivos \*.csv y devuelva los datos `Train` y `Test` como objetos `IDataView`. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en `LoadData()`:

[!code-csharp[LoadData](./snippets/movie-recommendation/csharp/Program.cs#LoadData "Load data from data paths")]

Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView). `IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto). Los datos se pueden cargar desde un archivo de texto o en tiempo real (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.

[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo. Toma las variables de ruta de acceso de datos y devuelve `IDataView`. En este caso, usted proporciona la ruta de acceso a los archivos `Test` y `Train` e indica el encabezado del archivo de texto (para que pueda usar correctamente los nombres de columna) y el separador de datos de caracteres de coma (el separador predeterminado es el tabulador).

Agregue este código en el método `Main()` para llamar al método `LoadData()` y devolver los datos `Train` y `Test`:

[!code-csharp[LoadDataMain](./snippets/movie-recommendation/csharp/Program.cs#LoadDataMain "Add LoadData method to Main")]

## <a name="build-and-train-your-model"></a>Compilación y entrenamiento del modelo

Cree el método `BuildAndTrainModel()`, justo después del método `LoadData()`, mediante el código siguiente:

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView trainingDataView)
{

}
```

> [!NOTE]
> Este método generará un error hasta que agregue una instrucción return en los pasos siguientes.

Defina las transformaciones de datos mediante la adición del código siguiente a `BuildAndTrainModel()`:

[!code-csharp[DataTransformations](./snippets/movie-recommendation/csharp/Program.cs#DataTransformations "Define data transformations")]

Puesto que `userId` y `movieId` representan usuarios y títulos de películas, en lugar de valores reales, debe usar el método [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) para transformar cada `userId` y `movieId` en una columna `Feature` de tipo de clave numérica (un formato que aceptan los algoritmos de recomendación) y agregarlos como nuevas columnas del conjunto de datos:

| userId | movieId | Etiqueta | userIdEncoded | movieIdEncoded |
| ------------- |:-------------:| -----:|-----:|-----:|
| 1 | 1 | 4 | userKey1 | movieKey1 |
| 1 | 3 | 4 | userKey1 | movieKey2 |
| 1 | 6 | 4 | userKey1 | movieKey3 |

Elija el algoritmo de Machine Learning y anéxelo a las definiciones de transformación de datos. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en `BuildAndTrainModel()`:

[!code-csharp[AddAlgorithm](./snippets/movie-recommendation/csharp/Program.cs#AddAlgorithm "Add the training algorithm with options")]

[MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) es el algoritmo de entrenamiento de recomendación.  La [factorización matricial](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) es una manera común de enfocar la recomendación cuando se dispone de datos que muestran cómo los usuarios clasificaron anteriormente los productos, que es el caso de los conjuntos de datos de este tutorial. Existen otros algoritmos de recomendación para cuando se dispone de datos diferentes (vea más adelante la sección [Otros algoritmos de recomendación](#other-recommendation-algorithms) para obtener más información).

En este caso, el algoritmo `Matrix Factorization` usa un método denominado "filtrado de colaboración", que presupone que si el Usuario 1 tiene la misma opinión que el Usuario 2 en un tema determinado, lo más probable es que el Usuario 1 piense lo mismo que el Usuario 2 sobre otro tema.

Por ejemplo, si el Usuario 1 y el Usuario 2 clasifican las películas de forma similar, lo más probable es que el Usuario 2 disfrute de una película que el Usuario 1 ha visto y ha clasificado con una puntuación alta:

| | `Incredibles 2 (2018)` | `The Avengers (2012)` | `Guardians of the Galaxy (2014)` |
| -------------:|-------------:| -----:|-----:|
| Usuario 1 | Ha visto la película y le ha gustado | Ha visto la película y le ha gustado | Ha visto la película y le ha gustado |
| Usuario 2 | Ha visto la película y le ha gustado | Ha visto la película y le ha gustado | No ha visto la película. RECOMENDARLA |

El instructor `Matrix Factorization` tiene varias [opciones](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), sobre las que puede informarse más adelante en la sección [Hiperparámetros de algoritmo](#algorithm-hyperparameters).

Ajuste el modelo a los datos `Train` y devuelva el modelo entrenado. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `BuildAndTrainModel()`:

[!code-csharp[FitModel](./snippets/movie-recommendation/csharp/Program.cs#FitModel "Call the Fit method and return back the trained model")]

El método [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) entrena el modelo con el conjunto de datos de entrenamiento proporcionado. Técnicamente, ejecuta las definiciones de `Estimator`, para lo que transforma los datos y aplica el entrenamiento, y devuelve el modelo entrenado, que es un `Transformer`.

Para obtener más información sobre el flujo de trabajo de entrenamiento de modelos en ML.NET, vea [¿Qué es ML.NET y cómo funciona?](../how-does-mldotnet-work.md#code-workflow).

Agregue lo que se indica a continuación como la siguiente líneas de código en el método `Main()` para llamar al método `BuildAndTrainModel()` y devolver el modelo entrenado:

[!code-csharp[BuildTrainModelMain](./snippets/movie-recommendation/csharp/Program.cs#BuildTrainModelMain "Add BuildAndTrainModel method in Main")]

## <a name="evaluate-your-model"></a>Evaluación del modelo

Una vez que haya entrenado el modelo, use los datos de prueba para evaluar el rendimiento del modelo.

Cree el método `EvaluateModel()`, justo después del método `BuildAndTrainModel()`, mediante el código siguiente:

```csharp
public static void EvaluateModel(MLContext mlContext, IDataView testDataView, ITransformer model)
{

}
```

Transforme los datos `Test` mediante la adición del código siguiente a `EvaluateModel()`:

[!code-csharp[Transform](./snippets/movie-recommendation/csharp/Program.cs#Transform "Transform the test data")]

El método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) realiza predicciones para varias filas de entrada proporcionadas de un conjunto de datos de prueba.

Para evaluar el modelo, agregue lo que se indica a continuación como la siguiente línea de código en el método `EvaluateModel()`:

[!code-csharp[Evaluate](./snippets/movie-recommendation/csharp/Program.cs#Evaluate "Evaluate the model using predictions from the test data")]

Una vez que se ha establecido la predicción, el método [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) valora el modelo, que compara los valores predichos con las `Labels` reales del conjunto de datos de prueba y devuelve métricas sobre el rendimiento del modelo.

Imprima las métricas de evaluación en la consola. Para ello, agregue lo que se indica a continuación como la siguiente línea de código en el método `EvaluateModel()`:

[!code-csharp[PrintMetrics](./snippets/movie-recommendation/csharp/Program.cs#PrintMetrics "Print the evaluation metrics")]

Agregue lo que se indica a continuación como la siguiente línea de código en el método `Main()` para llamar al método `EvaluateModel()`:

[!code-csharp[EvaluateModelMain](./snippets/movie-recommendation/csharp/Program.cs#EvaluateModelMain "Add EvaluateModel method in Main")]

Por el momento, la salida debe ser similar a la del texto siguiente:

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5403   3.1262e+05
   1       0.9221   1.6030e+05
   2       0.8687   1.5046e+05
   3       0.8416   1.4584e+05
   4       0.8142   1.4209e+05
   5       0.7849   1.3907e+05
   6       0.7544   1.3594e+05
   7       0.7266   1.3361e+05
   8       0.6987   1.3110e+05
   9       0.6751   1.2948e+05
  10       0.6530   1.2766e+05
  11       0.6350   1.2644e+05
  12       0.6197   1.2541e+05
  13       0.6067   1.2470e+05
  14       0.5953   1.2382e+05
  15       0.5871   1.2342e+05
  16       0.5781   1.2279e+05
  17       0.5713   1.2240e+05
  18       0.5660   1.2230e+05
  19       0.5592   1.2179e+05
=============== Evaluating the model ===============
Rms: 0.994051469730769
RSquared: 0.412556298844873
```

En esta salida, hay 20 iteraciones. En cada iteración, la medida de error disminuye y converge cada vez más hacia 0.

El valor `root of mean squared error` (RMS o RMSE) se usa para medir las diferencias entre los valores previstos por un modelo y los valores observados en un conjunto de datos de prueba. Técnicamente, es la raíz cuadrada de la media de los cuadrados de los errores. Cuanto menor sea su valor, mejor será el modelo.

`R Squared` indica en qué grado los datos se ajustan a un modelo. Va de 0 a 1. Un valor de 0 significa que los datos son aleatorios o no pueden ajustarse al modelo. Un valor de 1 significa que el modelo coincide exactamente con los datos. Le interesa que la puntuación de `R Squared` esté lo más cerca posible de 1.

La creación de modelos correctos es un proceso iterativo. Este modelo tiene una calidad inicial más baja, ya que el tutorial utiliza pequeños conjuntos de datos para proporcionar un entrenamiento rápido del modelo. Si no está satisfecho con la calidad del modelo, puede intentar mejorarlo proporcionando conjuntos de datos de entrenamiento más grandes o eligiendo algoritmos de entrenamiento distintos con diferentes hiperparámetros para cada algoritmo. Para más información, revise la sección [Mejora del modelo](#improve-your-model) a continuación.

## <a name="use-your-model"></a>Uso del modelo

Ahora puede usar el modelo entrenado para realizar predicciones sobre datos nuevos.

Cree el método `UseModelForSinglePrediction()`, justo después del método `EvaluateModel()`, mediante el código siguiente:

```csharp
public static void UseModelForSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

Use `PredictionEngine` para predecir la clasificación. Para ello, agregue el código siguiente a `UseModelForSinglePrediction()`:

[!code-csharp[PredictionEngine](./snippets/movie-recommendation/csharp/Program.cs#PredictionEngine "Create Prediction Engine")]

[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos. Es aceptable usarlo en entornos de un solo subproceso o prototipo. Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación. Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

> [!NOTE]
> La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.

Cree una instancia de `MovieRating` denominada `testInput` y pásela al motor de predicción. Para ello, agregue lo que se indica a continuación como las siguientes líneas de código en el método `UseModelForSinglePrediction()`:

[!code-csharp[MakeSinglePrediction](./snippets/movie-recommendation/csharp/Program.cs#MakeSinglePrediction "Make a single prediction with the Prediction Engine")]

La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción en una sola columna de datos.

Después, puede usar `Score`, o la clasificación predicha, para determinar si quiere recomendar la película con el movieId 10 al usuario 6. Cuanto más alto sea `Score`, más probable será que a un usuario le guste una película concreta. En este caso, supongamos que recomienda películas con una clasificación predicha superior a 3,5.

Para imprimir los resultados, agregue lo que se indica a continuación como las siguientes líneas de código en el método `UseModelForSinglePrediction()`:

[!code-csharp[PrintResults](./snippets/movie-recommendation/csharp/Program.cs#PrintResults "Print the recommendation prediction results")]

Agregue lo que se indica a continuación como la siguiente línea de código en el método `Main()` para llamar al método `UseModelForSinglePrediction()`:

[!code-csharp[UseModelMain](./snippets/movie-recommendation/csharp/Program.cs#UseModelMain "Add UseModelForSinglePrediction method in Main")]

La salida de este método debe ser similar a la del texto siguiente:

```console
=============== Making a prediction ===============
Movie 10 is recommended for user 6
```

### <a name="save-your-model"></a>Guardado del modelo

Para usar el modelo con el objeto de realizar predicciones en aplicaciones de usuario final, primero debe guardarlo.

Cree el método `SaveModel()`, justo después del método `UseModelForSinglePrediction()`, mediante el código siguiente:

```csharp
public static void SaveModel(MLContext mlContext, DataViewSchema trainingDataViewSchema, ITransformer model)
{

}
```

Para guardar el modelo entrenado, agregue el código siguiente en el método `SaveModel()`:

[!code-csharp[SaveModel](./snippets/movie-recommendation/csharp/Program.cs#SaveModel "Save the model to a zip file")]

Este método guarda el modelo entrenado en un archivo .zip (en la carpeta "Datos"), que puede usarse después en otras aplicaciones .NET para realizar predicciones.

Agregue lo que se indica a continuación como la siguiente línea de código en el método `Main()` para llamar al método `SaveModel()`:

[!code-csharp[SaveModelMain](./snippets/movie-recommendation/csharp/Program.cs#SaveModelMain "Create SaveModel method in Main")]

### <a name="use-your-saved-model"></a>Uso del modelo guardado

Una vez que haya guardado el modelo entrenado, puede usarlo en entornos diferentes. Consulte [Guardar y cargar modelos entrenados](../how-to-guides/save-load-machine-learning-models-ml-net.md) para obtener información sobre cómo poner en marcha un modelo de aprendizaje automático entrenado en aplicaciones.

## <a name="results"></a>Resultados

Después de seguir los pasos anteriores, ejecute la aplicación de consola (CTRL + F5). Los resultados de la predicción anterior deben ser similares a lo que se indica a continuación. Es posible que vea advertencias o mensajes de procesamiento, si bien se han quitado de los resultados siguientes para mayor claridad.

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5382   3.1213e+05
   1       0.9223   1.6051e+05
   2       0.8691   1.5050e+05
   3       0.8413   1.4576e+05
   4       0.8145   1.4208e+05
   5       0.7848   1.3895e+05
   6       0.7552   1.3613e+05
   7       0.7259   1.3357e+05
   8       0.6987   1.3121e+05
   9       0.6747   1.2949e+05
  10       0.6533   1.2766e+05
  11       0.6353   1.2636e+05
  12       0.6209   1.2561e+05
  13       0.6072   1.2462e+05
  14       0.5965   1.2394e+05
  15       0.5868   1.2352e+05
  16       0.5782   1.2279e+05
  17       0.5713   1.2227e+05
  18       0.5637   1.2190e+05
  19       0.5604   1.2178e+05
=============== Evaluating the model ===============
Rms: 0.977175077487166
RSquared: 0.43233349213192
=============== Making a prediction ===============
Movie 10 is recommended for user 6
=============== Saving the model to a file ===============
```

¡Enhorabuena! Ha compilado correctamente un modelo de Machine Learning para la recomendación de películas. Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/main/machine-learning/tutorials/MovieRecommendation).

## <a name="improve-your-model"></a>Mejora del código

Hay varias maneras de mejorar el rendimiento del modelo para obtener predicciones más precisas.

### <a name="data"></a>Datos

El hecho de agregar más datos de entrenamiento con suficientes ejemplos para cada usuario e identificador de película puede ayudar a mejorar la calidad del modelo de recomendación.

La [validación cruzada](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md) es una técnica para evaluar modelos que divide aleatoriamente los datos en subconjuntos (en lugar de extraer datos de prueba del conjunto de datos, como ha hecho en este tutorial) y toma algunos grupos como datos de entrenamiento y otros como datos de prueba. Este método supera en lo que respecta a la calidad del modelo la división en entrenamiento/prueba.

### <a name="features"></a>Características

En este tutorial, solo ha usado las tres `Features` (`user id`, `movie id` y `rating`) que proporciona el conjunto de datos.

Aunque es un buen comienzo, tal vez le interese agregar otros atributos o `Features` (por ejemplo, edad, sexo, ubicación geográfica, etc.) si se incluyen en el conjunto de datos. El hecho de agregar `Features` más pertinentes puede ayudar a mejorar el rendimiento del modelo de recomendación.

Si no está seguro de qué `Features` pueden ser más pertinentes para la tarea de aprendizaje automático, puede usar el Cálculo de la contribución de las características (FCC) y la [importancia de la característica de permutación](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md), que proporciona ML.NET para descubrir las `Features` más influyentes.

### <a name="algorithm-hyperparameters"></a>Hiperparámetros de algoritmo

Aunque ML.NET proporciona algoritmos de entrenamiento predeterminados de calidad, puede ajustar aún más el rendimiento si cambia los [hiperparámetros](../resources/glossary.md#hyperparameter) del algoritmo.

Para `Matrix Factorization`, puede experimentar con hiperparámetros como [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) y [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) para ver si así obtiene mejores resultados.

Por ejemplo, en este tutorial, las opciones de algoritmo son las siguientes:

```csharp
var options = new MatrixFactorizationTrainer.Options
{
    MatrixColumnIndexColumnName = "userIdEncoded",
    MatrixRowIndexColumnName = "movieIdEncoded",
    LabelColumnName = "Label",
    NumberOfIterations = 20,
    ApproximationRank = 100
};
```

### <a name="other-recommendation-algorithms"></a>Otros algoritmos de recomendación

El algoritmo de factorización matricial con filtrado de colaboración es solo un enfoque para realizar recomendaciones de películas. En muchos casos, es posible que no tenga a su disposición los datos de las clasificaciones y que solo cuente con el historial de películas de los usuarios. En otros casos, podría disponer de más datos que la clasificación del usuario.

| Algoritmo       | Escenario           | Ejemplo  |
| ------------- |:-------------:| -----:|
| Factorización matricial de una clase | Úselo cuando solo tenga los valores userId y movieId. Este tipo de recomendación se basa en el escenario de compra conjunta, es decir, en los productos que se suelen comprar juntos. Esto significa que se recomendará a los clientes un conjunto de productos en función de su propio historial de pedidos de compra. | [>Pruébelo](https://github.com/dotnet/machinelearning-samples/tree/main/samples/csharp/getting-started/MatrixFactorization_ProductRecommendation) |
| Máquinas de factorización con reconocimiento de campo | Úselo para realizar recomendaciones cuando disponga de más características que userId, productId y la clasificación (por ejemplo, la descripción o el precio del producto). Este método también usa un enfoque de filtrado de colaboración. | [>Pruébelo](https://github.com/dotnet/machinelearning-samples/tree/main/samples/csharp/end-to-end-apps/Recommendation-MovieRecommender) |

### <a name="new-user-scenario"></a>Escenario de nuevo usuario

Un problema común en el filtrado de colaboración es el "arranque en frío", que es cuando tiene un nuevo usuario sin ningún dato anterior a partir del cual pueda realizar inferencias. Por lo general, para solucionarlo se les pide a los nuevos usuarios que creen un perfil y, por ejemplo, clasifiquen películas que ya han visto. Aunque este método supone una relativa carga para el usuario, proporciona algunos datos iniciales para los usuarios nuevos que carecen de historial de clasificaciones.

## <a name="resources"></a>Recursos

Los datos que se han usado en este tutorial se han tomado del [conjunto de datos MovieLens](http://files.grouplens.org/datasets/movielens/).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:

> [!div class="checklist"]
>
> * Seleccionar un algoritmo de Machine Learning
> * Preparar y cargar los datos
> * Compilar y entrenar un modelo
> * Evaluar un modelo
> * Implementar y consumir un modelo

Siga con el siguiente tutorial para obtener más información
> [!div class="nextstepaction"]
> [Análisis de sentimiento](sentiment-analysis.md)

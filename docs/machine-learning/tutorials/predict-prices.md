---
title: 'Tutorial: Predicción de precios mediante regresión'
description: En este tutorial se muestra cómo compilar un modelo de regresión con ML.NET para predecir precios, en concreto, las tarifas de taxi de Nueva York.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: 91429383341cf718d38e636bd1d71dc25d30d20d
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607976"
---
# <a name="tutorial-predict-prices-using-regression-with-mlnet"></a>Tutorial: Predicción de precios mediante regresión con ML.NET

En este tutorial se muestra cómo compilar un [modelo de regresión](../resources/glossary.md#regression) con ML.NET para predecir precios, en concreto, las tarifas de taxi de Nueva York.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> * Preparar y entender los datos
> * Cargar y transformar los datos
> * Elegir un algoritmo de aprendizaje
> * Entrenar el modelo
> * Evaluar el modelo
> * Usar el modelo para las predicciones

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o posterior, o bien Visual Studio 2017 versión 15.6 o posterior con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Cree una **aplicación de consola de .NET Core** denominada "TaxiFarePrediction".

1. Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos y los archivos de modelo.

1. Instale el paquete NuGet **Microsoft.ML**:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione el paquete en la lista y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados. Haga lo mismo con el paquete NuGet **Microsoft.ML.FastTree**.

## <a name="prepare-and-understand-the-data"></a>Preparar y entender los datos

1. Descargue los conjuntos de datos [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) y [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) y guárdelos en la carpeta *Datos* que ha creado en el paso anterior. Usaremos estos conjuntos de datos para entrenar el modelo de aprendizaje automático y, después, evaluar su precisión. Estos conjuntos de datos proceden originalmente del [conjunto de datos NYC TLC Taxi Trip](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page).

1. En el **Explorador de soluciones**, haga clic con el botón derecho en cada uno de los archivos \*.csv y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

1. Abra el conjunto de datos **taxi-fare-train.csv** y consulte los encabezados de columna de la primera fila. Eche un vistazo a cada una de las columnas. Estudie los datos y decida qué columnas son **características** y cuál es la **etiqueta**.

`label` es la columna que quiere predecir. Las `Features` identificadas son las entradas que proporciona al modelo para predecir la `Label`.

El conjunto de datos proporcionado contiene las columnas siguientes:

* **vendor_id:** el identificador del taxista es una característica.
* **rate_code:** el tipo de tarifa del viaje en taxi es una característica.
* **passenger_count:** el número de pasajeros en el recorrido es una característica.
* **trip_time_in_secs:** la cantidad de tiempo que tardó el viaje. Por ejemplo, si quiere calcular la tarifa del viaje antes de que termine y aún no conoce la duración del viaje, el tiempo del viaje no es una característica, por lo que deberá excluir esta columna del modelo.
* **trip_distance:** la distancia del viaje es una característica.
* **payment_type:** el método de pago (efectivo o tarjeta de crédito) es una característica.
* **fare_amount:** la tarifa de taxi total pagada es la etiqueta.

## <a name="create-data-classes"></a>Crear clases de datos

Cree clases para los datos de entrada y las predicciones:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TaxiTrip.cs*. A continuación, seleccione el botón **Agregar**.
1. Agregue las siguientes directivas `using` al nuevo archivo:

   [!code-csharp[AddUsings](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/TaxiTrip.cs#1 "Add necessary usings")]

Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `TaxiTrip` y `TaxiTripFarePrediction`, al archivo *TaxiTrip.cs*:

[!code-csharp[DefineTaxiTrip](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` es la clase de datos de entrada y tiene definiciones para cada una de las columnas del conjunto de datos. Use el atributo <xref:Microsoft.ML.Data.LoadColumnAttribute> para especificar los índices de las columnas de origen en el conjunto de datos.

La clase `TaxiTripFarePrediction` representa los resultados predichos. Tiene un único campo flotante, `FareAmount`, con un atributo `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> aplicado. En el caso de la tarea de regresión, la columna **Score** contiene valores de etiqueta predichos.

> [!NOTE]
> Use el tipo `float` para representar los valores de punto flotante en las clases de entrada y predicción de datos.

### <a name="define-data-and-model-paths"></a>Definir rutas de acceso de datos y modelos

Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

[!code-csharp[AddUsings](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#1 "Add necessary usings")]

Deberá crear tres campos que contengan las rutas de acceso a los archivos con los conjuntos de datos y el archivo para guardar el modelo:

* `_trainDataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.
* `_testDataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para evaluar el modelo.
* `_modelPath` contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.

Agregue el código siguiente justo encima del método `Main` para especificar esas rutas de acceso y la variable `_textLoader`:

[!code-csharp[InitializePaths](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#2 "Define variables to store the data file paths")]

Todas las operaciones de ML.NET se inician en la [clase MLContext](xref:Microsoft.ML.MLContext). La inicialización de `mlContext` crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Como concepto, se parece a `DBContext` en Entity Framework.

### <a name="initialize-variables-in-main"></a>Inicializar variables en Main

Reemplace la línea `Console.WriteLine("Hello World!")` del método `Main` por el siguiente código para declarar e inicializar la variable `mlContext`:

[!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#3 "Create the ML Context")]

Agregue lo siguiente como la siguiente línea de código en el método `Main` para llamar al método `Train`:

[!code-csharp[Train](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#5 "Train your model")]

El método `Train()` ejecuta las tareas siguientes:

* Carga los datos.
* Extrae y transforma los datos.
* Entrena el modelo.
* Devuelve el modelo.

El método `Train` entrena el modelo. Cree ese método justo debajo de `Main` utilizando el código siguiente:

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

## <a name="load-and-transform-data"></a>Cargar y transformar datos

ML.NET usa la [clase IDataView](xref:Microsoft.ML.IDataView) como una forma flexible y eficaz de describir datos tabulares de texto o numéricos. `IDataView` puede cargar archivos de texto o en tiempo real (por ejemplo, una base de datos SQL o archivos de registro). Agregue el código siguiente a la primera línea del método `Train()`:

[!code-csharp[LoadTrainData](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#6 "loading training dataset")]

Como quiere predecir la tarifa de carreras de taxi, la columna `FareAmount` es la `Label` que va a predecir (la salida del modelo). Para ello, use la clase de transformación `CopyColumnsEstimator` para copiar `FareAmount` y agregue el código siguiente:

[!code-csharp[CopyColumnsEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#7 "Use the CopyColumnsEstimator")]

El algoritmo que entrena el modelo requiere características **numéricas**, por lo que debe transformar los datos de categorías (`VendorId`, `RateCode` y `PaymentType`) en números (`VendorIdEncoded`, `RateCodeEncoded` y `PaymentTypeEncoded`). Para ello, use la clase de transformación [OneHotEncodingTransformer](xref:Microsoft.ML.Transforms.OneHotEncodingTransformer), que asigna diferentes valores de clave numéricos a los distintos valores de cada una de las columnas y agregue el código siguiente:

[!code-csharp[OneHotEncodingEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#8 "Use the OneHotEncodingEstimator")]

En el último paso para la preparación de los datos, se combinan todas las columnas de característica en la columna **Características** mediante la clase de transformación `mlContext.Transforms.Concatenate`. De forma predeterminada, un algoritmo de aprendizaje solo procesa las características de la columna **Features**. Agregue el código siguiente:

[!code-csharp[ColumnConcatenatingEstimator](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a>Elegir un algoritmo de aprendizaje

Este problema consiste en predecir la tarifa de una carrera de taxi en la ciudad de Nueva York. A primera vista, puede parecer que simplemente depende de la distancia recorrida. Sin embargo, los taxistas de Nueva York cobran distintas cantidades por otros factores, como llevar pasajeros adicionales o pagar con tarjeta de crédito en lugar de efectivo. Quiere predecir el valor de precio, que es un valor real, en función de los demás factores del conjunto de datos. Para ello, se elige una tarea de aprendizaje automático de [regresión](../resources/glossary.md#regression).

Anexe la tarea de aprendizaje automático [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer) a las definiciones de transformación de datos al agregar esto como siguiente línea de código de `Train()`:

[!code-csharp[FastTreeRegressionTrainer](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a>Entrenar el modelo

Ajuste el modelo a la `dataview` de entrenamiento y devuelva el modelo entrenado agregando la siguiente línea de código en el método `Train()`:

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#11 "Train the model")]

El método [Fit()](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) entrena el modelo al transformar el conjunto de datos y aplicar el aprendizaje.

Devuelva el modelo entrenado con la siguiente línea de código en el método `Train()`:

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#12 "Return the model")]

## <a name="evaluate-the-model"></a>Evaluar el modelo

Luego evalúe el rendimiento del modelo con los datos de prueba de control de calidad y validación. Cree el método `Evaluate()`, justo después de `Train()`, con el código siguiente:

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

El método `Evaluate` ejecuta las tareas siguientes:

* Carga el conjunto de datos de prueba.
* Crea el evaluador de regresión.
* Evalúa el modelo y crea las métricas.
* Muestra las métricas.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Train`, utilizando el código siguiente:

[!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#14 "Call the Evaluate method")]

Cargue el conjunto de datos de prueba con el método [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A). Evalúe el modelo con este conjunto de datos como control de calidad al agregar el código siguiente en el método `Evaluate`:

[!code-csharp[LoadTestDataset](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#15 "Load the test dataset")]

Luego transforme los datos de `Test` al agregar el código siguiente a `Evaluate()`:

[!code-csharp[PredictWithTransformer](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#16 "Predict using the Transformer")]

El método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) realiza predicciones para las filas de entrada del conjunto de datos de prueba.

El método `RegressionContext.Evaluate` calcula las métricas de calidad para `PredictionModel` mediante el conjunto de datos especificado. Devuelve un objeto <xref:Microsoft.ML.Data.RegressionMetrics> que contiene las métricas totales calculadas por evaluadores de regresión.

Para mostrar estos elementos a fin de determinar la calidad del modelo, debe obtener primero las métricas. Agregue el siguiente código como la siguiente línea en el método `Evaluate`:

[!code-csharp[ComputeMetrics](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#17 "Compute Metrics")]

Una vez que se ha establecido la predicción, el método [Evaluate()](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) valora el modelo, que compara los valores predichos con las `Labels` reales del conjunto de datos de prueba y devuelve métricas sobre el rendimiento del modelo.

Agregue el código siguiente para evaluar el modelo y generar las métricas de evaluación:

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

[RSquared](../resources/glossary.md#coefficient-of-determination) es otra métrica de evaluación de modelos de regresión. RSquared muestra valores comprendidos entre 0 y 1. Cuanto más se acerque el valor a 1, mejor será el modelo. Agregue el código siguiente al método `Evaluate` para mostrar el valor de RSquared:

[!code-csharp[DisplayRSquared](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#18 "Display the RSquared metric.")]

[RMS](../resources/glossary.md#root-of-mean-squared-error-rmse) es una de las métricas de evaluación del modelo de regresión. Cuanto menor sea su valor, mejor será el modelo. Agregue el código siguiente al método `Evaluate` para mostrar el valor de RMS:

[!code-csharp[DisplayRMS](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a>Usar el modelo para las predicciones

Cree el método `TestSinglePrediction`, justo después del método `Evaluate`, mediante el código siguiente:

```csharp
private static void TestSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

El método `TestSinglePrediction` ejecuta las tareas siguientes:

* Crea un único comentario de datos de prueba.
* Predice la tarifa según los datos de prueba.
* Combina datos de prueba y predicciones para la generación de informes.
* Muestra los resultados de la predicción.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:

[!code-csharp[CallTestSinglePrediction](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#20 "Call the TestSinglePrediction method")]

Use `PredictionEngine` para predecir la tarifa al agregar el código siguiente a `TestSinglePrediction()`:

[!code-csharp[MakePredictionEngine](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#22 "Create the PredictionFunction")]

[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) es una API de conveniencia, que le permite realizar una predicción en una única instancia de datos. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) no es seguro para subprocesos. Es aceptable usarlo en entornos de un solo subproceso o prototipo. Para mejorar el rendimiento y la seguridad para subprocesos en entornos de producción, use el servicio `PredictionEnginePool`, que crea un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) de objetos de [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) para su uso en toda la aplicación. Consulte esta guía sobre cómo [usar `PredictionEnginePool` en una API web de ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

> [!NOTE]
> La extensión del servicio `PredictionEnginePool` está actualmente en versión preliminar.

En este tutorial se utiliza un viaje de prueba en esta clase. Más adelante, puede agregar otros escenarios para experimentar con el modelo. Agregue un viaje para probar la predicción de costo del modelo entrenado en el método `TestSinglePrediction()` mediante la creación de una instancia de `TaxiTrip`:

[!code-csharp[PredictionData](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#23 "Create test data for single prediction")]

Luego, prediga el importe del servicio según una instancia única de los datos de carreras de taxi y páselo a la clase `PredictionEngine` agregando lo siguiente como próximas líneas de código en el método `TestSinglePrediction()`:

[!code-csharp[Predict](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#24 "Create a prediction of taxi fare")]

La función [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) realiza una predicción sobre una única instancia de datos.

Para mostrar la tarifa prevista del viaje especificado, agregue el código siguiente al método `TestSinglePrediction`:

[!code-csharp[Predict](~/samples/snippets/machine-learning/TaxiFarePrediction/csharp/Program.cs#25 "Display the prediction.")]

Ejecute el programa para ver la tarifa de taxi predicha para su caso de prueba.

¡Enhorabuena! Ya ha creado correctamente un modelo de aprendizaje automático para predecir tarifas de viajes en taxi, ha evaluado su precisión y lo ha usado para hacer predicciones. Puede encontrar el código fuente de este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) de GitHub.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:

> [!div class="checklist"]
>
> * Preparar y entender los datos
> * Crear una canalización de aprendizaje
> * Cargar y transformar los datos
> * Elegir un algoritmo de aprendizaje
> * Entrenar el modelo
> * Evaluar el modelo
> * Usar el modelo para las predicciones

Siga con el siguiente tutorial para obtener más información.

> [!div class="nextstepaction"]
> [Agrupación en clústeres de iris](iris-clustering.md)

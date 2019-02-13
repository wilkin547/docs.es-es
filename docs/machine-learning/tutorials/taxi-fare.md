---
title: Predicción de precios mediante un aprendiz de regresión con ML.NET
description: Prediga precios mediante un aprendiz de regresión con ML.NET.
author: aditidugar
ms.author: johalex
ms.date: 01/15/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: e838d5b3b42ffec6648c67b4669a438dbd9e2c34
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828402"
---
# <a name="tutorial-predict-prices-using-a-regression-learner-with-mlnet"></a>Tutorial: Predicción de precios mediante un aprendiz de regresión con ML.NET

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, vea [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

En este tutorial se muestra cómo usar ML.NET para generar un [modelo de regresión](../resources/glossary.md#regression) para predecir precios, en concreto las tarifas de taxi de Nueva York.

En este tutorial aprenderá a:
> [!div class="checklist"]
> * Entender el problema
> * Seleccionar la tarea de aprendizaje automático adecuada
> * Preparar y entender los datos
> * Crear una canalización de aprendizaje
> * Cargar y transformar los datos
> * Elegir un algoritmo de aprendizaje
> * Entrenar el modelo
> * Evaluar el modelo
> * Usar el modelo para las predicciones

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

## <a name="understand-the-problem"></a>Entender el problema

Este problema trata sobre la predicción de la tarifa de una carrera de taxi en Nueva York. A primera vista, puede parecer que simplemente depende de la distancia recorrida. Sin embargo, los taxistas de Nueva York cobran distintas cantidades por otros factores, como llevar pasajeros adicionales o pagar con tarjeta de crédito en lugar de efectivo.

## <a name="select-the-appropriate-machine-learning-task"></a>Seleccionar la tarea de aprendizaje automático adecuada

Se quiere predecir el precio, que es un valor real, en función de los demás factores del conjunto de datos. Para ello, elija una tarea de aprendizaje automático de [regresión](../resources/glossary.md#regression).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "TaxiFarePrediction" y después haga clic en el botón **Aceptar**.

1. Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos y los archivos del modelo:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Datos" y presione Entrar.

1. Instale el paquete NuGet **Microsoft.ML**:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

## <a name="prepare-and-understand-the-data"></a>Preparar y entender los datos

1. Descargue los conjuntos de datos [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) y [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) y guárdelos en la carpeta *Datos* que ha creado en el paso anterior. Usaremos estos conjuntos de datos para entrenar el modelo de aprendizaje automático y, después, evaluar su precisión. Estos conjuntos de datos proceden originalmente del [conjunto de datos NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).

1. En el **Explorador de soluciones**, haga clic con el botón derecho en cada uno de los archivos \*.csv y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

1. Abra el conjunto de datos **taxi-fare-train.csv** y consulte los encabezados de columna de la primera fila. Eche un vistazo a cada una de las columnas. Estudie los datos y decida qué columnas son **características** y cuál es la **etiqueta**.

La **etiqueta** es el identificador de la columna que quiere predecir. Las **características** identificadas se usan para predecir la etiqueta.

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

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `TaxiTrip` y `TaxiTripFarePrediction`, al archivo *TaxiTrip.cs*:

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` es la clase de datos de entrada y tiene definiciones para cada una de las columnas del conjunto de datos. Use el atributo <xref:Microsoft.ML.Data.ColumnAttribute> para especificar los índices de las columnas de origen en el conjunto de datos.

La clase `TaxiTripFarePrediction` representa los resultados predichos. Tiene un único campo flotante, `FareAmount`, con un atributo `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> aplicado. En el caso de la tarea de regresión, la columna **Score** contiene valores de etiqueta predichos.

> [!NOTE]
> Use el tipo `float` para representar los valores de punto flotante en las clases de entrada y predicción de datos.

## <a name="define-data-and-model-paths"></a>Definir rutas de acceso de datos y modelos

Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

Deberá crear tres campos que contengan las rutas de acceso a los archivos con los conjuntos de datos y el archivo para guardar el modelo, además de una variable global para `TextLoader`:

* `_trainDataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.
* `_testDataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para evaluar el modelo.
* `_modelPath` contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.
* `_textLoader` es el <xref:Microsoft.ML.Data.TextLoader> utilizado para cargar y transformar los conjuntos de datos.

Agregue el código siguiente justo encima del método `Main` para especificar esas rutas de acceso y la variable `_textLoader`:

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

Cuando se crea un modelo con ML.NET se empieza creando un contexto de ML. Esto es comparable conceptualmente a usar `DbContext` en Entity Framework. El entorno proporciona un contexto para el trabajo de aprendizaje automático que puede usarse para el seguimiento y registro de excepciones.

### <a name="initialize-variables-in-main"></a>Inicializar variables en Main

Cree una variable denominada `mlContext` e inicialícela con una nueva instancia de `MLContext`.  Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

A continuación, para realizar la configuración para la carga de datos, inicialice la variable global `_textLoader` con el fin de volver a usarla.  Tenga en cuenta que se está usando `TextReader`. Cuando crea `TextLoader` mediante `TextReader`, se pasa en el contexto necesario y la clase <xref:Microsoft.ML.Data.TextLoader.Arguments> que habilita la personalización. Especifique el esquema de datos, pasando una matriz de objetos <xref:Microsoft.ML.Data.TextLoader.Column> a `TextReader` que contiene todos los nombres de columna y sus tipos. Definimos el esquema de datos anteriormente al crear nuestra clase `TaxiTrip`.

La clase `TextReader` devuelve la variable <xref:Microsoft.ML.Data.TextLoader> totalmente inicializada.  

Para inicializar la variable global `_textLoader` con el fin de volver a usarla para los conjuntos de datos necesarios, agregue el código siguiente después de la inicialización de `mlContext`:

[!code-csharp[initTextLoader](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Initialize the TextLoader")]

Agregue lo siguiente como la siguiente línea de código en el método `Main` para llamar al método `Train`:

[!code-csharp[Train](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

El método `Train` ejecuta las tareas siguientes:

* Carga los datos.
* Extrae y transforma los datos.
* Entrena el modelo.
* Guarda el modelo como un archivo ZIP.
* Devuelve el modelo.

El método `Train` entrena el modelo. Cree ese método justo debajo de `Main` utilizando el código siguiente:

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

Pasamos dos parámetros al método `Train`; `MLContext` para el contexto (`mlContext`) y una cadena para la ruta de acceso al conjunto de datos (`dataPath`). Vamos a volver a usar este método para cargar los conjuntos de datos.

## <a name="load-and-transform-data"></a>Cargar y transformar datos

Cargaremos los datos mediante la variable global `_textLoader` con el parámetro `dataPath`. Devuelve <xref:Microsoft.ML.Data.IDataView>. Como la entrada y salida de Transforms,`DataView` es el tipo de canalización de datos fundamentales, comparable con `IEnumerable` para `LINQ`.

En ML.NET, los datos son similares a una vista SQL. Se evalúan lentamente, se esquematizan y son heterogéneos. El objeto es la primera parte de la canalización y carga los datos. Para este tutorial, carga un conjunto de datos con información sobre los viajes en taxi que resulta útil para predecir las tarifas. Esto se usa para crear el modelo y entrenarlo.

 Agregue el código siguiente a la primera línea del método `Train`:

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

En los pasos siguientes se hace referencia a las columnas con los nombres definidos en la clase `TaxiTrip`.

Si el modelo se ha entrenado y evaluado, de forma predeterminada, los valores de la columna **Label** se consideran valores correctos para predecir. Para predecir la tarifa del viaje en taxi, debe copiar la columna `FareAmount` en la columna **Etiqueta**. Para ello, use la clase de transformación `CopyColumnsEstimator` y agregue el código siguiente:

[!code-csharp[CopyColumnsEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

El algoritmo que entrena el modelo requiere características **numéricas**, por lo que debe transformar los datos de categorías (`VendorId`, `RateCode` y `PaymentType`) en números. Para ello, use la clase de transformación `OneHotEncodingEstimator`, que asigna valores clave numéricos diferentes a los distintos valores de cada una de las columnas, y agregue el código siguiente:

[!code-csharp[OneHotEncodingEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

En el último paso para la preparación de los datos, se combinan todas las columnas de característica en la columna **Características** mediante la clase de transformación `ColumnConcatenatingEstimator`. De forma predeterminada, un algoritmo de aprendizaje solo procesa las características de la columna **Features**. Agregue el código siguiente:

[!code-csharp[ColumnConcatenatingEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a>Elegir un algoritmo de aprendizaje

Después de agregar los datos a la canalización y transformarlos en el formato de entrada correcto, se selecciona un algoritmo de aprendizaje (**aprendiz**). El aprendiz entrena el modelo. Elegimos una tarea de **regresión** para este problema, por lo que usamos un aprendiz de `FastTreeRegressionTrainer`, que es uno de los aprendices de regresión que proporciona ML.NET.

El aprendiz `FastTreeRegressionTrainer` usa la potenciación del gradiente. La potenciación de gradiente es una técnica para los problemas de regresión de aprendizaje automático. Crea cada árbol de regresión de forma escalonada. Utiliza una función de pérdida predefinida para medir el error en cada paso y corregirlo en el siguiente. El resultado es un modelo de predicción que es realmente un conjunto de modelos de predicción más débiles. Para obtener más información sobre la potenciación de gradiente, consulte [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regresión de árbol de decisión potenciado).

Agregue el código siguiente al método `Train` para agregar `FastTreeRegressionTrainer` al código de procesamiento de datos que se agregó en el paso anterior:

[!code-csharp[FastTreeRegressionTrainer](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a>Entrenar el modelo

El último paso es entrenar el modelo. Se entrena el modelo, <xref:Microsoft.ML.Data.TransformerChain>, en función del conjunto de datos que se haya cargado y transformado. Una vez que se ha definido el estimador, se entrena el modelo mediante <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> y, al mismo tiempo, se proporcionan los datos de entrenamiento ya cargados. Esto devuelve un modelo que se usa para las predicciones. `pipeline.Fit()` entrena la canalización y devuelve `Transformer` según la `DataView` que se pasa. El experimento no se ejecuta hasta que esto suceda.

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

Y listo. Ha entrenado correctamente un modelo de aprendizaje automático que puede predecir tarifas de taxi en Nueva York. Ahora, eche un vistazo para medir la precisión del modelo y aprender a usarlo para predecir los valores de tarifas de viajes en taxi.

### <a name="save-the-model"></a>Guardado del modelo

En este punto, tiene un modelo de tipo <xref:Microsoft.ML.Data.TransformerChain> que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes. Para guardar el modelo en un archivo .zip, agregue el código siguiente al final del método `Train`:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Save the model as a .zip file and return the model")]

## <a name="save-the-model-as-a-zip-file"></a>Almacenamiento del modelo como un archivo ZIP

Cree el método `SaveModelAsFile`, justo después del método `Train`, mediante el código siguiente:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

El método `SaveModelAsFile` ejecuta las tareas siguientes:

* Guarda el modelo como un archivo ZIP.

Es necesario crear un método para guardar el modelo para que se pueda volver a usar y consumir en otras aplicaciones. `ITransformer` tiene un método <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> que toma el campo global `_modelPath` y <xref:System.IO.Stream>. Como queremos guardar esto como archivo ZIP, vamos a crear `FileStream` inmediatamente antes de llamar al método `SaveTo`. Agregue el siguiente código al método `SaveModelAsFile` como la siguiente línea:

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Add the SaveTo Method")]

También podríamos mostrar dónde se escribió el archivo mediante la escritura de un mensaje de consola con `_modelPath`, utilizando el código siguiente:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a>Evaluar el modelo

La evaluación es el proceso que sirve para comprobar cómo predice valores de etiqueta el modelo. Es importante que el modelo haga buenas predicciones sobre los datos que no se han usado para entrenarlo. Una forma de hacerlo es dividir los datos en conjuntos de datos de entrenamiento y prueba, como se ha hecho en este tutorial. Ahora que ha entrenado el modelo en los datos de aprendizaje, puede ver qué tal funciona en los datos de prueba.

El método `Evaluate` evaluará el modelo. Para crear este método, agregue el código siguiente debajo del método `Train`:

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

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

Cargaremos el conjunto de datos de prueba mediante la variable global `_textLoader` inicializada anteriormente con el campo global `_testDataPath`. Puede evaluar el modelo utilizando este conjunto de datos como una comprobación de calidad. Agregue el código siguiente al método `Evaluate`:

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

A continuación, se usará el parámetro `model` de aprendizaje automático (un transformador) para introducir las características y devolver las predicciones. Agregue el siguiente código al método `Evaluate` como la siguiente línea:

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

El método `RegressionContext.Evaluate` calcula las métricas de calidad para `PredictionModel` mediante el conjunto de datos especificado. Devuelve un objeto <xref:Microsoft.ML.Data.RegressionMetrics> que contiene las métricas totales calculadas por evaluadores de regresión. Para mostrar estos elementos a fin de determinar la calidad del modelo, debe obtener primero las métricas. Agregue el siguiente código como la siguiente línea en el método `Evaluate`:

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

Agregue el código siguiente para evaluar el modelo y generar las métricas de evaluación:

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

[RSquared](../resources/glossary.md#coefficient-of-determination) es otra métrica de evaluación de modelos de regresión. RSquared muestra valores comprendidos entre 0 y 1. Cuanto más se acerque el valor a 1, mejor será el modelo. Agregue el código siguiente al método `Evaluate` para mostrar el valor de RSquared:

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) es una de las métricas de evaluación del modelo de regresión. Cuanto menor sea su valor, mejor será el modelo. Agregue el código siguiente al método `Evaluate` para mostrar el valor de RMS:

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a>Usar el modelo para las predicciones


## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a>Predicción del resultado de los datos de prueba con el modelo y un único comentario

Cree el método `TestSinglePrediction`, justo después del método `Evaluate`, mediante el código siguiente:

```csharp
private static void TestSinglePrediction(MLContext mlContext)
{

}
```

El método `TestSinglePrediction` ejecuta las tareas siguientes:

* Crea un único comentario de datos de prueba.
* Predice la tarifa según los datos de prueba.
* Combina datos de prueba y predicciones para la generación de informes.
* Muestra los resultados de la predicción.

Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:

[!code-csharp[CallTestSinglePrediction](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

Como queremos cargar el modelo desde el archivo ZIP que guardamos, crearemos `FileStream` inmediatamente antes de llamar al método `Load`. Agregue el código siguiente al método `TestSinglePrediction` como la siguiente línea:

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#21 "Load the model")]

Mientras `model` es `transformer` que opera en muchas filas de datos, un escenario muy común de producción es necesario para las predicciones con los ejemplos individuales. <xref:Microsoft.ML.PredictionEngine%602> es un contenedor que se devuelve del método `CreatePredictionEngine`. Vamos a agregar el código siguiente para crear `PredictionEngine` como la primera línea en el método `Predict`:

[!code-csharp[MakePredictionEngine](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]
  
En este tutorial se utiliza un viaje de prueba en esta clase. Más adelante, puede agregar otros escenarios para experimentar con el modelo. Agregue un viaje para probar la predicción de costo del modelo entrenado en el método `Predict` mediante la creación de una instancia de `TaxiTrip`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

 Podemos usarlo para predecir la tarifa en función de una instancia única de los datos del viaje en taxi. Para obtener una predicción, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> en los datos. Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización. La canalización está sincronizada durante el entrenamiento y la predicción. No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

Para mostrar la tarifa prevista del viaje especificado, agregue el código siguiente al método `Main`:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

Ejecute el programa para ver la tarifa de taxi predicha para su caso de prueba.

¡Enhorabuena! Ya ha creado correctamente un modelo de aprendizaje automático para predecir tarifas de viajes en taxi, ha evaluado su precisión y lo ha usado para hacer predicciones. Puede encontrar el código fuente de este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) de GitHub.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
> * Entender el problema
> * Seleccionar la tarea de aprendizaje automático adecuada
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

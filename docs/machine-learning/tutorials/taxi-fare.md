---
title: Uso de ML.NET para predecir las tarifas de taxi de Nueva York (regresión)
description: Obtenga información acerca de cómo usar ML.NET en un escenario de regresión.
author: aditidugar
ms.author: johalex
ms.date: 06/18/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9706dad0a8e32651496e0404be4501c2c70e9d75
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948636"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a>Tutorial: Uso de ML.NET para predecir las tarifas de taxi de Nueva York (regresión)

> [!NOTE]
> Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios. Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

En este tutorial se muestra cómo utilizar ML.NET para generar un [modelo de regresión](../resources/glossary.md#regression) para predecir las tarifas de taxi de Nueva York.

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

Este problema se centra en **predecir la tarifa de un viaje en taxi en Nueva York**. A primera vista, puede parecer que simplemente depende de la distancia recorrida. Sin embargo, los taxistas de Nueva York cobran distintas cantidades por otros factores, como llevar pasajeros adicionales o pagar con tarjeta de crédito en lugar de efectivo.

## <a name="select-the-appropriate-machine-learning-task"></a>Seleccionar la tarea de aprendizaje automático adecuada

Para predecir la tarifa del taxi, primero seleccione la tarea de aprendizaje automático adecuada. Está buscando predecir un valor real (un doble que representa el precio) en función de los otros factores del conjunto de datos. Elige una tarea de [**regresión**](../resources/glossary.md#regression).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "TaxiFarePrediction" y después haga clic en el botón **Aceptar**.

2. Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Datos" y presione Entrar.

3. Instale el **paquete NuGet Microsoft.ML**:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

## <a name="prepare-and-understand-the-data"></a>Preparar y entender los datos

1. Descargue los conjuntos de datos [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) y [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) y guárdelos en la carpeta *Datos* que ha creado en el paso anterior. Usaremos estos conjuntos de datos para entrenar el modelo de aprendizaje automático y, después, evaluar su precisión. Estos conjuntos de datos proceden originalmente del [conjunto de datos NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).

2. En el **Explorador de soluciones**, haga clic con el botón derecho en cada uno de los archivos \*.csv y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** a **Siempre**.

3. Abra el conjunto de datos **taxi-fare-train.csv** y consulte los encabezados de columna de la primera fila. Eche un vistazo a cada una de las columnas. Estudie los datos y decida qué columnas son **características** y cuál es la **etiqueta**.

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

`TaxiTrip` es la clase de datos de entrada y tiene definiciones para cada una de las columnas del conjunto de datos. Use el atributo [Columna](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) para especificar los índices de las columnas de origen en el conjunto de datos.

La clase `TaxiTripFarePrediction` se usa para representar los resultados previstos. Tiene un único campo flotante (`FareAmount`) con un atributo `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) aplicado. La columna **Puntuación** es la columna especial de ML.NET. El modelo generará valores de predicción en esa columna.

## <a name="define-data-and-model-paths"></a>Definir rutas de acceso de datos y modelos

Vuelva al archivo *Program.cs* y agregue tres campos para contener las rutas de acceso a los archivos con conjuntos de datos y el archivo en el que guardar el modelo:

* `_datapath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.
* `_testdatapath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para evaluar el modelo.
* `_modelpath` contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.

Agregue el código siguiente justo encima del método `Main` para especificar las rutas de acceso:

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

Para que el código anterior se compile, agregue las directivas `using` siguientes a la parte superior del archivo *Program.cs*:

[!code-csharp[AddUsingsForPaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Using statements for path definitions")]

## <a name="create-a-learning-pipeline"></a>Crear una canalización de aprendizaje

Agregue las directivas `using` adicionales siguientes a la parte superior del archivo *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

En `Main`, reemplace `Console.WriteLine("Hello World!")` por el código siguiente:

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

El método `Train` entrena el modelo. Cree ese método justo debajo de `Main` utilizando el código siguiente:

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

La canalización de aprendizaje carga todos los datos y algoritmos necesarios para entrenar el modelo. Agregue el código siguiente al método `Train`:

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-data"></a>Cargar y transformar datos

El primer paso que realiza la canalización de aprendizaje es cargar datos desde el conjunto de datos de entrenamiento. En nuestro caso, el conjunto de datos de entrenamiento se almacena en el archivo de texto con una ruta de acceso definida por el campo `_datapath`. Ese archivo contiene el encabezado con los nombres de columna, por lo que se debe omitir la primera fila al cargar los datos. En el archivo, las columnas se separan mediante una coma (","). Agregue el código siguiente al método `Train`:

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(useHeader: true, separator: ','));
```

En los pasos siguientes se hace referencia a las columnas con los nombres definidos en la clase `TaxiTrip`.

Cuando el modelo se entrena y evalúa, los valores de la columna **Etiqueta** se consideran valores correctos para predecir. Para predecir la tarifa del viaje en taxi, debe copiar la columna `FareAmount` en la columna **Etiqueta**. Para ello, use <xref:Microsoft.ML.Transforms.ColumnCopier> y agregue el código siguiente:

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

El algoritmo que entrena el modelo requiere características **numéricas**, por lo que debe transformar los datos de categorías (`VendorId`, `RateCode` y `PaymentType`) en números. Para ello, use <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer>, que asigna valores clave numéricos diferentes a los distintos valores de cada una de las columnas, y agregue el código siguiente:

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

En el último paso para la preparación de los datos, se combinan todas las columnas de característica en la columna **Características** mediante la clase de transformación <xref:Microsoft.ML.Transforms.ColumnConcatenator>. Este paso es necesario, ya que un aprendiz solo procesará las características de la columna **Características**. Agregue el código siguiente:

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

Tenga en cuenta que la columna `TripTime`, que corresponde a la columna `trip_time_in_secs` en el archivo con el conjunto de datos, no se incluye. Ya ha determinado que no es una característica útil de predicción.

> [!NOTE]
> Estos pasos deben agregarse a la canalización en el orden especificado anteriormente para su correcta ejecución.

## <a name="choose-a-learning-algorithm"></a>Elegir un algoritmo de aprendizaje

Después de agregar los datos a la canalización y transformarlos en el formato de entrada correcto, seleccione un algoritmo de aprendizaje (**aprendiz**). El aprendiz entrena el modelo. Como ha elegido una **tarea de regresión** para este problema, deberá agregar un aprendiz de <xref:Microsoft.ML.Trainers.FastTreeRegressor>, uno de los aprendices de regresión que proporciona ML.NET.

El aprendiz <xref:Microsoft.ML.Trainers.FastTreeRegressor> usa la potenciación de gradiente. La potenciación de gradiente es una técnica para los problemas de regresión de aprendizaje automático. Crea cada árbol de regresión de forma escalonada. Utiliza una función de pérdida predefinida para medir el error en cada paso y corregirlo en el siguiente. El resultado es un modelo de predicción que es realmente un conjunto de modelos de predicción más débiles. Para obtener más información sobre la potenciación de gradiente, consulte [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regresión de árbol de decisión potenciado).

Agregue el código siguiente al método `Train` después del código de procesamiento de datos que ha agregado en el paso anterior:

```csharp
pipeline.Add(new FastTreeRegressor());
```

Agregó todos los pasos anteriores a la canalización como instrucciones individuales, pero C# tiene una útil sintaxis de inicialización de recopilación que simplifica la creación e inicialización de la canalización. Reemplace el código que ha agregado hasta ahora al método `Train` por el siguiente código:

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a>Entrenar el modelo

El último paso es entrenar el modelo. Hasta este punto, no se ha ejecutado nada en la canalización. El método `pipeline.Train<TInput, TOutput>` genera el modelo que usa una instancia del tipo `TInput` para generar una instancia del tipo `TOutput`. Agregue el código siguiente al método `Train`:

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

Y listo. Ha entrenado correctamente un modelo de aprendizaje automático que puede predecir tarifas de taxi en Nueva York. Ahora, eche un vistazo para medir la precisión del modelo y aprender a usarlo para predecir los valores de tarifas de viajes en taxi.

### <a name="save-the-model"></a>Guardado del modelo

Antes de ir al paso siguiente, guarde el modelo en un archivo .zip agregando el código siguiente al final del método `Train`:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

La adición de la instrucción `await` a la llamada `model.WriteAsync` implica que el método `Train` debe cambiarse a un método asincrónico que devuelva una tarea. Modifique la firma del `Train` tal como se muestra en el código siguiente:

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

El cambio del tipo de valor devuelto del método `Train` implica que tiene que agregar `await` al código que llama a `Train` en el método `Main` tal como se muestra en el código siguiente:

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

El uso de `await` en el método `Main` implica que el método `Main` debe tener un modificador `async` y devolver un `Task`:

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

También tiene que agregar la siguiente directiva `using` a la parte superior del archivo:

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

Debido a que el método `async Main` es una característica agregada en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior. Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**. Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**. En la lista desplegable, seleccione **C# 7.1** (o una versión superior). Seleccione el botón **Aceptar**.

## <a name="evaluate-the-model"></a>Evaluar el modelo

La evaluación es el proceso que sirve para comprobar cómo predice valores de etiqueta el modelo. Es importante que el modelo haga buenas predicciones sobre los datos que no se han usado para entrenarlo. Una forma de hacerlo es dividiendo los datos en conjuntos de datos de entrenamiento y prueba, tal como ha hecho en este tutorial. Ahora que ha entrenado el modelo en los datos de entrenamiento, puede ver qué tal funciona en los datos de prueba.

Vuelva al método `Main` y agregue el código siguiente debajo de la llamada al método `Train`:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

El método `Evaluate` evaluará el modelo. Para crear este método, agregue el código siguiente debajo del método `Train`:

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

Agregue el código siguiente al método `Evaluate` para configurar la carga de los datos de prueba:

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

Agregue el código siguiente para evaluar el modelo y generar las métricas de evaluación:

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) es una de las métricas de evaluación del modelo de regresión. Cuanto menor sea su valor, mejor será el modelo. Agregue el código siguiente al método `Evaluate` para mostrar el valor de RMS:

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

[RSquared](../resources/glossary.md#coefficient-of-determination) es otra métrica de evaluación de modelos de regresión. RSquared muestra valores comprendidos entre 0 y 1. Cuanto más se acerque el valor a 1, mejor será el modelo. Agregue el código siguiente al método `Evaluate` para mostrar el valor de RSquared:

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a>Usar el modelo para las predicciones

A continuación, cree una clase para hospedar escenarios de prueba que pueda usar para asegurarse de que el modelo funcione correctamente:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TestTrips.cs*. A continuación, seleccione el botón **Agregar**.
1. Modifique la clase para que sea estática, como en el ejemplo siguiente:

   [!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

En este tutorial se utiliza un viaje de prueba en esta clase. Más adelante, puede agregar otros escenarios para experimentar con el modelo. Agregue el código siguiente a la clase `TestTrips`:

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

La tarifa real del viaje es de 29,5. Puesto que el modelo predecirá la tarifa, use 0 como marcador de posición.

Para predecir la tarifa del viaje especificado, vuelva al archivo *Program.cs* y agregue el código siguiente al método `Main`:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

Ejecute el programa para ver la tarifa de taxi predicha para su caso de prueba.

¡Enhorabuena! Ya ha creado correctamente un modelo de aprendizaje automático para predecir tarifas de viajes en taxi, ha evaluado su precisión y lo ha usado para hacer predicciones. Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).

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

Visite nuestro repositorio de GitHub para obtener más información y encontrar más ejemplos.
> [!div class="nextstepaction"]
> [Repositorio de GitHub de dotnet/machinelearning](https://github.com/dotnet/machinelearning/)

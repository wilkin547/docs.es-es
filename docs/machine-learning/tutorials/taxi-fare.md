---
title: Uso de ML.NET para predecir las tarifas de taxi de Nueva York (regresión)
description: Obtenga información acerca de cómo usar ML.NET en un escenario de regresión.
author: aditidugar
ms.author: johalex
ms.date: 06/05/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 048ed1d38408c1ba4901c554cae33d5552c9e303
ms.sourcegitcommit: 5b0802832fb9ad684d34e69b8644a16a5b7c4810
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2018
ms.locfileid: "34860708"
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

* [Visual Studio 2017 15.6 o posterior](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

## <a name="understand-the-problem"></a>Entender el problema

Este problema se centra en **predecir la tarifa de un viaje en taxi en Nueva York**. A primera vista, puede parecer que simplemente depende de la distancia recorrida. Sin embargo, los taxistas de Nueva York cobran distintas cantidades por otros factores, como llevar pasajeros adicionales o pagar con tarjeta de crédito en lugar de efectivo.

## <a name="select-the-appropriate-machine-learning-task"></a>Seleccionar la tarea de aprendizaje automático adecuada

Para predecir la tarifa del taxi, primero seleccione la tarea de aprendizaje automático adecuada. Está buscando predecir un valor real (un doble que representa el precio) en función de los otros factores del conjunto de datos. Elige una tarea de [**regresión**](../resources/glossary.md#regression).

El proceso de entrenamiento del modelo identifica qué factores del conjunto de datos son más influyentes al predecir el precio de la tarifa final.

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Abra Visual Studio 2017. Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús. En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**. Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "TaxiFarePrediction" y después haga clic en el botón **Aceptar**.

2. Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos:

    En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**. Escriba "Datos" y presione Entrar.

3. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML**, seleccione ese paquete en la lista y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.

### <a name="prepare-and-understand-your-data"></a>Preparar y entender los datos

1. Descargue los conjuntos de datos [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) y [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) y guárdelos en la carpeta *Datos* creada anteriormente. El conjunto de datos de tarifas de taxi entrena el modelo de aprendizaje automático y puede usarse para evaluar su grado de precisión. Estos conjuntos de datos proceden originalmente del [conjunto de datos NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).

2. En el Explorador de soluciones, haga clic con el botón secundario en cada uno de los archivos \*.csv y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** a **Siempre**.

3. Abra el conjunto de datos **taxi-fare-train.csv** en el editor de código y fíjese en los encabezados de columna de la primera fila. Eche un vistazo a cada una de las columnas. Comprenda los datos y decida qué columnas son **características** y cuál es la **etiqueta**.

La **etiqueta** es el identificador de la columna que está intentando predecir. Las **características** identificadas se usan para predecir la etiqueta.

* **vendor_id:** el identificador del taxista es una característica.
* **rate_code:** el tipo de tarifa del viaje en taxi es una característica.
* **passenger_count:** el número de pasajeros en el recorrido es una característica.
* **trip_time_in_secs:** la cantidad de tiempo que tardó el viaje. No sabrá cuánto tiempo tarda el recorrido hasta que se haya completado. Excluya esta columna del modelo.
* **trip_distance:** la distancia del viaje es una característica.
* **payment_type:** el método de pago (efectivo o tarjeta de crédito) es una característica.
* **fare_amount:** la tarifa de taxi total pagada es la etiqueta.

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

Debe crear tres variables globales para contener la ruta de acceso a los archivos descargados recientemente y para guardar el modelo:

* `_datapath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.
* `_testdatapath` tiene la ruta de acceso al conjunto de datos utilizado para evaluar el modelo.
* `_modelpath` tiene la ruta de acceso donde se almacena el modelo entrenado.

Agregue el código siguiente a la línea por encima de `Main` para especificar los archivos descargados recientemente:

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

A continuación, cree las clases para los datos de entrada y las predicciones:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TaxiTrip.cs*. A continuación, seleccione el botón **Agregar**.
1. Agregue las siguientes instrucciones `using` al archivo nuevo:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `TaxiTrip` y `TaxiTripFarePrediction`, al archivo *TaxiTrip.cs*:

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` es la clase de conjunto de datos de entrada y tiene definiciones para cada una de las columnas del conjunto de datos. La clase `TaxiTripFarePrediction` se usa para la predicción una vez entrenado el modelo. Tiene un único float (`FareAmount`) y un atributo `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) aplicado.

Ahora, vuelva al archivo **Program.cs**. En `Main`, reemplace `Console.WriteLine("Hello World!")` por el código siguiente:

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

El método `Train` entrena el modelo. Cree esa función justo debajo de `Main`, utilizando el código siguiente:

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

## <a name="create-a-learning-pipeline"></a>Crear una canalización de aprendizaje

La canalización de aprendizaje carga todos los datos y algoritmos necesarios para entrenar el modelo. Agregue el código siguiente al método `Train()`:

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-your-data"></a>Cargar y transformar los datos

A continuación, cargue los datos en la canalización. Apunte al `_datapath` creado inicialmente y especifique el delimitador del archivo .csv (,). Agregue el código siguiente al método `Train()` debajo del último paso:

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(separator:','));
```

Se hará referencia a las columnas sin el carácter de subrayado en el código que se va a crear. Copie la columna `FareAmount` en una nueva columna denominada "Etiqueta" mediante la función `ColumnCopier()`. Esta columna es la **Etiqueta**.

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

Lleve a cabo cierta **ingeniería de características** para transformar los datos a fin de que se puedan utilizar eficazmente para el aprendizaje automático. El algoritmo que entrena el modelo requiere características **numéricas**, transforme los datos de categorías (`VendorId`, `RateCode` y `PaymentType`) en números. La función `CategoricalOneHotVectorizer()` asigna una clave numérica a los valores de cada una de estas columnas. Transforme los datos mediante la adición de este código:

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

El último paso de preparación de datos combina todas las **características** en un vector usando la función `ColumnConcatenator()`. Este paso necesario ayuda al algoritmo a procesar fácilmente sus características. Agregue el código siguiente:

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

Tenga en cuenta que la columna `trip_time_in_secs` no está incluida. Ya ha determinado que no es una característica útil de predicción.

> [!NOTE]
> Estos pasos deben agregarse a la canalización en el orden especificado anteriormente para su correcta ejecución.

## <a name="choose-a-learning-algorithm"></a>Elegir un algoritmo de aprendizaje

Después de agregar los datos a la canalización y transformarlos en el formato de entrada correcto, seleccione un algoritmo de aprendizaje (**aprendiz**). El algoritmo de aprendizaje entrena el modelo. Eligió una **tarea de regresión** para este problema, por lo que agregó un aprendiz llamado `FastTreeRegressor()` a la canalización que utiliza la **potenciación de gradiente**.

La potenciación de gradiente es una técnica para los problemas de regresión de aprendizaje automático. Crea cada árbol de regresión de forma escalonada. Utiliza una función de pérdida predefinida para medir el error en cada paso y corregirlo en el siguiente. El resultado es un modelo de predicción que es realmente un conjunto de modelos de predicción más débiles. Para obtener más información sobre la potenciación de gradiente, consulte [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regresión de árbol de decisión potenciado).

Agregue el código siguiente al método `Train()` después del código de procesamiento de datos que agregó en el último paso:

```csharp
pipeline.Add(new FastTreeRegressor());
```

Agregó todos los pasos anteriores a la canalización como instrucciones individuales, pero C# tiene una útil sintaxis de inicialización de recopilación que simplifica la creación e inicialización de la canalización. Reemplace el código que ha agregado hasta ahora al método `Train()` por el siguiente código:

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a>Entrenar el modelo

El último paso es entrenar el modelo. Hasta este punto, no se ha ejecutado nada en la canalización. La función `pipeline.Train<T_Input, T_Output>()` toma el tipo de clase `TaxiTrip` predefinido y genera un tipo `TaxiTripFarePrediction`. Agregue este último fragmento de código a la función `Train()`:

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

Y listo. Ha entrenado correctamente un modelo de aprendizaje automático que puede predecir tarifas de taxi en Nueva York. Ahora eche un vistazo para valorar el grado de precisión de su modelo y aprender a utilizarlo.

## <a name="save-the-model"></a>Guardado del modelo

Antes de ir al siguiente paso, guarde el modelo en un archivo .zip agregando el código siguiente al final de su función `Train()`:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

La adición de la instrucción `await` a la llamada `model.WriteAsync()` implica que el método `Train()` debe cambiarse a un método asincrónico que devuelva un `Task`. Modifique la firma del `Train` tal como se muestra en el código siguiente:

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

El cambio del tipo de valor devuelto del método `Train` implica que tiene que agregar `await` al código que llama a `Train` en el método `Main` tal como se muestra en el código siguiente:

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

La adición de `await` en su método `Main` implica que el método `Main` debe tener un modificador `async` y devolver un `Task`:

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

También tiene que agregar la siguiente instrucción using en la parte superior del archivo:

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

Debido a que el método `async Main` es una característica nueva en C# 7.1 y la versión de lenguaje predeterminada del proyecto es C# 7.0, debe cambiar la versión del lenguaje a C# 7.1 o superior.
Para ello, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Propiedades**. Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**. En la lista desplegable, seleccione **C# 7.1** (o una versión superior). Seleccione el botón **Aceptar**.

## <a name="evaluate-the-model"></a>Evaluar el modelo

La evaluación es el proceso que sirve para comprobar cómo funciona el modelo. Es importante que su modelo haga buenas predicciones sobre los datos que no utilizó cuando se entrenó. Una forma de hacerlo es dividiendo los datos en conjuntos de datos de entrenamiento y prueba, tal y como hizo en este tutorial. Ahora que ha entrenado el modelo en los datos de entrenamiento, puede ver qué tal funciona en los datos de prueba.

Vuelva a su función `Main` y agregue el siguiente código debajo de la llamada al método `Train()`:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

La función `Evaluate()` evalúa el modelo. Cree esa función debajo de `Train()`. Agregue el código siguiente:

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

Cargue los datos de prueba mediante la función `TextLoader()`. Agregue el código siguiente al método `Evaluate()`:

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

Agregue el código siguiente para evaluar el modelo y generar las métricas para él:

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

RMS es una métrica para evaluar los problemas de regresión. Cuanto menor sea, mejor será el modelo. Agregue el código siguiente a la función `Evaluate()` para imprimir el RMS para el modelo.

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

RSquared es otra métrica para evaluar los problemas de regresión. RSquared será un valor comprendido entre 0 y 1. Cuanto más se acerque a 1, mejor será el modelo. Agregue el código siguiente a la función `Evaluate()` para imprimir el valor de RSquared para el modelo.

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a>Usar el modelo para las predicciones

A continuación, cree una clase para hospedar escenarios de prueba que puede usar para asegurarse de que el modelo funciona correctamente:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.
1. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TestTrips.cs*. A continuación, seleccione el botón **Agregar**.
1. Modifique la clase para que sea estática, como en el ejemplo siguiente:

[!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

En este tutorial se utiliza un viaje de prueba en esta clase. Más adelante, puede agregar otros escenarios para experimentar con este ejemplo. Agregue el código siguiente a la clase `TestTrips`:

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

La tarifa real de este viaje es 29,5, pero utilice 0 como marcador de posición. El algoritmo de aprendizaje automático predecirá el importe del servicio.

Agregue el código siguiente a la función `Main`. Prueba su modelo usando los datos `TestTrip`:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

Ejecute el programa para ver la tarifa de taxi predicha para su caso de prueba.

¡Enhorabuena! Ya ha creado correctamente un modelo de aprendizaje automático para predecir tarifas de taxi, ha evaluado su precisión y lo ha probado. Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).

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

---
title: 'Tutorial: Detección de anomalías en las ventas de productos'
description: Aprenda a crear una aplicación de detección de anomalías para los datos de ventas de productos. En este tutorial se va a crear una aplicación de consola de .NET Core mediante C# en Visual Studio 2019.
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: c3fd4aa715a64a20f1eff9b789f6a87eaa749163
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78239994"
---
# <a name="tutorial-detect-anomalies-in-product-sales-with-mlnet"></a>Tutorial: Detección de anomalías en ventas de productos con ML.NET

Aprenda a crear una aplicación de detección de anomalías para los datos de ventas de productos. En este tutorial se va a crear una aplicación de consola de .NET Core mediante C# en Visual Studio.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> * Carga de los datos
> * Crear una transformación para la detección de anomalías de picos
> * Detectar anomalías de picos con la transformación
> * Crear una transformación para la detección de anomalías de puntos de cambio
> * Detectar anomalías de puntos de cambio con la transformación

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2017, versión 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

* [El conjunto de datos product-sales.csv](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> El formato de datos en `product-sales.csv` se basa en el conjunto de datos "Shampoo Sales Over a Three Year Period" (Ventas de champú en un período de tres años) procedente originalmente de DataMarket y proporcionado por Time Series Data Library (TSDL), creado por Rob Hyndman.
> Conjunto de datos "Shampoo Sales Over a Three Year Period" con una licencia de conjunto de datos que se concede de acuerdo con DataMarket Default Open License.

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Cree una **aplicación de consola de .NET Core** denominada "ProductSalesAnomalyDetection".

2. Cree un directorio denominado *Datos* en el proyecto para guardar los archivos del conjunto de datos.

3. Instale el **paquete NuGet Microsoft.ML**:

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML** y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados. Repita estos pasos para **Microsoft.ML.TimeSeries**.

4. Agregue las instrucciones `using` siguientes en la parte superior del archivo *Program.cs*:

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a>Descarga de los datos

1. Descargue el conjunto de datos y guárdelo en la carpeta *Datos* que creó anteriormente:

   * Haga clic con el botón derecho en [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) y seleccione "Guardar vínculo (o destino) como...".

     Asegúrese de que guarda el archivo \*.csv en la carpeta *Datos* o, después de guardarlo en otro lugar, mueva el archivo \*.csv a la carpeta *Datos*.

2. En el Explorador de soluciones, haga clic con el botón derecho en el archivo \*.csv y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

La siguiente tabla es una vista previa de datos del archivo \*.csv:

|Mes  |ProductSales |
|-------|-------------|
|1 - Ene  |    271      |
|2 - Ene  |    150,9    |
|.....  |    .....    |
|1 - Feb  |    199,3    |
|.....  |    .....    |

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

A continuación, defina las estructuras de datos de la clase de entrada y de predicción.

Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nuevo elemento**.

2. En el **cuadro de diálogo Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *ProductSalesData.cs*. A continuación, seleccione el botón **Agregar**.

   El archivo *ProductSalesData.cs* se abre en el editor de código.

3. Agregue la siguiente instrucción `using` al principio de *ProductSalesData.cs*:

   ```csharp
   using Microsoft.ML.Data;
   ```

4. Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases, `ProductSalesData` y `ProductSalesPrediction`, al archivo *ProductSalesData.cs*:

    [!code-csharp[DeclareTypes](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/ProductSalesData.cs#DeclareTypes "Declare data record types")]

    `ProductSalesData` especifica una clase de datos de entrada. El atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) especifica qué columnas (por índice de columna) del conjunto de datos se deben cargar.

    `ProductSalesPrediction` especifica la clase de datos de predicción. En la detección de anomalías, la predicción consiste en una alerta que indica si hay una anomalía, una puntuación sin procesar y un valor p. Cuanto más se acerque el valor p a 0, más probable es que se haya producido una anomalía.

5. Cree dos campos globales para contener la ruta de acceso del archivo de conjunto de datos recientemente descargado y la ruta de acceso del archivo de modelo guardado:

    * `_dataPath` tiene la ruta de acceso al conjunto de datos utilizado para entrenar el modelo.
    * `_docsize` tiene el número de registros en el archivo de conjunto de datos. Usará `_docSize` para calcular `pvalueHistoryLength`.

6. Agregue el código siguiente a la línea justo encima del método `Main` para especificar las rutas de acceso:

    [!code-csharp[Declare global variables](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a>Inicializar variables en Main

1. Reemplace la línea `Console.WriteLine("Hello World!")` del método `Main` por el siguiente código para declarar e inicializar la variable `mlContext`:

    [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Como concepto, se parece a `DBContext` en Entity Framework.

### <a name="load-the-data"></a>Carga de los datos

Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView). `IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto). Los datos se pueden cargar desde un archivo de texto o u otros orígenes (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.

1. Agregue el siguiente código como la siguiente línea del método `Main()`:

    [!code-csharp[LoadData](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#LoadData "loading dataset")]

    [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo. Toma las variables de ruta de acceso de datos y devuelve `IDataView`.

## <a name="time-series-anomaly-detection"></a>Detección de anomalías en una serie temporal

La detección de anomalías marca comportamientos o eventos inesperados o poco habituales. Proporciona pistas sobre dónde buscar problemas y ayuda a responder la pregunta "¿es extraño esto?".

![Ejemplo de la detección de anomalías "Es extraño esto".](./media/sales-anomaly-detection/time-series-anomaly-detection.png)

La detección de anomalías es el proceso de detectar valores atípicos de datos de series temporales, puntos en determinada serie temporal de entrada donde el comportamiento no es lo que se esperaba o es "extraño".

La detección de anomalías puede ser útil de muchas maneras. Por ejemplo:

Si tiene un automóvil, tal vez desee saber: ¿Es normal la lectura del medidor de gasolina o tengo una fuga?
Si está supervisando el consumo de energía, desearía saber: ¿Hay una interrupción?

Hay dos tipos de anomalías de series temporales que se pueden detectar:

* Los **picos** indican ráfagas temporales de comportamiento anómalo en el sistema.

* Los **puntos de cambio** indican el inicio de cambios persistentes con el tiempo en el sistema.

En ML.NET, los algoritmos de la detección de picos de IID o de la detección de puntos de cambio de IID son adecuados para los [conjuntos de datos independientes y distribuidos de manera idéntica](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).

A diferencia de los modelos de los otros tutoriales, las transformaciones del detector de anomalías de series temporales funcionan directamente en los datos de entrada. El método `IEstimator.Fit()` no necesita datos de entrenamiento para generar la transformación. Sin embargo, necesita el esquema de datos, que se proporciona mediante una vista de datos generada a partir de una lista vacía de `ProductSalesData`.

Analizará los mismos datos de ventas de productos para detectar los picos y los puntos de cambio. El proceso de modelo de entrenamiento y compilación es el mismo para la detección de picos y la detección de puntos de cambio. La principal diferencia es el algoritmo de detección específico que se utiliza.

## <a name="spike-detection"></a>Detección de picos

El objetivo de la detección de picos es identificar ráfagas repentinas pero temporales que difieren significativamente de la mayoría de los valores de datos de las series temporales. Es importante detectar estos elementos, eventos u observaciones poco frecuentes y sospechosos de manera oportuna con el fin de minimizarlos. El siguiente enfoque puede utilizarse para detectar una variedad de anomalías, como interrupciones, ciberataques o contenido web viral. La siguiente imagen es un ejemplo de los picos de un conjunto de datos de serie temporal:

![Captura de pantalla en la que se muestran dos detecciones de picos.](./media/sales-anomaly-detection/two-spike-detections.png)

### <a name="add-the-createemptydataview-method"></a>Agregar el método CreateEmptyDataView()

Agregue el método siguiente a `Program.cs`:

[!code-csharp[CreateEmptyDataView](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateEmptyDataView)]

`CreateEmptyDataView()` genera un objeto de vista de datos vacío con el esquema correcto que se va a usar como entrada para el método `IEstimator.Fit()`.

### <a name="create-the-detectspike-method"></a>Crear el método DetectSpike()

El método `DetectSpike()` realiza las acciones siguientes:

* Crea la transformación desde el estimador.
* Detecta picos en función de los datos históricos de ventas.
* Muestra los resultados.

1. Cree el método `DetectSpike()`, justo después del método `Main()`, mediante el código siguiente:

    ```csharp
    static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. Use [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) para entrenar el modelo para la detección de picos. Agréguelo a un método `DetectSpike()` en el siguiente código:

    [!code-csharp[AddSpikeTrainer](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#AddSpikeTrainer)]

1. Para crear la transformación de detección de picos, agregue lo que se indica a continuación como la siguiente línea de código en el método `DetectSpike()`:

    [!code-csharp[TrainModel1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TrainModel1)]

1. Agregue la siguiente línea de código para transformar los datos `productSales` como la siguiente línea en el método `DetectSpike()`:

    [!code-csharp[TransformData1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TransformData1)]

    El código anterior usa el método [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) para hacer predicciones para varias filas de entrada de un conjunto de datos.

1. Convierta su `transformedData` en `IEnumerable` fuertemente tipado para mostrar fácilmente mediante el método [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) con el código siguiente:

    [!code-csharp[CreateEnumerable1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateEnumerable1)]

1. Cree una línea de encabezado de visualización mediante el código <xref:System.Console.WriteLine?displayProperty=nameWithType> siguiente:

    [!code-csharp[DisplayHeader1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayHeader1)]

    Se mostrará la siguiente información en los resultados de detección de picos:

    * `Alert` indica una alerta de pico para determinado punto de datos.
    * `Score` es el valor `ProductSales` para determinado punto de datos en el conjunto de datos.
    * `P-Value` La "P" significa probabilidad. Cuanto más se acerque el valor p a 0, más probable es que el punto de datos sea una anomalía.

1. Use el siguiente código para iterar en `predictions` `IEnumerable` y mostrar los resultados:

    [!code-csharp[DisplayResults1](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayResults1)]

1. Agregue la llamada al método `DetectSpike()` en el método `Main()`:

    [!code-csharp[CallDetectSpike](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CallDetectSpike)]

## <a name="spike-detection-results"></a>Resultados de la detección de picos

Los resultados deberían ser similares a los indicados a continuación. Durante el procesamiento, se muestran mensajes. Puede ver las advertencias o mensajes de procesamiento. Algunos de los mensajes se han quitado de los resultados siguientes para mayor claridad.

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a>Detección de puntos de cambio

`Change points` son cambios permanentes en una distribución de valores de secuencia de eventos de serie temporal, como los cambios de nivel y las tendencias. Estos cambios persistentes duran mucho más tiempo que `spikes` y podrían indicar eventos catastróficos. `Change points` no son normalmente visibles a simple vista, pero se pueden detectar en los datos mediante enfoques como el del siguiente método.  La siguiente imagen es un ejemplo de una detección de puntos de cambio:

![Captura de pantalla en la que se muestra una detección de puntos de cambio.](./media/sales-anomaly-detection/change-point-detection.png)

### <a name="create-the-detectchangepoint-method"></a>Crear el método DetectChangepoint()

El método `DetectChangepoint()` ejecuta las tareas siguientes:

* Crea la transformación desde el estimador.
* Detecta puntos de cambio en función de los datos históricos de ventas.
* Muestra los resultados.

1. Cree el método `DetectChangepoint()`, justo después del método `Main()`, mediante el código siguiente:

    ```csharp
    static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. Cree [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) en el método `DetectChangepoint()` con el código siguiente:

    [!code-csharp[AddChangepointTrainer](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#AddChangepointTrainer)]

1. Como hizo anteriormente, cree la transformación desde el estimador agregando la siguiente línea de código en el método `DetectChangePoint()`:

    [!code-csharp[TrainModel2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TrainModel2)]

1. Use el método `Transform()` para transformar los datos mediante la adición del código siguiente a `DetectChangePoint()`:

    [!code-csharp[TransformData2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#TransformData2)]

1. Como lo hizo anteriormente, convierta su `transformedData` en `IEnumerable` fuertemente tipado para mostrar fácilmente mediante el método `CreateEnumerable()` con el código siguiente:

    [!code-csharp[CreateEnumerable2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CreateEnumerable2)]

1. Cree un encabezado de visualización con el siguiente código como la siguiente línea en el método `DetectChangePoint()`:

    [!code-csharp[DisplayHeader2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayHeader2)]

    Se mostrará la siguiente información en los resultados de detección de puntos de cambio:

    * `Alert` indica una alerta de punto de cambio para determinado punto de datos.
    * `Score` es el valor `ProductSales` para determinado punto de datos en el conjunto de datos.
    * `P-Value` La "P" significa probabilidad. Cuanto más se acerque el valor P a 0, más probable es que el punto de datos sea una anomalía.
    * `Martingale value` se usa para identificar cuán "extraño" es un punto de datos, en función de la secuencia de valores de P.

1. Itere en `predictions` `IEnumerable` y muestre los resultados con el siguiente código:

    [!code-csharp[DisplayResults2](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#DisplayResults2)]

1. Agregue la llamada siguiente al método `DetectChangepoint()` en el método `Main()`:

    [!code-csharp[CallDetectChangepoint](~/samples/snippets/machine-learning/ProductSalesAnomalyDetection/csharp/Program.cs#CallDetectChangepoint)]

## <a name="change-point-detection-results"></a>Resultados de la detección de puntos de cambio

Los resultados deberían ser similares a los indicados a continuación. Durante el procesamiento, se muestran mensajes. Puede ver las advertencias o mensajes de procesamiento. Algunos de los mensajes se han quitado de los resultados siguientes para mayor claridad.

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

¡Enhorabuena! Ya ha creado correctamente los modelos de aprendizaje automático para detectar anomalías de picos y puntos de cambio en los datos de ventas.

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

En este tutorial ha aprendido a:
> [!div class="checklist"]
>
> * Carga de los datos
> * Entrenar el modelo para la detección de anomalías de picos
> * Detectar anomalías de picos con el modelo entrenado
> * Entrenar el modelo para la detección de anomalías de puntos de cambio
> * Detectar anomalías de puntos de cambio con el modelo entrenado

## <a name="next-steps"></a>Pasos siguientes

Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo de detección de anomalías de consumo de energía.
> [!div class="nextstepaction"]
> [Repositorio dotnet/machinelearning-samples de GitHub](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)

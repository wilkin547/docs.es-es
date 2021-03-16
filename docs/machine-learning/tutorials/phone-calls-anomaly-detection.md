---
title: 'Tutorial: Detección de anomalías en las llamadas telefónicas'
description: Aprenda a crear una aplicación de detección de anomalías para los datos de series temporales. En este tutorial se va a crear una aplicación de consola de .NET Core mediante C# en Visual Studio 2019.
ms.date: 12/04/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7edb84ae53f1da7903cf4b3f77d215206ffbf1ef
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259829"
---
# <a name="tutorial-detect-anomalies-in-time-series-with-mlnet"></a>Tutorial: Detección de anomalías en series temporales con ML.NET

Aprenda a crear una aplicación de detección de anomalías para los datos de series temporales. En este tutorial se va a crear una aplicación de consola de .NET Core mediante C# en Visual Studio 2019.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> * Carga de los datos
> * Detectar el período para una serie temporal
> * Detectar anomalías para una serie temporal periódica

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection).

## <a name="prerequisites"></a>Requisitos previos

* [Visual Studio 2019, versión 16.7.8 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.

* [Conjunto de datos phone-calls.csv](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrEntireDetection/Data/phone-calls.csv).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. Cree una **aplicación de consola de .NET Core en C#** denominada "PhoneCallsAnomalyDetection".

2. Cree un directorio denominado *Datos* en el proyecto para guardar los archivos de conjunto de datos.

3. Instale el **paquete NuGet Microsoft.ML**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    En el Explorador de soluciones, haga clic con el botón derecho en **Administrar paquetes NuGet**. Elija "nuget.org" como origen del paquete, seleccione la pestaña Examinar, busque **Microsoft.ML** y seleccione el botón **Instalar**. Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados. Repita estos pasos para **Microsoft.ML.TimeSeries**.

4. Agregue las instrucciones `using` siguientes en la parte superior del archivo *Program.cs*:

    [!code-csharp[AddUsings](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a>Descarga de los datos

1. Descargue el conjunto de datos y guárdelo en la carpeta *Datos* que creó anteriormente:

    Haga clic con el botón derecho en [*phone-calls.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_PhoneCalls/SrEntireDetection/Data/phone-calls.csv) y seleccione "Guardar vínculo (o destino) como...".

     Asegúrese de que guarda el archivo \*.csv en la carpeta *Datos* o, después de guardarlo en otro lugar, mueva el archivo \*.csv a la carpeta *Datos*.

2. En el Explorador de soluciones, haga clic con el botón derecho en el archivo \*.csv y seleccione **Propiedades**. En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.

La siguiente tabla es una vista previa de datos del archivo \*.csv:

| timestamp  | value |
|--------|--------------|
| 2018/9/3  | 36.69670857  |
| 2018/9/4  | 35.74160571  |
| .....  | .....  |
| 2018/10/3  | 34.49893429  |
| ...    | ....   |

Este archivo representa una serie temporal. Cada fila del archivo es un punto de datos. Cada punto de datos tiene dos atributos, es decir, `timestamp` y `value`, para representar el número de llamadas telefónicas de cada día. El número de llamadas telefónicas se marca como no confidencial.

### <a name="create-classes-and-define-paths"></a>Crear clases y definir rutas de acceso

A continuación, defina las estructuras de datos de la clase de entrada y de predicción.

Agregue una nueva clase a su proyecto:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar > Nuevo elemento**.

2. En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *s*. A continuación, seleccione el botón **Agregar**.

   El archivo *PhoneCallsData.cs* se abre en el editor de código.

3. Agregue la siguiente instrucción `using` al principio de *PhoneCallsData.cs*:

   ```csharp
   using Microsoft.ML.Data;
   ```

4. Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `PhoneCallsData` y `PhoneCallsPrediction`, al archivo *PhoneCallsData.cs*:

    [!code-csharp[DeclareTypes](./snippets/phone-calls-anomaly-detection/csharp/PhoneCallsData.cs#DeclareTypes "Declare data record types")]

    `PhoneCallsData` especifica una clase de datos de entrada. El atributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) especifica qué columnas (por índice de columna) del conjunto de datos se deben cargar. Tiene dos atributos `timestamp` y `value` que se corresponden con los mismos atributos en el archivo de datos.

    `PhoneCallsPrediction` especifica la clase de datos de predicción. Para el detector de SR-CNN, la predicción depende del [modo de detección](xref:Microsoft.ML.TimeSeries.SrCnnDetectMode) especificado. En este ejemplo, se selecciona el modo `AnomalyAndMargin`. La salida contiene siete columnas. En la mayoría de los casos, `IsAnomaly`, `ExpectedValue`, `UpperBoundary` y `LowerBoundary` son lo suficientemente informativas. Indican si un punto es una anomalía, el valor esperado del punto y la región del límite inferior y superior del punto.

5. Agregue el código siguiente a la línea inmediatamente por encima del método `Main` para especificar la ruta de acceso al archivo de datos:

    [!code-csharp[Declare global variables](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a>Inicializar variables en Main

1. Reemplace la línea `Console.WriteLine("Hello World!")` del método `Main` por el siguiente código para declarar e inicializar la variable `mlContext`:

    [!code-csharp[CreateMLContext](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    La [clase MLContext](xref:Microsoft.ML.MLContext) es un punto de partida para todas las operaciones de ML.NET. Al inicializar `mlContext`, se crea un entorno de ML.NET que se puede compartir entre los objetos del flujo de trabajo de creación de modelos. Como concepto, se parece a `DBContext` en Entity Framework.

### <a name="load-the-data"></a>Carga de los datos

Los datos de ML.NET se representan como una [clase IDataView](xref:Microsoft.ML.IDataView). `IDataView` es una manera flexible y eficiente de describir datos tabulares (numéricos y de texto). Los datos se pueden cargar desde un archivo de texto o u otros orígenes (por ejemplo, archivos de registro o base de datos SQL) en un objeto `IDataView`.

1. Agregue el siguiente código como la siguiente línea del método `Main`:

    [!code-csharp[LoadData](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#LoadData "loading dataset")]

    [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) define el esquema de datos y lee en el archivo. Toma las variables de ruta de acceso de datos y devuelve `IDataView`.

## <a name="time-series-anomaly-detection"></a>Detección de anomalías en una serie temporal

La detección de anomalías en una serie temporal es el proceso de detectar valores atípicos de datos de series temporales, puntos en determinada serie temporal de entrada donde el comportamiento no es lo que se esperaba o es "extraño". Estas anomalías son normalmente indicativas de algunos eventos de interés en el dominio del problema: un ciberataque en las cuentas de usuario, una interrupción del suministro eléctrico, una ráfaga de solicitudes por segundo en un servidor, una fuga de memoria, etc.

Para buscar anomalías en una serie temporal, primero debe determinar el período de la serie. Después, la serie temporal se puede descomponer en varios componentes como `Y = T + S + R`, donde `Y` es la serie original, `T` es el componente de tendencia, `S` es el componente estacional y `R` es el componente residual de la serie. Este paso se denomina [descomposición](https://en.wikipedia.org/wiki/Decomposition_of_time_series). Por último, se realiza la detección en el componente residual para encontrar las anomalías. En ML.NET, el algoritmo SR-CNN es un algoritmo avanzado nuevo que se basa en la red neuronal residual (SR) y la red neuronal de circunvolución (CNN) para detectar anomalías en la serie temporal. Para obtener más información sobre este algoritmo, consulte [Servicio de detección de anomalías en una serie temporal en Microsoft](https://arxiv.org/pdf/1906.03821.pdf).

En este tutorial, verá que estos procedimientos se pueden llevar a cabo con dos funciones.

## <a name="detect-period"></a>Detección del período

En el primer paso, se invoca la función `DetectSeasonality` para determinar el período de la serie.

### <a name="create-the-detectperiod-method"></a>Creación del método DetectPeriod

1. Cree el método `DetectPeriod`, justo debajo del método `Main`, mediante el código siguiente:

    ```csharp
    static void DetectPeriod(MLContext mlContext, IDataView phoneCalls)
    {

    }
    ```

2. Utilice la función <xref:Microsoft.ML.TimeSeriesCatalog.DetectSeasonality%2A> para detectar el período. Agréguelo a un método `DetectPeriod` en el siguiente código:

    [!code-csharp[DetectSeasonality](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectSeasonality)]

3. Muestre el valor del período agregando lo que se indica a continuación como la siguiente línea de código en el método `DetectPeriod`:

    [!code-csharp[DisplayPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayPeriod)]

4. Agregue la llamada siguiente al método `DetectPeriod` en el método `Main`:

    [!code-csharp[CallDetectPeriod](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectPeriod)]

### <a name="period-detection-results"></a>Resultados de la detección del período

Ejecute la aplicación. Los resultados deberían ser similares a los indicados a continuación.

```console
Period of the series is: 7.
```

## <a name="detect-anomaly"></a>Detección de anomalías

En este paso, usará el método <xref:Microsoft.ML.TimeSeriesCatalog.DetectEntireAnomalyBySrCnn%2A> para buscar anomalías.

### <a name="create-the-detectanomaly-method"></a>Creación del método DetectAnomaly

1. Cree el método `DetectAnomaly`, justo debajo del método `DetectPeriod`, mediante el código siguiente:

    ```csharp
    static void DetectAnomaly(MLContext mlContext, IDataView phoneCalls, int period)
    {

    }
    ```

2. Configure el método <xref:Microsoft.ML.TimeSeries.SrCnnEntireAnomalyDetectorOptions> en el método `DetectAnomaly` con el código siguiente:

    [!code-csharp[SetupSrCnnParameters](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#SetupSrCnnParameters)]

3. Detecte anomalías mediante el algoritmo SR-CNN agregando la siguiente línea de código en el método `DetectAnomaly`:

    [!code-csharp[DetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DetectAnomaly)]

4. Convierta la vista de datos de salida en un `IEnumerable` fuertemente tipado para mostrar fácilmente mediante el método [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) con este código:

    [!code-csharp[CreateEnumerableForResult](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CreateEnumerableForResult)]

5. Cree un encabezado de visualización con el siguiente código como la siguiente línea en el método `DetectAnomaly`:

    [!code-csharp[DisplayHeader](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayHeader)]

    Se mostrará la siguiente información en los resultados de detección de puntos de cambio:

    * `Index` es el índice de cada punto.
    * `Anomaly` es el indicador de si cada punto se detecta como anomalía.
    * `ExpectedValue` es el valor estimado de cada punto.
    * `LowerBoundary` es el valor más bajo de que cada punto no sea una anomalía.
    * `UpperBoundary` es el valor más alto de que cada punto no sea una anomalía.

6. Itere en `predictions` `IEnumerable` y muestre los resultados con el siguiente código:

    [!code-csharp[DisplayAnomalyDetectionResults](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#DisplayAnomalyDetectionResults)]

7. Agregue la llamada siguiente al método `DetectAnomaly` en el método `Main`:

    [!code-csharp[CallDetectAnomaly](./snippets/phone-calls-anomaly-detection/csharp/Program.cs#CallDetectAnomaly)]

## <a name="anomaly-detection-results"></a>Resultados de detección de anomalías

Ejecute la aplicación. Los resultados deberían ser similares a los indicados a continuación. Durante el procesamiento, se muestran mensajes. Puede ver las advertencias o mensajes de procesamiento. Algunos de los mensajes se han quitado de los resultados siguientes para mayor claridad.

```console
Detect period of the series
Period of the series is: 7.
Detect anomaly points in the series
Index   Data    Anomaly AnomalyScore    Mag     ExpectedValue   BoundaryUnit    UpperBoundary   LowerBoundary
0,0,36.841787256739266,41.14206982401966,32.541504689458876
1,0,35.67303618137362,39.97331874865401,31.372753614093227
2,0,34.710132999891826,39.029491313022824,30.390774686760828
3,0,33.44765248883495,37.786086547816545,29.10921842985335
4,0,28.937110922276364,33.25646923540736,24.61775260914537
5,0,5.143895892785781,9.444178460066171,0.843613325505391
6,0,5.163325228419392,9.463607795699783,0.8630426611390014
7,0,36.76414836240396,41.06443092968435,32.46386579512357
8,0,35.77908590657007,40.07936847385046,31.478803339289676
9,0,34.547259536635245,38.847542103915636,30.246976969354854
10,0,33.55193524820608,37.871293561337076,29.23257693507508
11,0,29.091800129624648,33.392082696905035,24.79151756234426
12,0,5.154836630338823,9.455119197619213,0.8545540630584334
13,0,5.234332502492464,9.534615069772855,0.934049935212073
14,0,36.54992549471526,40.85020806199565,32.24964292743487
15,0,35.79526470980883,40.095547277089224,31.494982142528443
16,0,34.34099013096804,38.64127269824843,30.040707563687647
17,0,33.61201516582131,37.9122977331017,29.31173259854092
18,0,29.223563320561812,33.5238458878422,24.923280753281425
19,0,5.170512168851533,9.470794736131923,0.8702296015711433
20,0,5.2614938889462834,9.561776456226674,0.9612113216658926
21,0,36.37103858487317,40.67132115215356,32.07075601759278
22,0,35.813544599026855,40.113827166307246,31.513262031746464
23,0,34.05600492733225,38.356287494612644,29.755722360051863
24,0,33.65828319077884,37.95856575805923,29.358000623498448
25,0,29.381125690882463,33.681408258162854,25.080843123602072
26,0,5.261543539820418,9.561826107100808,0.9612609725400283
27,0,5.4873712582971805,9.787653825577571,1.1870886910167897
28,1,36.504694001629254,40.804976568909645,32.20441143434886  <-- alert is on, detected anomaly
...
```

¡Enhorabuena! Ya ha creado correctamente los modelos de aprendizaje automático para detectar períodos y anomalías en series periódicas.

Puede encontrar el código fuente para este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/PhoneCallsAnomalyDetection).

En este tutorial ha aprendido a:
> [!div class="checklist"]
>
> * Carga de los datos
> * Detectar períodos en datos de una serie temporal
> * Detectar anomalías en datos de una serie temporal

## <a name="next-steps"></a>Pasos siguientes

Consulte el repositorio de GitHub con ejemplos de Machine Learning para explorar un ejemplo de detección de anomalías de consumo de energía.
> [!div class="nextstepaction"]
> [Repositorio dotnet/machinelearning-samples de GitHub](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)

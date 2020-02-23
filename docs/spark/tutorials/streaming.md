---
title: Tutorial Structured Streaming con .NET para Apache Spark
description: En este tutorial, aprenderá a usar .NET para Apache Spark para Spark Structured Streaming.
author: mamccrea
ms.author: mamccrea
ms.date: 12/04/2019
ms.topic: tutorial
ms.openlocfilehash: 83d44af080d95ab6f9311ddd3ca4860806757436
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504044"
---
# <a name="tutorial-structured-streaming-with-net-for-apache-spark"></a>Tutorial: Structured Streaming con .NET para Apache Spark 

En este tutorial aprenderá a invocar Spark Structured Streaming mediante .NET para Apache Spark. Spark Structured Streaming es la compatibilidad de Apache Spark con el procesamiento de flujos de datos en tiempo real. El procesamiento de flujos se refiere a la realización de análisis de datos activos a medida que se producen.

En este tutorial aprenderá a:

> [!div class="checklist"]
>
> * Crear y ejecutar una aplicación de .NET para Apache Spark
> * Usar netcat para crear un flujo de datos
> * Usar funciones definidas por el usuario y SparkSQL para analizar datos de streaming

## <a name="prerequisites"></a>Requisitos previos

Si esta es su primera aplicación de .NET para Apache Spark, comience con el [tutorial de introducción](get-started.md) para familiarizarse con los aspectos básicos.

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. En el símbolo del sistema, ejecute los comandos siguientes para crear una aplicación de consola:

   ```dotnetcli
   dotnet new console -o mySparkStreamingApp
   cd mySparkStreamingApp
   ```

   El comando `dotnet` crea una aplicación `new` de tipo `console` de forma automática. El parámetro `-o` crea un directorio denominado *mySparkStreamingApp* donde se almacena la aplicación y lo rellena con los archivos necesarios. El comando `cd mySparkStreamingApp` cambia el directorio al directorio de la aplicación que acaba de crear.

1. Para usar .NET para Apache Spark en una aplicación, instale el paquete Microsoft.Spark. En la consola, ejecute el siguiente comando:

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="establish-and-connect-to-a-data-stream"></a>Establecimiento y conexión a un flujo de datos

Una forma popular de probar el procesamiento de flujos es a través de **netcat**. netcat (también conocido como *nc*) le permite leer desde conexiones de red y escribir en ellas. Establezca una conexión de red con netcat a través de una ventana de terminal. 

### <a name="create-a-data-stream-with-netcat"></a>Creación de un flujo de datos con netcat

1. [Descargue netcat](https://sourceforge.net/projects/nc110/files/). A continuación, extraiga el archivo de la descarga de zip y anexe el directorio que extrajo a su variable de entorno "PATH".

2. Para iniciar una nueva conexión, abra una nueva consola y ejecute el siguiente comando que se conecte a localhost en el puerto 9999.

   En Windows:

   ```console
   nc -vvv -l -p 9999
   ```

   En Linux:

   ```console
   nc -lk 9999
   ```

   El programa de Spark escucha la entrada que escribe en este símbolo del sistema.

### <a name="create-a-sparksession"></a>Creación de una SparkSession

1. Agregue las instrucciones `using` adicionales siguientes a la parte superior del archivo *Program.cs* en *mySparkStreamingApp*:

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using Microsoft.Spark.Sql.Streaming;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. Agregue el código siguiente al método `Main` para crear una nueva `SparkSession`. La sesión de Spark es el punto de entrada para programar Spark con la API de DataFrame y DataSet.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("Streaming example with a UDF")
        .GetOrCreate();
   ```

   Llamar al objeto *spark* creado anteriormente le permite tener acceso a la funcionalidad de DataFrame y Spark a través del programa.

### <a name="connect-to-a-stream-with-readstream"></a>Conexión a un flujo con ReadStream ()

El método `ReadStream()` devuelve un `DataStreamReader` que se puede usar para leer datos de streaming como `DataFrame`. Incluya la información del host y el puerto para indicar a su aplicación Spark dónde se deben esperar sus datos de streaming.

```csharp
DataFrame lines = spark
    .ReadStream()
    .Format("socket")
    .Option("host", hostname)
    .Option("port", port)
    .Load();
```

## <a name="register-a-user-defined-function"></a>Registro de una función definida por el usuario

Puede usar UDF, *funciones definidas por el usuario*, en aplicaciones Spark para realizar cálculos y análisis de los datos.

Agregue el siguiente código a su método `Main` para registrar una UDF llamada `udfArray`. 

```csharp
Func<Column, Column> udfArray =
    Udf<string, string[]>((str) => new string[] { str, $"{str} {str.Length}" });
```

Esta UDF procesa cada cadena que recibe del terminal netcat para producir una cadena que incluye la cadena original (contenida en *str*), seguida de la cadena original concatenada con la longitud de la cadena original. 

Por ejemplo, al escribir *Hola mundo* en el terminal netcat se produce una matriz donde:

* matriz\[0] = Hola mundo
* matriz\[1] = Hola mundo 11

## <a name="use-sparksql"></a>Uso de SparkSQL

Use SparkSQL para realizar diversas funciones en los datos almacenados en DataFrame. Es habitual combinar UDF y SparkSQL para aplicar una UDF a cada fila de un DataFrame.

```csharp
DataFrame arrayDF = lines.Select(Explode(udfArray(lines["value"])));
```

Este fragmento de código aplica *udfArray* a cada valor del DataFrame, que representa cada cadena leída del terminal netcat. Aplique el método SparkSQL <xref:Microsoft.Spark.Sql.Functions.Explode%2A> para colocar cada entrada de la matriz en su propia fila. Por último, use <xref:Microsoft.Spark.Sql.DataFrame.Select%2A> para colocar las columnas que ha producido en el nuevo DataFrame *arrayDF.*

## <a name="display-your-stream"></a>Presentación del flujo

Use <xref:Microsoft.Spark.Sql.DataFrame.WriteStream> para establecer las características de su salida, como la impresión de resultados en la consola y la presentación solamente de la salida más reciente.

```csharp
StreamingQuery query = arrayDf
    .WriteStream()
    .Format("console")
    .Start();
```

## <a name="run-your-code"></a>Ejecución del código

Structured Streaming en Spark procesa datos a través de una serie de pequeños **lotes**.  Al ejecutar su programa, el símbolo del sistema donde establece la conexión netcat le permite empezar a escribir. Cada vez que presiona la tecla Entrar tras escribir datos en ese símbolo del sistema, Spark considera su entrada un lote y ejecuta la UDF.

### <a name="use-spark-submit-to-run-your-app"></a>Uso de spark-submit para ejecutar la aplicación

Una vez iniciada una nueva sesión de netcat, abra un nuevo terminal y ejecute el comando `spark-submit`, similar al comando siguiente:

```powershell
spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /path/to/microsoft-spark-<version>.jar Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkCharacterCount localhost 9999
```

> [!NOTE]
> Asegúrese de actualizar el comando anterior con la ruta de acceso real a su archivo jar de Microsoft Spark. El comando anterior también da por hecho que su servidor netcat se ejecuta en el puerto localhost 9999.

## <a name="get-the-code"></a>Obtención del código

En este tutorial se usa el ejemplo [StructuredNetworkCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs), pero hay otros tres ejemplos de procesamiento de flujos completo en GitHub:

* [StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): recuento de palabras en datos de streaming de cualquier origen
* [StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): recuento de palabras en datos con lógica de ventanas
* [StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): recuento de palabras en datos de streaming de Kafka

## <a name="next-steps"></a>Pasos siguientes

Avance al siguiente artículo para aprender a implementar su aplicación de .NET para Apache Spark en Databricks.
> [!div class="nextstepaction"]
> [Tutorial: Implementación de una aplicación de .NET para Apache Spark en Databricks](databricks-deployment.md)

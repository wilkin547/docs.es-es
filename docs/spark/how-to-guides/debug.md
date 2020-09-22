---
title: Depuración de una aplicación de .NET para Apache Spark en Windows
description: Sepa cómo depurar una aplicación de .NET para Apache Spark en Windows.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 249b4bccbf1378d8ef8c824f39151c33fb9f875a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557156"
---
# <a name="debug-a-net-for-apache-spark-application"></a>Depuración de una aplicación de .NET para Apache Spark

En este procedimiento se proporcionan los pasos para depurar una aplicación de .NET para Apache Spark en Windows.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="debug-your-application"></a>Depuración de la aplicación

Abra una ventana nueva del símbolo del sistema y ejecute este comando:

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

Al ejecutar el comando, verá la siguiente salida:

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

En el modo de depuración, DotnetRunner no inicia la aplicación de .NET, sino que espera a que el usuario inicie la aplicación de .NET. Deje abierta esta ventana del símbolo del sistema e inicie la aplicación de .NET a través del depurador de C# para depurar la aplicación. Inicie la depuración de .NET con un depurador de C# (el [depurador de Visual Studio para Windows/macOS](https://visualstudio.microsoft.com/vs/) o la [extensión del depurador de C# en Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)) para depurar la aplicación.

## <a name="debug-a-user-defined-function-udf"></a>Depuración de una función definida por el usuario (UDF)

> [!NOTE]
> Las funciones definidas por el usuario solo se admiten en Windows con el depurador de Visual Studio.

Antes de ejecutar `spark-submit`, establezca esta variable de entorno:

```bat
set DOTNET_WORKER_DEBUG=1
```

Al ejecutar la aplicación de Spark, aparecerá una ventana de `Choose Just-In-Time Debugger`. Elija un depurador de Visual Studio.

El depurador se interrumpirá en esta ubicación en [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52):

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

Vaya al archivo *.cs* que contiene la UDF que va a depurar y [establezca un punto de interrupción](/visualstudio/debugger/using-breakpoints?view=vs-2019). El punto de interrupción indicará `The breakpoint will not currently be hit`, porque el trabajo todavía no ha cargado el ensamblado que contiene la UDF.

Presione `F5` para continuar la aplicación y, a la larga, se alcanzará el punto de interrupción.

> [!NOTE]
> La ventana Choose Just-In-Time Debugger (Elegir el depurador Just-In-Time) aparece para cada tarea. Para evitar un exceso de elementos emergentes, establezca el número de ejecutores en un número bajo. Por ejemplo, puede usar la opción **--master local[1]** para spark-submit para establecer el número de tareas en 1, lo que inicia una instancia de depurador única.

## <a name="debug-scala-code"></a>Depuración de código de Scala

Si tiene que depurar el código de Scala (`DotnetRunner`, `DotnetBackendHandler`, etc.), puede usar el comando siguiente y adjuntar un depurador al proceso en ejecución mediante [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

Después de ejecutar el comando, asocie un depurador al proceso en ejecución mediante [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).

## <a name="next-steps"></a>Pasos siguientes

* [Introducción a .NET para Apache Spark](../tutorials/get-started.md)
* [Implementación de una aplicación de .NET para Apache Spark en Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [Implementación de una aplicación de .NET para Apache Spark en Databricks](../tutorials/databricks-deployment.md)
* [Implementación de una aplicación de .NET para Apache Spark en Amazon EMR Spark](../tutorials/amazon-emr-spark-deployment.md)

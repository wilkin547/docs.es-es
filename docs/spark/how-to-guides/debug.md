---
title: Depuración de una aplicación de .NET para Apache Spark en Windows
description: Sepa cómo depurar una aplicación de .NET para Apache Spark en Windows.
ms.date: 08/15/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 098c7519fe99ef04773c5e4b81685ca0f06f1272
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281530"
---
# <a name="debug-a-net-for-apache-spark-application"></a>Depuración de una aplicación de .NET para Apache Spark

En este procedimiento encontrará los comandos que hay que ejecutar para depurar la aplicación de .NET para Apache Spark y el código de Scala en Windows.

## <a name="debug-your-application"></a>Depuración de la aplicación

Abra una nueva ventana del símbolo del sistema y ejecute lo siguiente:

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

En este modo de depuración, `DotnetRunner` no inicia la aplicación .NET, sino que espera a que se conecte. Deje abierta esta ventana del símbolo del sistema.

Ahora puede ejecutar la aplicación .NET con cualquier depurador para depurarla.

## <a name="debug-scala-code"></a>Depuración de código de Scala

Si necesita depurar el código de Scala, como `DotnetRunner` o `DotnetBackendHandler`, ejecute el siguiente comando:

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

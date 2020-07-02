---
title: ¿Qué es .NET para Apache Spark?
description: Obtenga información sobre .NET para Apache Spark, un marco de análisis de macrodatos gratuito, de código abierto y multiplataforma que permite usar Spark en cualquier lugar en el que escriba código de .NET.
author: mamccrea
ms.topic: overview
ms.date: 06/25/2020
ms.openlocfilehash: 2c04861dabe604b52df583cd5a7eecc5ff8e5481
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621865"
---
# <a name="what-is-net-for-apache-spark"></a>¿Qué es .NET para Apache Spark?

[Apache Spark](what-is-spark.md) es un motor de procesamiento distribuido de uso general para realizar análisis de grandes conjuntos de datos (normalmente, terabytes o petabytes de datos). Con .NET para Apache Spark, la compatibilidad de .NET gratuita, de código abierto y multiplataforma para el conocido marco de análisis de macrodatos de código abierto, ahora puede agregar la capacidad de Apache Spark a las aplicaciones de macrodatos con lenguajes que ya conoce.

[!INCLUDE [spark-preview-note](../../includes/spark-preview-note.md)]

## <a name="why-choose-net-for-apache-spark"></a>¿Por qué elegir .NET para Apache Spark?

.NET para Apache Spark permite a los desarrolladores con experiencia en .NET o en bases de código participar en el mundo del análisis de macrodatos. .NET para Apache Spark proporciona API de alto rendimiento para usar Spark desde C# y F#. Con C# y F#, puede tener acceso a lo siguiente:

* DataFrame y SparkSQL para trabajar con datos estructurados.
* Spark Structured Streaming, para trabajar con datos de streaming.
* Spark SQL, para escribir consultas con sintaxis SQL.
* Integración de aprendizaje automático para acelerar el entrenamiento y la predicción (es decir, uso de .NET para Apache Spark junto con [ML.NET](https://dot.net/ml)).

.NET for Apache Spark es compatible con .NET Standard, una especificación formal de las API de .NET que son comunes entre las implementaciones de .NET. Esto significa que puede usar .NET para Apache Spark en cualquier lugar en el que escriba código de .NET, de modo que podrá reutilizar todo el conocimiento, los conocimientos, el código y las bibliotecas que ya posee como desarrollador de .NET.

.NET para Apache Spark se ejecuta en Windows, Linux y macOS con .NET Core. También se ejecuta en Windows con .NET Framework. Puede implementar las aplicaciones en todos los principales proveedores de servicios en la nube, como Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks y Databricks on AWS.

## <a name="net-for-apache-spark-architecture"></a>.NET para arquitectura de Apache Spark

El enlace del lenguaje C#/F# a Spark se escribe en una capa nueva de interoperabilidad de Spark que ofrece una extensibilidad más sencilla. Esta nueva capa de interoperabilidad de Spark se ha escrito usando los procedimientos recomendado para la extensión de lenguaje y optimiza la interoperabilidad y el rendimiento. A largo plazo, esta extensibilidad se puede usar para agregar compatibilidad con otros lenguajes en Spark.

> [!div class="mx-imgBorder"]
> ![.NET para arquitectura de Apache Spark](media/dotnet-spark-architecture.png)

Puede obtener información sobre la compatibilidad de interoperabilidad con las extensiones de lenguaje en Spark en [la propuesta](https://issues.apache.org/jira/browse/SPARK-26257).

## <a name="net-for-apache-spark-performance"></a>.NET para rendimiento de Apache Spark

Cuando se comparan con Python y Scala mediante el [banco de pruebas TPC-H](http://www.tpc.org/tpch/), .NET para Apache Spark funciona correctamente en la mayoría de los casos, y es dos veces más rápido que Python cuando el rendimiento de la función definida por el usuario es crítico. Existe un esfuerzo continuo por mejorar y realizar pruebas comparativas del rendimiento.

Para realizar su propio banco de pruebas, consulte los bancos de pruebas disponibles en el [GitHub de .NET para Apache Spark](https://github.com/dotnet/spark/tree/master/benchmark).

## <a name="net-for-apache-spark-roadmap"></a>Guía de .NET para Apache Spark

Obtenga información sobre los planes a corto y a largo plazo en la [Guía de .NET para Apache Spark](https://github.com/dotnet/spark/blob/master/ROADMAP.md).

## <a name="net-foundation"></a>.NET Foundation

El proyecto de .NET para Apache Spark forma parte de [.NET Foundation](https://www.dotnetfoundation.org/).

## <a name="contributions"></a>Contribuciones

El equipo de .NET para Apache Spark anima a que se aporten contribuciones, en forma tanto de incidencias de GitHub como de solicitudes de incorporación de cambios. En primer lugar, busque [una incidencia existente](https://github.com/dotnet/spark/issues). Si no encuentra una incidencia existente, [abra una nueva](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).

## <a name="next-steps"></a>Pasos siguientes

Pruebe .NET para Apache Spark.
> [!div class="nextstepaction"]
> [Tutorial: Introducción a .NET para Apache Spark](./tutorials/get-started.md)

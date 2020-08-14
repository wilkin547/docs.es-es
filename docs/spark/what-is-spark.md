---
title: ¿Qué es Apache Spark?
description: Más información sobre Apache Spark y escenarios de macrodatos.
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: cde66c4084b7c86e1b78d89c2bad94402dbd7d60
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555999"
---
# <a name="what-is-apache-spark"></a>¿Qué es Apache Spark?

[Apache Spark](https://spark.apache.org/) es una plataforma de procesamiento paralelo de código abierto que admite el procesamiento en memoria para mejorar el rendimiento de las aplicaciones que analizan macrodatos. Las soluciones de macrodatos están diseñadas para controlar datos que son demasiado grandes o complejos para las bases de datos tradicionales. Spark procesa grandes cantidades de datos en memoria, lo que es mucho más rápido que las alternativas basadas en disco.

## <a name="common-big-data-scenarios"></a>Escenarios comunes de macrodatos

Es posible que considere la posibilidad de usar una arquitectura de macrodatos si tiene que almacenar y procesar grandes volúmenes de datos, transformar datos no estructurados o procesos de transmisión de datos. Spark es un motor de procesamiento distribuido de uso general que se puede usar para varios escenarios de macrodatos.

### <a name="extract-transform-and-load-etl"></a>Extracción, transformación y carga de datos (ETL)

[Extracción, transformación y carga de datos (ETL)](/azure/architecture/data-guide/relational-data/etl) es el proceso de recopilación de datos de uno o varios orígenes, su modificación y el traslado a un nuevo almacén de datos. Existen varias maneras de transformar datos, como las siguientes:

* Filtros
* Ordenar
* Agregación
* Combinación
* Limpieza
* Desduplicación
* Validating

### <a name="real-time-data-stream-processing"></a>Procesamiento de flujos de datos en tiempo real

Los datos de streaming, o en tiempo real, son datos en movimiento. La telemetría desde dispositivos de IoT, blogs y clickstream son ejemplos de datos de streaming. Los datos en tiempo real se pueden procesar para proporcionar información útil, como análisis geoespacial, supervisión remota y detección de anomalías. Como sucede con los datos relacionales, los datos de streaming se pueden filtrar, agregar y preparar antes de moverlos a un receptor de salida. Apache Spark admite el [procesamiento de flujos de datos en tiempo real](/azure/architecture/data-guide/big-data/real-time-processing) mediante [Spark Streaming](https://spark.apache.org/streaming/).

### <a name="batch-processing"></a>Procesamiento por lotes

El [procesamiento por lotes](/azure/architecture/data-guide/big-data/batch-processing) es el procesamiento de macrodatos en reposo. Puede filtrar, agregar y preparar conjuntos de datos muy grandes mediante trabajos en paralelo de larga ejecución.

### <a name="machine-learning-through-mllib"></a>Aprendizaje automático a través de MLlib

El aprendizaje automático se usa para problemas analíticos avanzados. El equipo puede usar los datos existentes para prever o predecir comportamientos futuros, resultados y tendencias. La biblioteca de aprendizaje automático de Apache Spark, [MLlib](https://spark.apache.org/mllib/), contiene varios algoritmos y utilidades de aprendizaje automático.

### <a name="graph-processing-through-graphx"></a>Procesamiento de grafos a través de GraphX

Un grafo es una colección de nodos conectados por bordes. Es posible que use una base de datos de grafos si tiene datos jerárquicos o datos con relaciones interconectadas. Puede procesar estos datos mediante la API [GraphX](https://spark.apache.org/graphx/) de Apache Spark.

### <a name="sql-and-structured-data-processing-with-spark-sql"></a>Procesamiento de datos SQL y estructurados con Spark SQL

Si va a trabajar con datos estructurados (con formato), puede usar consultas SQL en la aplicación Spark mediante [Spark SQL](https://spark.apache.org/sql/).

## <a name="apache-spark-architecture"></a>Arquitectura de Apache Spark

Apache Spark, que usa la arquitectura de maestro y trabajo, tiene tres componentes principales: el controlador, los ejecutores y el administrador de clústeres.

![Arquitectura de Apache Spark](media/spark-architecture.png)

### <a name="driver"></a>Controlador

El controlador se compone del programa, como una aplicación de consola de C#, y una sesión de Spark. La sesión de Spark toma el programa y lo divide en tareas más pequeñas controladas por los ejecutores.

### <a name="executors"></a>Ejecutores

Cada ejecutor, o nodo de trabajo, recibe una tarea del controlador y la ejecuta. Los ejecutores residen en una entidad conocida como clúster.

### <a name="cluster-manager"></a>Administrador de clústeres

El administrador de clústeres se comunica con el controlador y los ejecutores para:

* Administrar la asignación de recursos
* Administrar la división de programas
* Administrar la ejecución de programas

## <a name="language-support"></a>Compatibilidad con idiomas

Apache Spark admite los lenguajes de programación siguientes:

* Scala
* Plantillas de
* Java
* SQL
* R
* Lenguajes .NET (C#/F#)

## <a name="spark-apis"></a>API de Spark

Apache Spark admite las API siguientes:

* [Spark Scala API](https://spark.apache.org/docs/2.2.0/api/scala/index.html)
* [Spark Java API](https://spark.apache.org/docs/2.2.0/api/java/index.html)
* [Spark Python API](https://spark.apache.org/docs/2.2.0/api/python/index.html)
* [Spark R API](https://spark.apache.org/docs/2.2.0/api/R/index.html)
* [Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), funciones integradas

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre cómo puede usar Apache Spark en la aplicación .NET. Con .NET para Apache Spark, los desarrolladores con experiencia de .NET y lógica de negocios pueden escribir consultas de macrodatos en C# y F#.
> [!div class="nextstepaction"]
> [¿Qué es .NET para Apache Spark?](what-is-apache-spark-dotnet.md)

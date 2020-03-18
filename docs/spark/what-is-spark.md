---
title: ¿Qué es Apache Spark?
description: Más información sobre Apache Spark y escenarios de macrodatos.
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: 653f355d09a045feabb3dee0f5737cb691cf2dc4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73458173"
---
# <a name="what-is-apache-spark"></a><span data-ttu-id="8e498-103">¿Qué es Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="8e498-103">What is Apache Spark?</span></span>

<span data-ttu-id="8e498-104">[Apache Spark](https://spark.apache.org/) es una plataforma de procesamiento paralelo de código abierto que admite el procesamiento en memoria para mejorar el rendimiento de las aplicaciones que analizan macrodatos.</span><span class="sxs-lookup"><span data-stu-id="8e498-104">[Apache Spark](https://spark.apache.org/) is an open-source parallel processing framework that supports in-memory processing to boost the performance of applications that analyze big data.</span></span> <span data-ttu-id="8e498-105">Las soluciones de macrodatos están diseñadas para controlar datos que son demasiado grandes o complejos para las bases de datos tradicionales.</span><span class="sxs-lookup"><span data-stu-id="8e498-105">Big data solutions are designed to handle data that is too large or complex for traditional databases.</span></span> <span data-ttu-id="8e498-106">Spark procesa grandes cantidades de datos en memoria, lo que es mucho más rápido que las alternativas basadas en disco.</span><span class="sxs-lookup"><span data-stu-id="8e498-106">Spark processes large amounts of data in memory, which is much faster than disk-based alternatives.</span></span>

## <a name="common-big-data-scenarios"></a><span data-ttu-id="8e498-107">Escenarios comunes de macrodatos</span><span class="sxs-lookup"><span data-stu-id="8e498-107">Common big data scenarios</span></span>

<span data-ttu-id="8e498-108">Es posible que considere la posibilidad de usar una arquitectura de macrodatos si tiene que almacenar y procesar grandes volúmenes de datos, transformar datos no estructurados o procesos de transmisión de datos.</span><span class="sxs-lookup"><span data-stu-id="8e498-108">You might consider a big data architecture if you need to store and process large volumes of data, transform unstructured data, or processes streaming data.</span></span> <span data-ttu-id="8e498-109">Spark es un motor de procesamiento distribuido de uso general que se puede usar para varios escenarios de macrodatos.</span><span class="sxs-lookup"><span data-stu-id="8e498-109">Spark is a general-purpose distributed processing engine that can be used for several big data scenarios.</span></span>

### <a name="extract-transform-and-load-etl"></a><span data-ttu-id="8e498-110">Extracción, transformación y carga de datos (ETL)</span><span class="sxs-lookup"><span data-stu-id="8e498-110">Extract, transform, and load (ETL)</span></span>

<span data-ttu-id="8e498-111">[Extracción, transformación y carga de datos (ETL)](/azure/architecture/data-guide/relational-data/etl) es el proceso de recopilación de datos de uno o varios orígenes, su modificación y el traslado a un nuevo almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="8e498-111">[Extract, transform, and load (ETL)](/azure/architecture/data-guide/relational-data/etl) is the process of collecting data from one or multiple sources, modifying the data, and moving the data to a new data store.</span></span> <span data-ttu-id="8e498-112">Existen varias maneras de transformar datos, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="8e498-112">There are several ways to transform data, including:</span></span>

* <span data-ttu-id="8e498-113">Filtros</span><span class="sxs-lookup"><span data-stu-id="8e498-113">Filtering</span></span>
* <span data-ttu-id="8e498-114">Ordenar</span><span class="sxs-lookup"><span data-stu-id="8e498-114">Sorting</span></span>
* <span data-ttu-id="8e498-115">Agregación</span><span class="sxs-lookup"><span data-stu-id="8e498-115">Aggregating</span></span>
* <span data-ttu-id="8e498-116">Combinación</span><span class="sxs-lookup"><span data-stu-id="8e498-116">Joining</span></span>
* <span data-ttu-id="8e498-117">Limpieza</span><span class="sxs-lookup"><span data-stu-id="8e498-117">Cleaning</span></span>
* <span data-ttu-id="8e498-118">Desduplicación</span><span class="sxs-lookup"><span data-stu-id="8e498-118">Deduplicating</span></span>
* <span data-ttu-id="8e498-119">Validating</span><span class="sxs-lookup"><span data-stu-id="8e498-119">Validating</span></span>

### <a name="real-time-data-stream-processing"></a><span data-ttu-id="8e498-120">Procesamiento de flujos de datos en tiempo real</span><span class="sxs-lookup"><span data-stu-id="8e498-120">Real-time data stream processing</span></span>

<span data-ttu-id="8e498-121">Los datos de streaming, o en tiempo real, son datos en movimiento.</span><span class="sxs-lookup"><span data-stu-id="8e498-121">Streaming, or real-time, data is data in motion.</span></span> <span data-ttu-id="8e498-122">La telemetría desde dispositivos de IoT, blogs y clickstream son ejemplos de datos de streaming.</span><span class="sxs-lookup"><span data-stu-id="8e498-122">Telemetry from IoT devices, weblogs, and clickstreams are all examples of streaming data.</span></span> <span data-ttu-id="8e498-123">Los datos en tiempo real se pueden procesar para proporcionar información útil, como análisis geoespacial, supervisión remota y detección de anomalías.</span><span class="sxs-lookup"><span data-stu-id="8e498-123">Real-time data can be processed to provide useful information, such as geospatial analysis, remote monitoring, and anomaly detection.</span></span> <span data-ttu-id="8e498-124">Como sucede con los datos relacionales, los datos de streaming se pueden filtrar, agregar y preparar antes de moverlos a un receptor de salida.</span><span class="sxs-lookup"><span data-stu-id="8e498-124">Just like relational data, you can filter, aggregate, and prepare streaming data before moving the data to an output sink.</span></span> <span data-ttu-id="8e498-125">Apache Spark admite el [procesamiento de flujos de datos en tiempo real](/azure/architecture/data-guide/big-data/real-time-processing) mediante [Spark Streaming](https://spark.apache.org/streaming/).</span><span class="sxs-lookup"><span data-stu-id="8e498-125">Apache Spark supports [real-time data stream processing](/azure/architecture/data-guide/big-data/real-time-processing) through [Spark Streaming](https://spark.apache.org/streaming/).</span></span>

### <a name="batch-processing"></a><span data-ttu-id="8e498-126">Procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="8e498-126">Batch processing</span></span>

<span data-ttu-id="8e498-127">El [procesamiento por lotes](/azure/architecture/data-guide/big-data/batch-processing) es el procesamiento de macrodatos en reposo.</span><span class="sxs-lookup"><span data-stu-id="8e498-127">[Batch processing](/azure/architecture/data-guide/big-data/batch-processing) is the processing of big data at rest.</span></span> <span data-ttu-id="8e498-128">Puede filtrar, agregar y preparar conjuntos de datos muy grandes mediante trabajos en paralelo de larga ejecución.</span><span class="sxs-lookup"><span data-stu-id="8e498-128">You can filter, aggregate, and prepare very large datasets using long-running jobs in parallel.</span></span>

### <a name="machine-learning-through-mllib"></a><span data-ttu-id="8e498-129">Aprendizaje automático a través de MLlib</span><span class="sxs-lookup"><span data-stu-id="8e498-129">Machine learning through MLlib</span></span>

<span data-ttu-id="8e498-130">El aprendizaje automático se usa para problemas analíticos avanzados.</span><span class="sxs-lookup"><span data-stu-id="8e498-130">Machine learning is used for advanced analytical problems.</span></span> <span data-ttu-id="8e498-131">El equipo puede usar los datos existentes para prever o predecir comportamientos futuros, resultados y tendencias.</span><span class="sxs-lookup"><span data-stu-id="8e498-131">Your computer can use existing data to forecast or predict future behaviors, outcomes, and trends.</span></span> <span data-ttu-id="8e498-132">La biblioteca de aprendizaje automático de Apache Spark, [MLlib](https://spark.apache.org/mllib/), contiene varios algoritmos y utilidades de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="8e498-132">Apache Spark's machine learning library, [MLlib](https://spark.apache.org/mllib/), contains several machine learning algorithms and utilities.</span></span>

### <a name="graph-processing-through-graphx"></a><span data-ttu-id="8e498-133">Procesamiento de grafos a través de GraphX</span><span class="sxs-lookup"><span data-stu-id="8e498-133">Graph processing through GraphX</span></span>

<span data-ttu-id="8e498-134">Un grafo es una colección de nodos conectados por bordes.</span><span class="sxs-lookup"><span data-stu-id="8e498-134">A graph is a collection of nodes connected by edges.</span></span> <span data-ttu-id="8e498-135">Es posible que use una base de datos de grafos si tiene datos jerárquicos o datos con relaciones interconectadas.</span><span class="sxs-lookup"><span data-stu-id="8e498-135">You might use a graph database if you have hierarchial data or data with interconnected relationships.</span></span> <span data-ttu-id="8e498-136">Puede procesar estos datos mediante la API [GraphX](https://spark.apache.org/graphx/) de Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="8e498-136">You can process this data using Apache Spark's [GraphX](https://spark.apache.org/graphx/) API.</span></span>

### <a name="sql-and-structured-data-processing-with-spark-sql"></a><span data-ttu-id="8e498-137">Procesamiento de datos SQL y estructurados con Spark SQL</span><span class="sxs-lookup"><span data-stu-id="8e498-137">SQL and structured data processing with Spark SQL</span></span>

<span data-ttu-id="8e498-138">Si va a trabajar con datos estructurados (con formato), puede usar consultas SQL en la aplicación Spark mediante [Spark SQL](https://spark.apache.org/sql/).</span><span class="sxs-lookup"><span data-stu-id="8e498-138">If you're working with structured (formatted) data, you can use SQL queries in your Spark application using [Spark SQL](https://spark.apache.org/sql/).</span></span>

## <a name="apache-spark-architecture"></a><span data-ttu-id="8e498-139">Arquitectura de Apache Spark</span><span class="sxs-lookup"><span data-stu-id="8e498-139">Apache Spark architecture</span></span>

<span data-ttu-id="8e498-140">Apache Spark, que usa la arquitectura de maestro y trabajo, tiene tres componentes principales: el controlador, los ejecutores y el administrador de clústeres.</span><span class="sxs-lookup"><span data-stu-id="8e498-140">Apache Spark, which uses the master/worker architecture, has three main components: the driver, executors, and cluster manager.</span></span>

![Arquitectura de Apache Spark](media/spark-architecture.png)

### <a name="driver"></a><span data-ttu-id="8e498-142">Controlador</span><span class="sxs-lookup"><span data-stu-id="8e498-142">Driver</span></span>

<span data-ttu-id="8e498-143">El controlador se compone del programa, como una aplicación de consola de C#, y una sesión de Spark.</span><span class="sxs-lookup"><span data-stu-id="8e498-143">The driver consists of your program, like a C# console app, and a Spark session.</span></span> <span data-ttu-id="8e498-144">La sesión de Spark toma el programa y lo divide en tareas más pequeñas controladas por los ejecutores.</span><span class="sxs-lookup"><span data-stu-id="8e498-144">The Spark session takes your program and divides it into smaller tasks that are handled by the executors.</span></span>

### <a name="executors"></a><span data-ttu-id="8e498-145">Ejecutores</span><span class="sxs-lookup"><span data-stu-id="8e498-145">Executors</span></span>

<span data-ttu-id="8e498-146">Cada ejecutor, o nodo de trabajo, recibe una tarea del controlador y la ejecuta.</span><span class="sxs-lookup"><span data-stu-id="8e498-146">Each executor, or worker node, receives a task from the driver and executes that task.</span></span> <span data-ttu-id="8e498-147">Los ejecutores residen en una entidad conocida como clúster.</span><span class="sxs-lookup"><span data-stu-id="8e498-147">The executors reside on an entity known as a cluster.</span></span>

### <a name="cluster-manager"></a><span data-ttu-id="8e498-148">Administrador de clústeres</span><span class="sxs-lookup"><span data-stu-id="8e498-148">Cluster manager</span></span>

<span data-ttu-id="8e498-149">El administrador de clústeres se comunica con el controlador y los ejecutores para:</span><span class="sxs-lookup"><span data-stu-id="8e498-149">The cluster manager communicates with both the driver and the executors to:</span></span>

* <span data-ttu-id="8e498-150">Administrar la asignación de recursos</span><span class="sxs-lookup"><span data-stu-id="8e498-150">Manage resource allocation</span></span>
* <span data-ttu-id="8e498-151">Administrar la división de programas</span><span class="sxs-lookup"><span data-stu-id="8e498-151">Manage program division</span></span>
* <span data-ttu-id="8e498-152">Administrar la ejecución de programas</span><span class="sxs-lookup"><span data-stu-id="8e498-152">Manage program execution</span></span>

## <a name="language-support"></a><span data-ttu-id="8e498-153">Compatibilidad con idiomas</span><span class="sxs-lookup"><span data-stu-id="8e498-153">Language support</span></span>

<span data-ttu-id="8e498-154">Apache Spark admite los lenguajes de programación siguientes:</span><span class="sxs-lookup"><span data-stu-id="8e498-154">Apache Spark supports the following programming languages:</span></span>

* <span data-ttu-id="8e498-155">Scala</span><span class="sxs-lookup"><span data-stu-id="8e498-155">Scala</span></span>
* <span data-ttu-id="8e498-156">Plantillas de</span><span class="sxs-lookup"><span data-stu-id="8e498-156">Python</span></span>
* <span data-ttu-id="8e498-157">Java</span><span class="sxs-lookup"><span data-stu-id="8e498-157">Java</span></span>
* <span data-ttu-id="8e498-158">SQL</span><span class="sxs-lookup"><span data-stu-id="8e498-158">SQL</span></span>
* <span data-ttu-id="8e498-159">R</span><span class="sxs-lookup"><span data-stu-id="8e498-159">R</span></span>
* <span data-ttu-id="8e498-160">.NET</span><span class="sxs-lookup"><span data-stu-id="8e498-160">.NET</span></span>

## <a name="spark-apis"></a><span data-ttu-id="8e498-161">API de Spark</span><span class="sxs-lookup"><span data-stu-id="8e498-161">Spark APIs</span></span>

<span data-ttu-id="8e498-162">Apache Spark admite las API siguientes:</span><span class="sxs-lookup"><span data-stu-id="8e498-162">Apache Spark supports the following APIs:</span></span>

* [<span data-ttu-id="8e498-163">Spark Scala API</span><span class="sxs-lookup"><span data-stu-id="8e498-163">Spark Scala API</span></span>](https://spark.apache.org/docs/2.2.0/api/scala/index.html)
* [<span data-ttu-id="8e498-164">Spark Java API</span><span class="sxs-lookup"><span data-stu-id="8e498-164">Spark Java API</span></span>](https://spark.apache.org/docs/2.2.0/api/java/index.html)
* [<span data-ttu-id="8e498-165">Spark Python API</span><span class="sxs-lookup"><span data-stu-id="8e498-165">Spark Python API</span></span>](https://spark.apache.org/docs/2.2.0/api/python/index.html)
* [<span data-ttu-id="8e498-166">Spark R API</span><span class="sxs-lookup"><span data-stu-id="8e498-166">Spark R API</span></span>](https://spark.apache.org/docs/2.2.0/api/R/index.html)
* <span data-ttu-id="8e498-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), funciones integradas</span><span class="sxs-lookup"><span data-stu-id="8e498-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), built-in functions</span></span>

## <a name="next-steps"></a><span data-ttu-id="8e498-168">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8e498-168">Next steps</span></span>

<span data-ttu-id="8e498-169">Obtenga información sobre cómo puede usar Apache Spark en la aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="8e498-169">Learn how you can use Apache Spark in your .NET application.</span></span> <span data-ttu-id="8e498-170">Con .NET para Apache Spark, los desarrolladores con experiencia de .NET y lógica de negocios pueden escribir consultas de macrodatos en C# y F#.</span><span class="sxs-lookup"><span data-stu-id="8e498-170">With .NET for Apache Spark, developers with .NET experience and business logic can write big data queries in C# and F#.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="8e498-171">¿Qué es .NET para Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="8e498-171">What is .NET for Apache Spark</span></span>](what-is-apache-spark-dotnet.md)

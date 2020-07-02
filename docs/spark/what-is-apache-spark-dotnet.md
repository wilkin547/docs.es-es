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
# <a name="what-is-net-for-apache-spark"></a><span data-ttu-id="c657c-103">¿Qué es .NET para Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="c657c-103">What is .NET for Apache Spark?</span></span>

<span data-ttu-id="c657c-104">[Apache Spark](what-is-spark.md) es un motor de procesamiento distribuido de uso general para realizar análisis de grandes conjuntos de datos (normalmente, terabytes o petabytes de datos).</span><span class="sxs-lookup"><span data-stu-id="c657c-104">[Apache Spark](what-is-spark.md) is a general-purpose distributed processing engine for analytics over large data sets - typically terabytes or petabytes of data.</span></span> <span data-ttu-id="c657c-105">Con .NET para Apache Spark, la compatibilidad de .NET gratuita, de código abierto y multiplataforma para el conocido marco de análisis de macrodatos de código abierto, ahora puede agregar la capacidad de Apache Spark a las aplicaciones de macrodatos con lenguajes que ya conoce.</span><span class="sxs-lookup"><span data-stu-id="c657c-105">With .NET for Apache Spark, the free, open-source, and cross-platform .NET Support for the popular open-source big data analytics framework, you can now add the power of Apache Spark to your big data applications using languages you already know.</span></span>

[!INCLUDE [spark-preview-note](../../includes/spark-preview-note.md)]

## <a name="why-choose-net-for-apache-spark"></a><span data-ttu-id="c657c-106">¿Por qué elegir .NET para Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="c657c-106">Why choose .NET for Apache Spark?</span></span>

<span data-ttu-id="c657c-107">.NET para Apache Spark permite a los desarrolladores con experiencia en .NET o en bases de código participar en el mundo del análisis de macrodatos.</span><span class="sxs-lookup"><span data-stu-id="c657c-107">.NET for Apache Spark empowers developers with .NET experience or code bases to participate in the world of big data analytics.</span></span> <span data-ttu-id="c657c-108">.NET para Apache Spark proporciona API de alto rendimiento para usar Spark desde C# y F#.</span><span class="sxs-lookup"><span data-stu-id="c657c-108">.NET for Apache Spark provides high performance APIs for using Spark from C# and F#.</span></span> <span data-ttu-id="c657c-109">Con C# y F#, puede tener acceso a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c657c-109">With C# and F#, you can access:</span></span>

* <span data-ttu-id="c657c-110">DataFrame y SparkSQL para trabajar con datos estructurados.</span><span class="sxs-lookup"><span data-stu-id="c657c-110">DataFrame and SparkSQL for working with structured data.</span></span>
* <span data-ttu-id="c657c-111">Spark Structured Streaming, para trabajar con datos de streaming.</span><span class="sxs-lookup"><span data-stu-id="c657c-111">Spark Structured Streaming for working with streaming data.</span></span>
* <span data-ttu-id="c657c-112">Spark SQL, para escribir consultas con sintaxis SQL.</span><span class="sxs-lookup"><span data-stu-id="c657c-112">Spark SQL for writing queries with SQL syntax.</span></span>
* <span data-ttu-id="c657c-113">Integración de aprendizaje automático para acelerar el entrenamiento y la predicción (es decir, uso de .NET para Apache Spark junto con [ML.NET](https://dot.net/ml)).</span><span class="sxs-lookup"><span data-stu-id="c657c-113">Machine learning integration for faster training and prediction (that is, use .NET for Apache Spark alongside [ML.NET](https://dot.net/ml)).</span></span>

<span data-ttu-id="c657c-114">.NET for Apache Spark es compatible con .NET Standard, una especificación formal de las API de .NET que son comunes entre las implementaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="c657c-114">.NET for Apache Spark is compliant with .NET Standard, a formal specification of .NET APIs that are common across .NET implementations.</span></span> <span data-ttu-id="c657c-115">Esto significa que puede usar .NET para Apache Spark en cualquier lugar en el que escriba código de .NET, de modo que podrá reutilizar todo el conocimiento, los conocimientos, el código y las bibliotecas que ya posee como desarrollador de .NET.</span><span class="sxs-lookup"><span data-stu-id="c657c-115">This means you can use .NET for Apache Spark anywhere you write .NET code allowing you to reuse all the knowledge, skills, code, and libraries you already have as a .NET developer.</span></span>

<span data-ttu-id="c657c-116">.NET para Apache Spark se ejecuta en Windows, Linux y macOS con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c657c-116">.NET for Apache Spark runs on Windows, Linux, and macOS using .NET Core.</span></span> <span data-ttu-id="c657c-117">También se ejecuta en Windows con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c657c-117">It also runs on Windows using .NET Framework.</span></span> <span data-ttu-id="c657c-118">Puede implementar las aplicaciones en todos los principales proveedores de servicios en la nube, como Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks y Databricks on AWS.</span><span class="sxs-lookup"><span data-stu-id="c657c-118">You can deploy your applications to all major cloud providers including Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks, and Databricks on AWS.</span></span>

## <a name="net-for-apache-spark-architecture"></a><span data-ttu-id="c657c-119">.NET para arquitectura de Apache Spark</span><span class="sxs-lookup"><span data-stu-id="c657c-119">.NET for Apache Spark architecture</span></span>

<span data-ttu-id="c657c-120">El enlace del lenguaje C#/F# a Spark se escribe en una capa nueva de interoperabilidad de Spark que ofrece una extensibilidad más sencilla.</span><span class="sxs-lookup"><span data-stu-id="c657c-120">The C#/ F# language binding to Spark is written on a new Spark interop layer which offers easier extensibility.</span></span> <span data-ttu-id="c657c-121">Esta nueva capa de interoperabilidad de Spark se ha escrito usando los procedimientos recomendado para la extensión de lenguaje y optimiza la interoperabilidad y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c657c-121">This new layer of Spark interop was written using the best practices for language extension and optimizes for interop and performance.</span></span> <span data-ttu-id="c657c-122">A largo plazo, esta extensibilidad se puede usar para agregar compatibilidad con otros lenguajes en Spark.</span><span class="sxs-lookup"><span data-stu-id="c657c-122">Long term, this extensibility can be used for adding support for other languages in Spark.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c657c-123">![.NET para arquitectura de Apache Spark](media/dotnet-spark-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="c657c-123">![.NET for Apache Spark architecture](media/dotnet-spark-architecture.png)</span></span>

<span data-ttu-id="c657c-124">Puede obtener información sobre la compatibilidad de interoperabilidad con las extensiones de lenguaje en Spark en [la propuesta](https://issues.apache.org/jira/browse/SPARK-26257).</span><span class="sxs-lookup"><span data-stu-id="c657c-124">You can learn about interop support for Spark language extensions from [the proposal](https://issues.apache.org/jira/browse/SPARK-26257).</span></span>

## <a name="net-for-apache-spark-performance"></a><span data-ttu-id="c657c-125">.NET para rendimiento de Apache Spark</span><span class="sxs-lookup"><span data-stu-id="c657c-125">.NET for Apache Spark performance</span></span>

<span data-ttu-id="c657c-126">Cuando se comparan con Python y Scala mediante el [banco de pruebas TPC-H](http://www.tpc.org/tpch/), .NET para Apache Spark funciona correctamente en la mayoría de los casos, y es dos veces más rápido que Python cuando el rendimiento de la función definida por el usuario es crítico.</span><span class="sxs-lookup"><span data-stu-id="c657c-126">When compared against Python and Scala using the [TPC-H benchmark](http://www.tpc.org/tpch/), .NET for Apache Spark performs well in most cases and is 2x faster than Python when user-defined function performance is critical.</span></span> <span data-ttu-id="c657c-127">Existe un esfuerzo continuo por mejorar y realizar pruebas comparativas del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c657c-127">There is an ongoing effort to improve and benchmark performance.</span></span>

<span data-ttu-id="c657c-128">Para realizar su propio banco de pruebas, consulte los bancos de pruebas disponibles en el [GitHub de .NET para Apache Spark](https://github.com/dotnet/spark/tree/master/benchmark).</span><span class="sxs-lookup"><span data-stu-id="c657c-128">To do your own benchmarking, see the benchmarks available on the [.NET for Apache Spark GitHub](https://github.com/dotnet/spark/tree/master/benchmark).</span></span>

## <a name="net-for-apache-spark-roadmap"></a><span data-ttu-id="c657c-129">Guía de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="c657c-129">.NET for Apache Spark roadmap</span></span>

<span data-ttu-id="c657c-130">Obtenga información sobre los planes a corto y a largo plazo en la [Guía de .NET para Apache Spark](https://github.com/dotnet/spark/blob/master/ROADMAP.md).</span><span class="sxs-lookup"><span data-stu-id="c657c-130">Learn about short term and long term plans from the official [.NET for Apache Spark roadmap](https://github.com/dotnet/spark/blob/master/ROADMAP.md).</span></span>

## <a name="net-foundation"></a><span data-ttu-id="c657c-131">.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="c657c-131">.NET Foundation</span></span>

<span data-ttu-id="c657c-132">El proyecto de .NET para Apache Spark forma parte de [.NET Foundation](https://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="c657c-132">The .NET for Apache Spark project is part of the [.NET Foundation](https://www.dotnetfoundation.org/).</span></span>

## <a name="contributions"></a><span data-ttu-id="c657c-133">Contribuciones</span><span class="sxs-lookup"><span data-stu-id="c657c-133">Contributions</span></span>

<span data-ttu-id="c657c-134">El equipo de .NET para Apache Spark anima a que se aporten contribuciones, en forma tanto de incidencias de GitHub como de solicitudes de incorporación de cambios.</span><span class="sxs-lookup"><span data-stu-id="c657c-134">The .NET for Apache Spark team encourages contributions, both GitHub issues and pull requests.</span></span> <span data-ttu-id="c657c-135">En primer lugar, busque [una incidencia existente](https://github.com/dotnet/spark/issues).</span><span class="sxs-lookup"><span data-stu-id="c657c-135">First, look for an [existing issue](https://github.com/dotnet/spark/issues).</span></span> <span data-ttu-id="c657c-136">Si no encuentra una incidencia existente, [abra una nueva](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span><span class="sxs-lookup"><span data-stu-id="c657c-136">If you can't find an existing issue, [open a new issue](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c657c-137">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c657c-137">Next steps</span></span>

<span data-ttu-id="c657c-138">Pruebe .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="c657c-138">Try .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="c657c-139">Tutorial: Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="c657c-139">Tutorial: Get started with .NET for Apache Spark</span></span>](./tutorials/get-started.md)

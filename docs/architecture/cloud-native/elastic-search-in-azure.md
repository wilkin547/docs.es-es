---
title: Elasticsearch en aplicaciones nativas de la nube
description: Obtenga información sobre cómo agregar capacidades de Elastic Search a aplicaciones nativas de la nube.
author: robvet
ms.date: 03/02/2020
ms.openlocfilehash: da6b9402cf266f5a298b05cf837805b2377bc75a
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805566"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="47dc5-103">Elasticsearch en una aplicación nativa de la nube</span><span class="sxs-lookup"><span data-stu-id="47dc5-103">Elasticsearch in a cloud-native app</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="47dc5-104">Elasticsearch es un sistema de búsqueda y análisis distribuido que permite capacidades de búsqueda complejas en diversos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="47dc5-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="47dc5-105">Es de código abierto y ampliamente popular.</span><span class="sxs-lookup"><span data-stu-id="47dc5-105">It's open source and widely popular.</span></span> <span data-ttu-id="47dc5-106">Tenga en cuenta cómo las siguientes empresas integran Elasticsearch en su aplicación:</span><span class="sxs-lookup"><span data-stu-id="47dc5-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="47dc5-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) para texto completo e incremental (búsqueda a medida que escribes) búsqueda.</span><span class="sxs-lookup"><span data-stu-id="47dc5-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="47dc5-108">[GitHub](https://www.elastic.co/customers/github) para indexar y exponer más de 8 millones de repositorios de código.</span><span class="sxs-lookup"><span data-stu-id="47dc5-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="47dc5-109">[Docker](https://www.elastic.co/customers/docker) para hacer que su biblioteca de contenedores sea detectable.</span><span class="sxs-lookup"><span data-stu-id="47dc5-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="47dc5-110">Elasticsearch se basa en el motor de búsqueda de texto completo [Apache Lucene.](https://lucene.apache.org/core/)</span><span class="sxs-lookup"><span data-stu-id="47dc5-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="47dc5-111">Lucene proporciona indización y consulta de documentos de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="47dc5-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="47dc5-112">Indiza los datos con un esquema de indexación invertido: en lugar de asignar páginas a palabras clave, asigna palabras clave a páginas como un glosario al final de un libro.</span><span class="sxs-lookup"><span data-stu-id="47dc5-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="47dc5-113">Lucene tiene potentes capacidades de sintaxis de consulta y puede consultar datos mediante:</span><span class="sxs-lookup"><span data-stu-id="47dc5-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="47dc5-114">Término (una palabra completa)</span><span class="sxs-lookup"><span data-stu-id="47dc5-114">Term (a full word)</span></span>
- <span data-ttu-id="47dc5-115">Prefijo (comienza con word)</span><span class="sxs-lookup"><span data-stu-id="47dc5-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="47dc5-116">Comodín (usando filtros "\*" o "?"</span><span class="sxs-lookup"><span data-stu-id="47dc5-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="47dc5-117">Frase (una secuencia de texto en un documento)</span><span class="sxs-lookup"><span data-stu-id="47dc5-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="47dc5-118">Valor booleano (búsquedas complejas que combinan consultas)</span><span class="sxs-lookup"><span data-stu-id="47dc5-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="47dc5-119">Aunque Lucene proporciona fontanería de bajo nivel para la búsqueda, Elasticsearch proporciona el servidor que se encuentra en la parte superior de Lucene.</span><span class="sxs-lookup"><span data-stu-id="47dc5-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="47dc5-120">Elasticsearch añade funcionalidad de nivel superior para simplificar el trabajo de Lucene, incluida una API RESTful para acceder a la funcionalidad de indexación y búsqueda de Lucene.</span><span class="sxs-lookup"><span data-stu-id="47dc5-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene's indexing and searching functionality.</span></span> <span data-ttu-id="47dc5-121">También proporciona una infraestructura distribuida capaz de escalabilidad masiva, tolerancia a errores y alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="47dc5-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="47dc5-122">Para aplicaciones nativas de la nube más grandes con requisitos de búsqueda complejos, Elasticsearch está disponible como servicio administrado en Azure.</span><span class="sxs-lookup"><span data-stu-id="47dc5-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="47dc5-123">Microsoft Azure Marketplace cuenta con plantillas preconfiguradas que los desarrolladores pueden usar para implementar un clúster de Elasticsearch en Azure.</span><span class="sxs-lookup"><span data-stu-id="47dc5-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="47dc5-124">Desde Microsoft Azure Marketplace, los desarrolladores pueden usar plantillas preconfiguradas creadas para implementar rápidamente un clúster de Elasticsearch en Azure.</span><span class="sxs-lookup"><span data-stu-id="47dc5-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="47dc5-125">Con la oferta administrada por Azure, puede implementar hasta 50 nodos de datos, 20 nodos de coordinación y tres nodos maestros dedicados.</span><span class="sxs-lookup"><span data-stu-id="47dc5-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="47dc5-126">Resumen</span><span class="sxs-lookup"><span data-stu-id="47dc5-126">Summary</span></span>

<span data-ttu-id="47dc5-127">En este capítulo se presenta una visión detallada de los datos en sistemas nativos de la nube.</span><span class="sxs-lookup"><span data-stu-id="47dc5-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="47dc5-128">Comenzamos contrastando el almacenamiento de datos en aplicaciones monolíticas con patrones de almacenamiento de datos en sistemas nativos de la nube.</span><span class="sxs-lookup"><span data-stu-id="47dc5-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="47dc5-129">Examinamos los patrones de datos implementados en sistemas nativos de la nube, incluidas las consultas entre servicios, las transacciones distribuidas y los patrones para tratar con sistemas de gran volumen.</span><span class="sxs-lookup"><span data-stu-id="47dc5-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="47dc5-130">Contrastamos SQL con datos NoSQL.</span><span class="sxs-lookup"><span data-stu-id="47dc5-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="47dc5-131">Examinamos las opciones de almacenamiento de datos disponibles en Azure que incluyen opciones centradas en Microsoft y de código abierto.</span><span class="sxs-lookup"><span data-stu-id="47dc5-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="47dc5-132">Por último, analizamos el almacenamiento en caché y Elasticsearch en una aplicación nativa de la nube.</span><span class="sxs-lookup"><span data-stu-id="47dc5-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="47dc5-133">Referencias</span><span class="sxs-lookup"><span data-stu-id="47dc5-133">References</span></span>

- [<span data-ttu-id="47dc5-134">Patrón Command and Query Responsibility Segregation (CQRS).</span><span class="sxs-lookup"><span data-stu-id="47dc5-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="47dc5-135">Patrón Event Sourcing</span><span class="sxs-lookup"><span data-stu-id="47dc5-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="47dc5-136">¿Por qué RDBMS Partition Tolerant en el teorema CAP y por qué está disponible?</span><span class="sxs-lookup"><span data-stu-id="47dc5-136">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="47dc5-137">Vista materializada</span><span class="sxs-lookup"><span data-stu-id="47dc5-137">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="47dc5-138">Todo lo que realmente necesita saber sobre bases de datos de código abierto</span><span class="sxs-lookup"><span data-stu-id="47dc5-138">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="47dc5-139">Patrón de transacción de compensación</span><span class="sxs-lookup"><span data-stu-id="47dc5-139">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="47dc5-140">Patrón Saga</span><span class="sxs-lookup"><span data-stu-id="47dc5-140">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="47dc5-141">Patrones de Saga Cómo implementar transacciones empresariales mediante microservicios</span><span class="sxs-lookup"><span data-stu-id="47dc5-141">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="47dc5-142">Patrón de transacción de compensación</span><span class="sxs-lookup"><span data-stu-id="47dc5-142">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="47dc5-143">Ponerse detrás de la bola 9: Niveles de consistencia de Cosmos DB explicados</span><span class="sxs-lookup"><span data-stu-id="47dc5-143">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="47dc5-144">Explorar los diferentes tipos de bases de datos NoSQL Parte II</span><span class="sxs-lookup"><span data-stu-id="47dc5-144">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="47dc5-145">En bases de datos RDBMS, NoSQL y NewSQL. Entrevista con John Ryan</span><span class="sxs-lookup"><span data-stu-id="47dc5-145">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="47dc5-146">SQL vs NoSQL vs NewSQL: La comparación completa</span><span class="sxs-lookup"><span data-stu-id="47dc5-146">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="47dc5-147">DASH: Cuatro propiedades de las bases de datos nativas de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="47dc5-147">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="47dc5-148">CockroachDB</span><span class="sxs-lookup"><span data-stu-id="47dc5-148">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="47dc5-149">TiDB</span><span class="sxs-lookup"><span data-stu-id="47dc5-149">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="47dc5-150">YugabyteDB</span><span class="sxs-lookup"><span data-stu-id="47dc5-150">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="47dc5-151">Vitess</span><span class="sxs-lookup"><span data-stu-id="47dc5-151">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="47dc5-152">Elasticsearch: The Definitive Guide (Elasticsearch: la guía definitiva).</span><span class="sxs-lookup"><span data-stu-id="47dc5-152">Elasticsearch: The Definitive Guide</span></span>](http://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="47dc5-153">Introducción a Apache Lucene</span><span class="sxs-lookup"><span data-stu-id="47dc5-153">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="47dc5-154">[Anterior](azure-caching.md)
>[Siguiente](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="47dc5-154">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->

---
title: Elasticsearch en aplicaciones nativas de la nube
description: Obtenga información sobre cómo agregar funcionalidades de búsqueda elástica a aplicaciones nativas de la nube.
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: fa46f3387eecb3fccd63fdea10c11e92923ae862
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155385"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="e4e7f-103">Elasticsearch en una aplicación nativa en la nube</span><span class="sxs-lookup"><span data-stu-id="e4e7f-103">Elasticsearch in a cloud-native app</span></span>

<span data-ttu-id="e4e7f-104">Elasticsearch es un sistema de búsqueda y análisis distribuido que permite capacidades de búsqueda complejas a través de diversos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="e4e7f-105">Es de código abierto y es muy popular.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-105">It's open source and widely popular.</span></span> <span data-ttu-id="e4e7f-106">Tenga en cuenta cómo las siguientes empresas integran Elasticsearch en su aplicación:</span><span class="sxs-lookup"><span data-stu-id="e4e7f-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="e4e7f-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) para búsqueda de texto completo e incremental (búsqueda a medida que escribe).</span><span class="sxs-lookup"><span data-stu-id="e4e7f-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="e4e7f-108">[GitHub](https://www.elastic.co/customers/github) para indexar y exponer en repositorios de código de 8 millones.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="e4e7f-109">[Docker](https://www.elastic.co/customers/docker) para que su biblioteca de contenedores sea reconocible.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="e4e7f-110">Elasticsearch se basa en el motor de búsqueda de texto completo de [Apache Lucene](https://lucene.apache.org/core/) .</span><span class="sxs-lookup"><span data-stu-id="e4e7f-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="e4e7f-111">Lucene proporciona indexación y consulta de documentos de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="e4e7f-112">Indexa los datos con un esquema de indexación invertido, en lugar de asignar páginas a palabras clave, asigna palabras clave a páginas como un glosario al final de un libro.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="e4e7f-113">Lucene tiene capacidades de sintaxis de consulta eficaces y puede consultar los datos mediante:</span><span class="sxs-lookup"><span data-stu-id="e4e7f-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="e4e7f-114">Término (palabra completa)</span><span class="sxs-lookup"><span data-stu-id="e4e7f-114">Term (a full word)</span></span>
- <span data-ttu-id="e4e7f-115">Prefix (Start-with Word)</span><span class="sxs-lookup"><span data-stu-id="e4e7f-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="e4e7f-116">Carácter comodín (con \* filtros "" o "?")</span><span class="sxs-lookup"><span data-stu-id="e4e7f-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="e4e7f-117">Frase (una secuencia de texto en un documento)</span><span class="sxs-lookup"><span data-stu-id="e4e7f-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="e4e7f-118">Valor booleano (búsquedas complejas combinando consultas)</span><span class="sxs-lookup"><span data-stu-id="e4e7f-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="e4e7f-119">Aunque Lucene proporciona una infraestructura de bajo nivel para la búsqueda, Elasticsearch proporciona el servidor que se encuentra en Lucene.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="e4e7f-120">Elasticsearch agrega funcionalidad de nivel superior para simplificar el funcionamiento de Lucene, incluida una API de RESTful para acceder a la funcionalidad de indexación y búsqueda de Lucene.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene's indexing and searching functionality.</span></span> <span data-ttu-id="e4e7f-121">También proporciona una infraestructura distribuida capaz de escalabilidad masiva, tolerancia a errores y alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="e4e7f-122">En el caso de las aplicaciones nativas de nube más grandes con requisitos de búsqueda complejos, Elasticsearch está disponible como servicio administrado en Azure.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="e4e7f-123">El Microsoft Azure Marketplace incluye plantillas preconfiguradas que los desarrolladores pueden usar para implementar un clúster de Elasticsearch en Azure.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="e4e7f-124">En el Microsoft Azure Marketplace, los desarrolladores pueden usar plantillas preconfiguradas compiladas para implementar rápidamente un clúster de Elasticsearch en Azure.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="e4e7f-125">Mediante la oferta administrada por Azure, puede implementar hasta 50 nodos de datos, 20 nodos de coordinación y tres nodos maestros dedicados.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="e4e7f-126">Resumen</span><span class="sxs-lookup"><span data-stu-id="e4e7f-126">Summary</span></span>

<span data-ttu-id="e4e7f-127">En este capítulo se describe detalladamente los datos de los sistemas nativos en la nube.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="e4e7f-128">Empezamos por contrastar el almacenamiento de datos en aplicaciones monolíticas con patrones de almacenamiento de datos en sistemas nativos en la nube.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="e4e7f-129">Analizamos los patrones de datos implementados en sistemas nativos en la nube, incluidas consultas entre servicios, transacciones distribuidas y patrones para tratar con sistemas de gran volumen.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="e4e7f-130">Contrastamos SQL con los datos NoSQL.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="e4e7f-131">Analizamos las opciones de almacenamiento de datos disponibles en Azure que incluyen opciones de código abierto y centrado en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="e4e7f-132">Por último, analizamos el almacenamiento en caché y Elasticsearch en una aplicación nativa en la nube.</span><span class="sxs-lookup"><span data-stu-id="e4e7f-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="e4e7f-133">Referencias</span><span class="sxs-lookup"><span data-stu-id="e4e7f-133">References</span></span>

- [<span data-ttu-id="e4e7f-134">Patrón Command and Query Responsibility Segregation (CQRS).</span><span class="sxs-lookup"><span data-stu-id="e4e7f-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="e4e7f-135">Patrón Event Sourcing</span><span class="sxs-lookup"><span data-stu-id="e4e7f-135">Event Sourcing pattern</span></span>](/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="e4e7f-136">¿Por qué no es tolerante a las particiones de RDBMS en CAP teorema y por qué está disponible?</span><span class="sxs-lookup"><span data-stu-id="e4e7f-136">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="e4e7f-137">Materialized View</span><span class="sxs-lookup"><span data-stu-id="e4e7f-137">Materialized View</span></span>](/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="e4e7f-138">Todo lo que realmente necesita saber sobre las bases de datos de código abierto</span><span class="sxs-lookup"><span data-stu-id="e4e7f-138">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="e4e7f-139">Patrón de transacción de compensación</span><span class="sxs-lookup"><span data-stu-id="e4e7f-139">Compensating Transaction pattern</span></span>](/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="e4e7f-140">Patrón saga</span><span class="sxs-lookup"><span data-stu-id="e4e7f-140">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="e4e7f-141">Patrones de saga | Cómo implementar transacciones comerciales con microservicios</span><span class="sxs-lookup"><span data-stu-id="e4e7f-141">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="e4e7f-142">Patrón de transacción de compensación</span><span class="sxs-lookup"><span data-stu-id="e4e7f-142">Compensating Transaction pattern</span></span>](/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="e4e7f-143">Una vez que se encuentra en la sección 9: Cosmos DB niveles de coherencia explicados</span><span class="sxs-lookup"><span data-stu-id="e4e7f-143">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="e4e7f-144">Exploración de los diferentes tipos de bases de datos NoSQL, parte II</span><span class="sxs-lookup"><span data-stu-id="e4e7f-144">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="e4e7f-145">En las bases de datos de RDBMS, NoSQL y NewSQL. Entrevista con John Ryan</span><span class="sxs-lookup"><span data-stu-id="e4e7f-145">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="e4e7f-146">SQL vs NoSQL vs NewSQL: comparación completa</span><span class="sxs-lookup"><span data-stu-id="e4e7f-146">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="e4e7f-147">DASH: cuatro propiedades de Kubernetes: bases de datos nativas</span><span class="sxs-lookup"><span data-stu-id="e4e7f-147">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="e4e7f-148">CockroachDB</span><span class="sxs-lookup"><span data-stu-id="e4e7f-148">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="e4e7f-149">TiDB</span><span class="sxs-lookup"><span data-stu-id="e4e7f-149">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="e4e7f-150">YugabyteDB</span><span class="sxs-lookup"><span data-stu-id="e4e7f-150">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="e4e7f-151">Vitess</span><span class="sxs-lookup"><span data-stu-id="e4e7f-151">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="e4e7f-152">Elasticsearch: The Definitive Guide (Elasticsearch: la guía definitiva).</span><span class="sxs-lookup"><span data-stu-id="e4e7f-152">Elasticsearch: The Definitive Guide</span></span>](https://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="e4e7f-153">Introducción a Apache Lucene</span><span class="sxs-lookup"><span data-stu-id="e4e7f-153">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="e4e7f-154">[Anterior](azure-caching.md)
>[Siguiente](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="e4e7f-154">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->

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
# <a name="elasticsearch-in-a-cloud-native-app"></a>Elasticsearch en una aplicación nativa en la nube

Elasticsearch es un sistema de búsqueda y análisis distribuido que permite capacidades de búsqueda complejas a través de diversos tipos de datos. Es de código abierto y es muy popular. Tenga en cuenta cómo las siguientes empresas integran Elasticsearch en su aplicación:

- [Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) para búsqueda de texto completo e incremental (búsqueda a medida que escribe).
- [GitHub](https://www.elastic.co/customers/github) para indexar y exponer en repositorios de código de 8 millones.  
- [Docker](https://www.elastic.co/customers/docker) para que su biblioteca de contenedores sea reconocible.

Elasticsearch se basa en el motor de búsqueda de texto completo de [Apache Lucene](https://lucene.apache.org/core/) . Lucene proporciona indexación y consulta de documentos de alto rendimiento. Indexa los datos con un esquema de indexación invertido, en lugar de asignar páginas a palabras clave, asigna palabras clave a páginas como un glosario al final de un libro. Lucene tiene capacidades de sintaxis de consulta eficaces y puede consultar los datos mediante:

- Término (palabra completa)
- Prefix (Start-with Word)
- Carácter comodín (con \* filtros "" o "?")
- Frase (una secuencia de texto en un documento)
- Valor booleano (búsquedas complejas combinando consultas)

Aunque Lucene proporciona una infraestructura de bajo nivel para la búsqueda, Elasticsearch proporciona el servidor que se encuentra en Lucene. Elasticsearch agrega funcionalidad de nivel superior para simplificar el funcionamiento de Lucene, incluida una API de RESTful para acceder a la funcionalidad de indexación y búsqueda de Lucene. También proporciona una infraestructura distribuida capaz de escalabilidad masiva, tolerancia a errores y alta disponibilidad.

En el caso de las aplicaciones nativas de nube más grandes con requisitos de búsqueda complejos, Elasticsearch está disponible como servicio administrado en Azure. El Microsoft Azure Marketplace incluye plantillas preconfiguradas que los desarrolladores pueden usar para implementar un clúster de Elasticsearch en Azure.

En el Microsoft Azure Marketplace, los desarrolladores pueden usar plantillas preconfiguradas compiladas para implementar rápidamente un clúster de Elasticsearch en Azure. Mediante la oferta administrada por Azure, puede implementar hasta 50 nodos de datos, 20 nodos de coordinación y tres nodos maestros dedicados.

## <a name="summary"></a>Resumen

En este capítulo se describe detalladamente los datos de los sistemas nativos en la nube. Empezamos por contrastar el almacenamiento de datos en aplicaciones monolíticas con patrones de almacenamiento de datos en sistemas nativos en la nube. Analizamos los patrones de datos implementados en sistemas nativos en la nube, incluidas consultas entre servicios, transacciones distribuidas y patrones para tratar con sistemas de gran volumen. Contrastamos SQL con los datos NoSQL. Analizamos las opciones de almacenamiento de datos disponibles en Azure que incluyen opciones de código abierto y centrado en Microsoft. Por último, analizamos el almacenamiento en caché y Elasticsearch en una aplicación nativa en la nube.

### <a name="references"></a>Referencias

- [Patrón Command and Query Responsibility Segregation (CQRS).](/azure/architecture/patterns/cqrs)

- [Patrón Event Sourcing](/azure/architecture/patterns/event-sourcing)

- [¿Por qué no es tolerante a las particiones de RDBMS en CAP teorema y por qué está disponible?](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [Materialized View](/azure/architecture/patterns/materialized-view)

- [Todo lo que realmente necesita saber sobre las bases de datos de código abierto](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [Patrón de transacción de compensación](/azure/architecture/patterns/compensating-transaction)

- [Patrón saga](https://microservices.io/patterns/data/saga.html)

- [Patrones de saga | Cómo implementar transacciones comerciales con microservicios](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [Patrón de transacción de compensación](/azure/architecture/patterns/compensating-transaction)

- [Una vez que se encuentra en la sección 9: Cosmos DB niveles de coherencia explicados](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [Exploración de los diferentes tipos de bases de datos NoSQL, parte II](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [En las bases de datos de RDBMS, NoSQL y NewSQL. Entrevista con John Ryan](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [SQL vs NoSQL vs NewSQL: comparación completa](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [DASH: cuatro propiedades de Kubernetes: bases de datos nativas](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [CockroachDB](https://www.cockroachlabs.com/)

- [TiDB](https://pingcap.com/en/)

- [YugabyteDB](https://www.yugabyte.com/)

- [Vitess](https://vitess.io/)

- [Elasticsearch: The Definitive Guide (Elasticsearch: la guía definitiva).](https://shop.oreilly.com/product/0636920028505.do)
  
- [Introducción a Apache Lucene](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
>[Anterior](azure-caching.md)
>[Siguiente](resiliency.md) <!-- Next Chapter -->

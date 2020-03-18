---
title: Elasticsearch en aplicaciones nativas de la nube
description: Obtenga información sobre cómo agregar capacidades de Elastic Search a aplicaciones nativas de la nube.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 1bce255b6315006b11e0b6ac77040300f67ed984
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141294"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a>Elasticsearch en una aplicación nativa de la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Elasticsearch es un sistema de búsqueda y análisis distribuido que permite capacidades de búsqueda complejas en diversos tipos de datos. Es de código abierto y ampliamente popular. Tenga en cuenta cómo las siguientes empresas integran Elasticsearch en su aplicación:

- [Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) para texto completo e incremental (búsqueda a medida que escribes) búsqueda.
- [GitHub](https://www.elastic.co/customers/github) para indexar y exponer más de 8 millones de repositorios de código.  
- [Docker](https://www.elastic.co/customers/docker) para hacer que su biblioteca de contenedores sea detectable.

Elasticsearch se basa en el motor de búsqueda de texto completo [Apache Lucene.](https://lucene.apache.org/core/) Lucene proporciona indización y consulta de documentos de alto rendimiento. Indiza los datos con un esquema de indexación invertido: en lugar de asignar páginas a palabras clave, asigna palabras clave a páginas como un glosario al final de un libro. Lucene tiene potentes capacidades de sintaxis de consulta y puede consultar datos mediante:

- Término (una palabra completa)
- Prefijo (comienza con word)
- Comodín (usando filtros "\*" o "?"
- Frase (una secuencia de texto en un documento)
- Valor booleano (búsquedas complejas que combinan consultas)

Aunque Lucene proporciona fontanería de bajo nivel para la búsqueda, Elasticsearch proporciona el servidor que se encuentra en la parte superior de Lucene. Elasticsearch añade funcionalidad de nivel superior para simplificar el trabajo de Lucene, incluida una API RESTful para acceder a la funcionalidad de indexación y búsqueda de Lucene. También proporciona una infraestructura distribuida capaz de escalabilidad masiva, tolerancia a errores y alta disponibilidad.

Para aplicaciones nativas de la nube más grandes con requisitos de búsqueda complejos, Elasticsearch está disponible como servicio administrado en Azure. Microsoft Azure Marketplace cuenta con plantillas preconfiguradas que los desarrolladores pueden usar para implementar un clúster de Elasticsearch en Azure.

Desde Microsoft Azure Marketplace, los desarrolladores pueden usar plantillas preconfiguradas creadas para implementar rápidamente un clúster de Elasticsearch en Azure. Con la oferta administrada por Azure, puede implementar hasta 50 nodos de datos, 20 nodos de coordinación y tres nodos maestros dedicados.

## <a name="summary"></a>Resumen

En este capítulo se presenta una visión detallada de los datos en sistemas nativos de la nube. Comenzamos contrastando el almacenamiento de datos en aplicaciones monolíticas con patrones de almacenamiento de datos en sistemas nativos de la nube. Examinamos los patrones de datos implementados en sistemas nativos de la nube, incluidas las consultas entre servicios, las transacciones distribuidas y los patrones para tratar con sistemas de gran volumen. Contrastamos SQL con datos NoSQL. Examinamos las opciones de almacenamiento de datos disponibles en Azure que incluyen opciones centradas en Microsoft y de código abierto. Por último, analizamos el almacenamiento en caché y Elasticsearch en una aplicación nativa de la nube.

### <a name="references"></a>Referencias

- [Patrón Command and Query Responsibility Segregation (CQRS).](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [Patrón Event Sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [RDDBMS frente a bases de datos NoSQL: Visión general](https://maxivak.com/rdbms-vs-nosql-databases/)

- [¿Por qué RDBMS Partition Tolerant en el teorema CAP y por qué está disponible?](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [Vista materializada](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [Todo lo que realmente necesita saber sobre bases de datos de código abierto](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [Patrón de transacción de compensación](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Patrón Saga](https://microservices.io/patterns/data/saga.html)

- [Patrones de Saga Cómo implementar transacciones empresariales mediante microservicios](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [Patrón de transacción de compensación](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Ponerse detrás de la bola 9: Niveles de consistencia de Cosmos DB explicados](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [Explorar los diferentes tipos de bases de datos NoSQL Parte II](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [En bases de datos RDBMS, NoSQL y NewSQL. Entrevista con John Ryan](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [SQL vs NoSQL vs NewSQL: La comparación completa](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [DASH: Cuatro propiedades de las bases de datos nativas de Kubernetes](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [CockroachDB](https://www.cockroachlabs.com/)

- [TiDB](https://pingcap.com/en/)

- [YugabyteDB](https://www.yugabyte.com/)

- [Vitess](https://vitess.io/)

- [Elasticsearch: The Definitive Guide (Elasticsearch: la guía definitiva).](http://shop.oreilly.com/product/0636920028505.do)
  
- [Introducción a Apache Lucene](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
>[Anterior](azure-caching.md)
>[Siguiente](resiliency.md) <!-- Next Chapter -->

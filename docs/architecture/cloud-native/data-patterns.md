---
title: Patrones de datos nativos en la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Patrones de datos nativos de la nube
ms.date: 06/30/2019
ms.openlocfilehash: 9e90409b0b633796b452cfcfecb3896e79002d4d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337423"
---
# <a name="cloud-native-data-patterns"></a>Patrones de datos nativos en la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Aunque los datos descentralizados pueden mejorar el rendimiento, la escalabilidad y el ahorro de costos, también presenta muchos desafíos. La consulta de datos entre microservicios es compleja. Una transacción que abarca microservicios debe administrarse mediante programación, ya que las transacciones distribuidas no se admiten en aplicaciones nativas de la nube. Puede pasar de un mundo de *coherencia inmediata* a la *coherencia final*.

Ahora trataremos estos desafíos.

## <a name="cross-service-queries"></a>Consultas entre servicios

¿Cómo consulta una aplicación los datos que se distribuyen entre muchos microservicios independientes?

En la figura 5-4 se muestra este escenario.

![Consultas entre microservicios](./media/cross-service-query.png)

**Figura 5-4**. Consultas entre microservicios

Observe cómo en la figura anterior vemos un microservicio de cesta de la compra que agrega un artículo al carro de la compra de un usuario. Aunque el almacén de datos de la cesta de la compra contiene una tabla basket y lineItem, no contiene datos de productos o de precios, ya que estos elementos se encuentran en los microservicios de productos y precios. Para agregar un elemento, el microservicio de cesta de la compra necesita datos de productos y datos de precios. ¿Cuáles son las opciones para obtener los datos de precios y productos?

En la figura 5-5 se muestra el microservicio de cesta de la compra que realiza una llamada HTTP directa al catálogo de productos y a los microservicios de precios.

![Comunicación http directa](./media/direct-http-communication.png)

**Figura 5-5**. Comunicación HTTP directa

Aunque es factible implementar, en el capítulo 4 se explicó cómo las llamadas HTTP directas a través de microservicios acoplan el sistema y no se considera una buena práctica.

Podríamos implementar un microservicio del agregador que se muestra en la figura 5-6.

![Microservicio del agregador](./media/aggregator-microservice.png)

**Figura 5-6**. Microservicio del agregador

Aunque este enfoque encapsula el flujo de trabajo de la operación empresarial en un microservicio individual, agrega complejidad y sigue produciendo llamadas HTTP directas.

Un enfoque común para ejecutar consultas entre servicios usa el patrón de [vista materializada](https://docs.microsoft.com/azure/architecture/patterns/materialized-view), que se muestra en la figura 5-7.

![Patrón de vista materializada](./media/materialized-view-pattern.png)

**Figure5-7**. Patrón de vista materializada

Con este patrón, se coloca directamente una tabla local (conocida como *modelo de lectura*) en el servicio de cesta de la compra que contiene una copia desnormalizada de los datos que se necesitan del producto y los microservicios de precios. La colocación de los datos en el microservicio de la cesta de la compra elimina la necesidad de invocar una costosa llamada entre servicios. Con los datos locales del servicio, mejora el tiempo de respuesta y la confiabilidad.

La detección con este enfoque es que ahora tiene datos duplicados en el sistema. En los sistemas nativos en la nube, los datos duplicados no se consideran [antipatrón](https://en.wikipedia.org/wiki/Anti-pattern) y se suelen implementar en sistemas nativos de la nube. Sin embargo, un solo sistema puede ser el propietario de cualquier conjunto de datos y debe implementar un mecanismo de sincronización para el sistema de registro para actualizar todos los modelos de lectura asociados, siempre que se produzca un cambio en los datos subyacentes.

## <a name="transactional-support"></a>Compatibilidad transaccional

Aunque las consultas entre microservicios son desafiantes, la implementación de una transacción en varios microservicios puede ser compleja. El reto inherente de mantener la coherencia de los datos entre los orígenes de datos que residen en diferentes microservicios no puede estar en un subestado. En la figura 5-8 se muestra el problema.

![Transacción en el patrón saga](./media/saga-transaction-operation.png)

**Figura 5-8**. Implementar una transacción entre microservicios

Tenga en cuenta que, en la ilustración anterior, cinco microservicios independientes participan en una transacción de *creación de pedidos* distribuida. Sin embargo, la transacción de cada uno de los cinco microservicios individuales debe ser correcta, o todos deben anular y revertir la operación. Aunque la compatibilidad con transacciones integrada está disponible dentro de cada uno de los microservicios, no se admite una transacción distribuida en los cinco servicios.

Dado que la compatibilidad transaccional es esencial para que esta operación Mantenga los datos coherentes en cada uno de los microservicios, debe construir mediante programación una transacción distribuida.

Un patrón popular para agregar compatibilidad transaccional mediante programación es el [patrón saga](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/). Se implementa mediante la agrupación de transacciones locales y la invocación secuencial de cada una de ellas. Si se produce un error en una transacción local, el saga anula la operación e invoca un conjunto de [transacciones de compensación](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction) para deshacer los cambios realizados por las transacciones locales anteriores. En la figura 5-9 se muestra una transacción con error con el patrón saga.

![Reversión en el patrón saga](./media/saga-rollback-operation.png)

**Figura 5-9**. Deshacer una transacción

Observe cómo en la ilustración anterior se produjo un error en la operación *GenerateContent* en el microservicio de música. El saga invoca las transacciones de compensación (en rojo) para quitar el contenido, cancelar el pago y cancelar el pedido, devolviendo los datos de cada microservicio a un estado coherente.

Los patrones de saga normalmente se sencillamenten como una serie de eventos relacionados o se organizan como un conjunto de comandos relacionados.

## <a name="cqrs-pattern"></a>Patrón CQRS

CQRS, o [segregación de responsabilidades de comandos y consultas](https://docs.microsoft.com/azure/architecture/patterns/cqrs), es un patrón arquitectónico que separa las operaciones que leen los datos de los que escriben datos. Este patrón puede ayudar a maximizar el rendimiento, la escalabilidad y la seguridad.

En *los* escenarios de acceso a datos normales, se implementa un modelo único (entidad y objeto de repositorio) que realiza operaciones de lectura y escritura de datos.

Sin embargo, un escenario de acceso a datos más avanzado podría beneficiarse de modelos independientes y tablas de datos para lecturas y escrituras. Para mejorar el rendimiento, la operación de lectura, que se conoce como una *consulta*, puede consultar una representación muy desnormalizada de los datos para evitar combinaciones de tablas repetitivas costosas. Mientras que la operación de *escritura* , conocida como *comando*, podría actualizarse contra una representación totalmente normalizada de los datos. A continuación, debe implementar un mecanismo para mantener ambas representaciones sincronizadas. Normalmente, siempre que se modifica la tabla de escritura, se genera un evento que replica la modificación de los datos en la tabla de lectura.

En la figura 5-10 se muestra una implementación del patrón CQRS.

![Implementación de CQRS](./media/cqrs-implementation.png)

**Figura 5-10**. Implementación de CQRS

Observe cómo se implementan los modelos de comando y consulta independientes en la figura anterior. Además, cada operación de escritura de datos se guarda en el almacén de escritura y, a continuación, se propaga al almacén de lectura. Preste mucha atención a cómo funciona el proceso de propagación en el principio de [coherencia eventual](https://www.cloudcomputingpatterns.org/eventual_consistency/), mientras que el modelo de lectura finalmente se sincroniza con el modelo de escritura, pero puede haber algún retraso en el proceso.

Mediante la implementación de la separación, tiene la capacidad de escalar lecturas y escrituras por separado. También puede imponer una seguridad más estricta en las operaciones de escritura que las que se refieren a las lecturas.

Normalmente, los patrones CQRS se aplican a secciones limitadas del sistema en función de las necesidades específicas.

## <a name="relational-vs-nosql"></a>Relacional frente a NoSQL

El impacto de las tecnologías [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) no puede ser sobreutilizado, especialmente en sistemas nativos en la nube distribuidos. La proliferación de nuevas tecnologías de datos en este espacio ha interrumpido soluciones que, una vez confiaba exclusivamente en las bases de datos relacionales.

Por un lado, las bases de datos relacionales han sido una tecnología predominante para décadas. Están consolidados, probados y ampliamente implementados. Los productos de base de datos, la experiencia y las herramientas que compiten. Las bases de datos relacionales proporcionan un almacén de tablas de datos relacionadas. Estas tablas tienen un esquema fijo, usan SQL (Lenguaje de consulta estructurado) para administrar datos y tienen garantías [acid](https://www.geeksforgeeks.org/acid-properties-in-dbms/) (también conocidas como atomicidad, coherencia, aislamiento y durabilidad).

Las bases de datos no-SQL, por otro lado, se refieren a almacenes de datos no relacionales de alto rendimiento. Excel en sus características de facilidad de uso, escalabilidad, resistencia y disponibilidad. En lugar de combinar tablas de datos normalizados, NoSQL almacena datos autodescriptivos (sin esquema) normalmente en documentos JSON. No ofrecen garantías [acid](https://www.geeksforgeeks.org/acid-properties-in-dbms/) .

Una manera de comprender las diferencias entre estos tipos de bases de datos puede encontrarse en el [teorema Cap](https://towardsdatascience.com/cap-theorem-and-distributed-database-management-systems-5c2be977950e), un conjunto de principios que se pueden aplicar a sistemas distribuidos que almacenan el estado. En la figura 5-11 se muestran las tres propiedades del CAP teorema.

![Teorema CAP](./media/cap-theorem.png)

**Figura 5-11**. Teorema CAP

El teorema indica que cualquier sistema de datos distribuidos ofrecerá un equilibrio entre coherencia, disponibilidad y tolerancia de particiones, y que cualquier base de datos solo puede garantizar dos de las tres propiedades:

- *Coherencia*: todos los nodos del clúster responderán con los datos más recientes, incluso si necesita bloquear una solicitud hasta que todas las réplicas se actualicen correctamente.

- *Disponibilidad*: cada nodo devolverá una respuesta en un período de tiempo razonable, incluso si esa respuesta no es los datos más recientes.

- *Tolerancia de partición*: garantiza que el sistema continuará funcionando si se produce un error en un nodo o se pierde la conectividad con otro.

Las bases de datos relacionales muestran coherencia y disponibilidad, pero no tolerancia a particiones. La creación de particiones de una base de datos relacional, como el particionamiento, es difícil y puede afectar al rendimiento.

Por otra parte, las bases de datos NoSQL suelen presentar tolerancia de particiones, lo que se conoce como escalabilidad horizontal y alta disponibilidad. Como el CAP teorema especifica, solo puede tener dos de los tres principios y se pierde la propiedad Consistency.

Las bases de datos NoSQL se distribuyen y normalmente se escalan horizontalmente a través de servidores de mercancías. Si lo hace, puede proporcionar una gran disponibilidad, tanto dentro como entre regiones geográficas con un coste reducido. Los datos se pueden particionar y replicar en estos equipos, o nodos, lo que proporciona redundancia y tolerancia a errores. El inconveniente es la coherencia. Un cambio en los datos de un nodo NoSQL puede tardar algún tiempo en propagarse a otros nodos. Normalmente, un nodo de base de datos NoSQL proporcionará una respuesta inmediata a una consulta, incluso si los datos que presenta están obsoletos y aún no se han actualizado.

Se trata de una [coherencia final](https://www.cloudcomputingpatterns.org/eventual_consistency/)conocida, una característica de los sistemas de datos distribuidos donde no se admiten las transacciones ACID. Es un breve retraso entre la actualización de un elemento de datos y el tiempo que se tarda en propagar esa actualización a cada uno de los nodos de réplica. Si actualiza un elemento de producto en una base de datos NoSQL en el Estados Unidos, pero al mismo tiempo consulta ese mismo elemento de datos desde un nodo de réplica de Europa, podría recuperar la información del producto anterior, hasta que el nodo Europeo se haya actualizado con el cambio del producto. La desventaja es que, al otorgar una [coherencia fuerte](https://en.wikipedia.org/wiki/Strong_consistency), esperar a que todos los nodos de réplica se actualicen antes de devolver el resultado de una consulta, puede admitir enormes volúmenes de tráfico y escalado, pero con la posibilidad de presentar datos antiguos.

Las bases de datos NoSQL se pueden clasificar por los cuatro modelos siguientes:

- *Almacén de documentos* (MongoDB, CouchDB, Couchbase): los datos (y los metadatos correspondientes) se almacenan de forma no relacional en documentos basados en JSON desnormalizados dentro de la base de datos.

- *Almacén de clave/valor* (Redis, Riak, Memcached): los datos se almacenan en pares de clave-valor simples con operaciones del sistema realizadas con una clave de acceso única asignada a un valor de datos de usuario.

- *Almacén de columnas anchas* (HBase, Cassandra): los datos relacionados se almacenan en un formato de columnas como un conjunto de pares de clave-valor anidados dentro de una sola columna con datos que se recuperan normalmente como una sola unidad sin tener que combinar varias tablas.

- *Almacenes de grafos* (Neo4J, Titan): los datos se almacenan como una representación gráfica dentro de un nodo junto con los bordes que especifican la relación entre los nodos.

Las bases de datos NoSQL se pueden optimizar para tratar con datos a gran escala, especialmente cuando los datos son relativamente simples. Considere una base de datos NoSQL cuando:

- La carga de trabajo requiere una gran escala y una simultaneidad alta.
- Tiene un gran número de usuarios.
- Los datos se pueden expresar simplemente sin relaciones.
- Debe distribuir geográficamente los datos.
- No necesita garantías ACID.
- Se implementará en hardware estándar.

A continuación, considere una base de datos relacional cuando:

- Las cargas de trabajo requieren una escala mediana y grande.
- La simultaneidad no es una preocupación importante.
- Se necesitan garantías ACID.
- Los datos se expresan con mayor relación.
- La aplicación se implementará en hardware grande y de alto nivel.

A continuación, veremos el almacenamiento de datos en la nube de Azure.

>[!div class="step-by-step"]
>[Anterior](distributed-data.md)
>[Siguiente](azure-data-storage.md)

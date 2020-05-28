---
title: Datos distribuidos
description: Compare el almacenamiento de datos en aplicaciones monolíticas y nativas en la nube.
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 28513f8691c06cf58ed14d57bf7830bb35d94852
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144401"
---
# <a name="distributed-data"></a>Datos distribuidos

Como hemos visto en este libro, un enfoque nativo en la nube cambia la manera de diseñar, implementar y administrar aplicaciones. También cambia la manera de administrar y almacenar los datos.

En la figura 5-1 se contrastan las diferencias.

![Almacenamiento de datos en aplicaciones nativas de la nube](./media/distributed-data.png)

**Figura 5-1**. Administración de datos en aplicaciones nativas en la nube

Los desarrolladores experimentados reconocerán fácilmente la arquitectura en el lado izquierdo de la figura 5-1. En esta *aplicación monolítica*, los componentes de servicio empresarial colocar juntos en un nivel de servicios compartidos, compartiendo datos de una única base de datos relacional.

En muchos sentidos, una sola base de datos mantiene la administración de datos simple. La consulta de datos en varias tablas es sencilla. Cambios en la actualización de datos juntos o en todas las reversiones. [Las transacciones ACID](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) garantizan una coherencia fuerte y inmediata.

Al diseñar para la nube nativa, adoptamos un enfoque diferente. En el lado derecho de la figura 5-1, observe cómo la funcionalidad empresarial se segrega en microservicios pequeños e independientes. Cada microservicio encapsula una funcionalidad empresarial específica y sus propios datos. La base de datos monolítica se descompone en un modelo de datos distribuido con muchas bases de datos más pequeñas, cada una de las cuales se alinea con un microservicio. Cuando el humo se borra, surge un diseño que expone una *base de datos por microservicio*.

## <a name="database-per-microservice-why"></a>Base de datos por microservicio, ¿por qué?

Esta base de datos por microservicio proporciona muchas ventajas, especialmente para los sistemas que deben evolucionar rápidamente y admiten una escala masiva. Con este modelo...

- Los datos del dominio se encapsulan dentro del servicio
- El esquema de datos puede evolucionar sin afectar directamente a otros servicios
- Cada almacén de datos puede escalarse de forma independiente
- Un error del almacén de datos en un servicio no afecta directamente A otros servicios

La segregación de datos también permite a cada microservicio implementar el tipo de almacén de datos que se optimiza mejor para su carga de trabajo, sus necesidades de almacenamiento y patrones de lectura y escritura. Entre las opciones se incluyen los almacenes de datos relacionales, de documentos, de clave-valor e incluso de gráficos.

La figura 5-2 presenta el principio de la persistencia de Polyglot en un sistema nativo en la nube.

![Persistencia de datos de Polyglot](./media/polyglot-data-persistence.png)

**Figura 5-2**. Persistencia de datos de Polyglot

Observe en la ilustración anterior cómo cada microservicio admite un tipo de almacén de datos diferente.

- El microservicio del catálogo de productos consume una base de datos relacional para dar cabida a la estructura relacional enriquecida de sus datos subyacentes.
- El microservicio de carro de la compra consume una caché distribuida que admite su simple almacén de datos de clave-valor.
- El microservicio de pedidos consume una base de datos de documentos NoSql para operaciones de escritura junto con un almacén de clave/valor muy desnormalizado para acomodar grandes volúmenes de operaciones de lectura.
  
Aunque las bases de datos relacionales siguen siendo relevantes para los microservicios con datos complejos, las bases de datos NoSQL han ganado una popularidad considerable. Proporcionan escalado masivo y alta disponibilidad. Su naturaleza sin esquema permite a los desarrolladores salir de una arquitectura de clases de datos con tipo y ORM que hacen que los cambios sean costosos y lentos. En este capítulo se tratan las bases de datos NoSQL.

 Aunque encapsular los datos en microservicios independientes puede aumentar la agilidad, el rendimiento y la escalabilidad, también presenta muchos desafíos. En la siguiente sección, trataremos estos desafíos junto con patrones y prácticas para ayudarle a superarlos.  

## <a name="cross-service-queries"></a>Consultas entre servicios

Aunque los microservicios son independientes y se centran en funcionalidades funcionales específicas, como el inventario, el envío o la ordenación, con frecuencia requieren la integración con otros microservicios. A menudo, la integración implica que un microservicio *consulte* a otro los datos. En la figura 5-3 se muestra el escenario.

![Consultas entre microservicios](./media/cross-service-query.png)

**Figura 5-3**. Consultas entre microservicios

En la ilustración anterior, vemos un microservicio de cesta de la compra que agrega un artículo a la cesta de la compra de un usuario. Mientras que el almacén de datos para este microservicio contiene datos de cesta y de elemento de línea, no mantiene los datos de productos o de precios. En su lugar, los elementos de datos son propiedad de los microservicios de catálogo y de precios. Esto supone un problema. ¿Cómo puede el microservicio de cesta de la compra agregar un producto a la cesta de la compra del usuario cuando no tiene datos de productos ni de precios en su base de datos?

Una opción que se describe en el capítulo 4 es una [llamada http directa](service-to-service-communication.md#queries) desde la cesta de la compra al catálogo y los microservicios de precios. Sin embargo, en el capítulo 4, hemos mencionado que las *llamadas http* sincrónicas unen microservicios, lo que reduce su autonomía y reduce sus ventajas arquitectónicas.

También se puede implementar un patrón de solicitud-respuesta con colas de entrada y salida independientes para cada servicio. Sin embargo, este patrón es complicado y requiere la fontanería para correlacionar los mensajes de solicitud y respuesta.
Aunque Desacople las llamadas de microservicios de back-end, el servicio de llamada debe esperar de forma sincrónica a que se complete la llamada. La congestión de la red, los errores transitorios o un microservicio sobrecargado y pueden dar lugar a operaciones de ejecución prolongada e incluso con errores.

En su lugar, un patrón ampliamente aceptado para quitar las dependencias entre servicios es el [patrón de vista materializada](https://docs.microsoft.com/azure/architecture/patterns/materialized-view), que se muestra en la figura 5-4.

![Patrón de vista materializada](./media/materialized-view-pattern.png)

**Figura 5-4**. Materialized View Pattern

Con este patrón, se coloca una tabla de datos local (conocida como *modelo de lectura*) en el servicio de cesta de la compra. Esta tabla contiene una copia desnormalizada de los datos necesarios de los microservicios de productos y precios. Copiar los datos directamente en el microservicio de la cesta de la compra elimina la necesidad de costosas llamadas entre servicios. Con los datos locales del servicio, mejora el tiempo de respuesta y la confiabilidad del servicio. Además, tener su propia copia de los datos hace que el servicio de la cesta de la compra sea más resistente. Si el servicio de catálogo debe dejar de estar disponible, no afectará directamente al servicio de cesta de la compra. La cesta de la compra puede seguir operando con los datos de su propio almacén.

La detección con este enfoque es que ahora tiene datos duplicados en el sistema. Sin embargo, la duplicación *estratégica* de datos en sistemas nativos en la nube es una práctica establecida que no se considera un antipatrón, o una práctica incorrecta. Tenga en cuenta que solo un *servicio* puede poseer un conjunto de datos y tener autoridad sobre él. Deberá sincronizar los modelos de lectura cuando se actualice el sistema de registro. La sincronización se implementa normalmente mediante mensajería asincrónica con un [patrón de publicación/suscripción](service-to-service-communication.md#events), como se muestra en la figura 5,4.

## <a name="distributed-transactions"></a>Distributed transactions

Aunque la consulta de datos entre microservicios es difícil, implementar una transacción en varios microservicios es incluso más complejo. El reto inherente de mantener la coherencia de los datos en orígenes de datos independientes en diferentes microservicios no puede estar desutilizado. La falta de transacciones distribuidas en aplicaciones nativas de la nube significa que debe administrar mediante programación las transacciones distribuidas. Puede pasar de un mundo de *coherencia inmediata* a la *coherencia final*.

En la figura 5-5 se muestra el problema.

![Transacción en el patrón saga](./media/saga-transaction-operation.png)

**Figura 5-5**. Implementar una transacción entre microservicios

En la ilustración anterior, cinco microservicios independientes participan en una transacción distribuida que crea un pedido. Cada microservicio mantiene su propio almacén de datos e implementa una transacción local para su almacén. Para crear el pedido, la transacción local para *cada* microservicio individual debe realizarse correctamente, o *todas* deben anular y revertir la operación. Aunque la compatibilidad con transacciones integrada está disponible dentro de cada uno de los microservicios, no hay compatibilidad con una transacción distribuida que abarcaría entre los cinco servicios para mantener la coherencia de los datos.

En su lugar, debe construir esta transacción distribuida *mediante programación*.

Un patrón popular para agregar compatibilidad transaccional distribuida es el patrón saga. Se implementa agrupando las transacciones locales mediante programación y invocando secuencialmente cada una de ellas. Si se produce un error en cualquiera de las transacciones locales, el saga anula la operación e invoca un conjunto de [transacciones de compensación](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction). Las transacciones de compensación deshacen los cambios realizados por las transacciones locales anteriores y restauran la coherencia de los datos. En la figura 5-6 se muestra una transacción con error con el patrón saga.

![Reversión en el patrón saga](./media/saga-rollback-operation.png)

**Figura 5-6**. Revertir una transacción

En la ilustración anterior, se produjo un error en la operación de *actualización de inventario* en el microservicio de inventario. Saga invoca un conjunto de transacciones de compensación (en rojo) para ajustar los recuentos de inventario, cancelar el pago y el pedido y devolver los datos de cada microservicio a un estado coherente.

Los patrones saga normalmente se sencillamenten como una serie de eventos relacionados, o bien se organizan como un conjunto de comandos relacionados. En el capítulo 4, analizamos el patrón Service Aggregator que sería la base de una implementación de saga orquestada. También hemos analizado los eventos junto con temas de Azure Service Bus y Azure Event Grid que serían una base para una implementación de sencillamente saga.

## <a name="high-volume-data"></a>Datos de gran volumen

Las aplicaciones nativas en la nube de gran tamaño suelen admitir los requisitos de datos de gran volumen. En estos casos, las técnicas tradicionales de almacenamiento de datos pueden producir cuellos de botella. En el caso de los sistemas complejos que se implementan a gran escala, segregación de responsabilidades de comandos y consultas (CQRS) y el abastecimiento de eventos pueden mejorar el rendimiento de la aplicación.  

### <a name="cqrs"></a>CQRS

[CQRS](https://docs.microsoft.com/azure/architecture/patterns/cqrs)es un patrón arquitectónico que puede ayudar a maximizar el rendimiento, la escalabilidad y la seguridad. El patrón separa las operaciones que leen datos de las operaciones que escriben datos.

En los escenarios normales, se usan el mismo modelo de entidad y el mismo objeto de repositorio de datos para las operaciones *de lectura y* escritura.

Sin embargo, un escenario de datos de gran volumen puede beneficiarse de modelos independientes y tablas de datos para lecturas y escrituras. Para mejorar el rendimiento, la operación de lectura puede realizar consultas en una representación muy desnormalizada de los datos para evitar combinaciones de tablas repetitivas y bloqueos de tabla. La operación de *escritura* , conocida como *comando*, se actualizaría contra una representación totalmente normalizada de los datos que garantizarían la coherencia. A continuación, debe implementar un mecanismo para mantener ambas representaciones sincronizadas. Normalmente, siempre que se modifica la tabla de escritura, se publica un evento que replica la modificación en la tabla de lectura.

En la figura 5-7 se muestra una implementación del patrón CQRS.

![segregación de responsabilidades de comandos y consultas](./media/cqrs-implementation.png)

**Figura 5-7**. Implementación de CQRS

En la ilustración anterior, se implementan los modelos de comando y consulta independientes. Cada operación de escritura de datos se guarda en el almacén de escritura y, a continuación, se propaga al almacén de lectura. Preste mucha atención a cómo funciona el proceso de propagación de datos en el principio de [coherencia eventual](https://www.cloudcomputingpatterns.org/eventual_consistency/). El modelo de lectura finalmente se sincroniza con el modelo de escritura, pero puede haber algún retraso en el proceso. Analizamos la coherencia final en la sección siguiente.

Esta separación permite que las lecturas y escrituras se escalen de forma independiente. Las operaciones de lectura utilizan un esquema optimizado para las consultas, mientras que las escrituras usan un esquema optimizado para las actualizaciones. Las consultas de lectura incluyen datos desnormalizados, mientras que la lógica de negocios compleja se puede aplicar al modelo de escritura. También puede imponer una seguridad más estricta en las operaciones de escritura que las que exponen lecturas.

La implementación de CQRS puede mejorar el rendimiento de las aplicaciones para los servicios nativos de la nube. Sin embargo, da como resultado un diseño más complejo. Aplique este principio con cuidado y de forma estratégica a las secciones de la aplicación nativa en la nube que se beneficiarán de ella. Para obtener más información sobre CQRS, vea el libro [de Microsoft microservicios de .net: arquitectura para aplicaciones .net en contenedor](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns).

### <a name="event-sourcing"></a>Aprovisionamiento de eventos

Otro enfoque para optimizar los escenarios de datos de gran volumen implica el [suministro de eventos](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

Un sistema normalmente almacena el estado actual de una entidad de datos. Si un usuario cambia el número de teléfono, por ejemplo, el registro del cliente se actualiza con el nuevo número. Siempre sabemos el estado actual de una entidad de datos, pero cada actualización sobrescribe el estado anterior.

En la mayoría de los casos, este modelo funciona bien. Sin embargo, en los sistemas de gran volumen, la sobrecarga del bloqueo transaccional y las operaciones de actualización frecuentes pueden afectar al rendimiento de la base de datos, la capacidad de respuesta y la escalabilidad del límite.

El suministro de eventos adopta un enfoque diferente para capturar datos. Cada operación que afecta a los datos se conserva en un almacén de eventos. En lugar de actualizar el estado de un registro de datos, se anexa cada cambio a una lista secuencial de eventos pasados, similar a la contabilidad de un contable. El almacén de eventos se convierte en el sistema de registro de los datos. Se usa para propagar varias vistas materializadas en el contexto enlazado de un microservicio. En la figura 5,8 se muestra el patrón.

![Aprovisionamiento de eventos](./media/event-sourcing.png)

**Figura 5-8**. Aprovisionamiento de eventos

En la ilustración anterior, observe cómo cada entrada (en azul) del carro de la compra de un usuario se anexa a un almacén de eventos subyacente. En la vista materializada adyacente, el sistema proyecta el estado actual mediante la reproducción de todos los eventos asociados a cada carro de la compra. Esta vista, o leer modelo, se expone de nuevo a la interfaz de usuario. Los eventos también se pueden integrar con sistemas y aplicaciones externos o consultarse para determinar el estado actual de una entidad. Con este enfoque, se mantiene el historial. No solo sabe el estado actual de una entidad, sino también cómo llegó a este estado.

En la conversación mecánica, el suministro de eventos simplifica el modelo de escritura. No hay actualizaciones ni eliminaciones. Al anexar cada entrada de datos como un evento inmutable, se minimizan los conflictos de contención, bloqueo y simultaneidad asociados a las bases de datos relacionales. La creación de modelos de lectura con el patrón de vista materializada le permite desacoplar la vista del modelo de escritura y elegir el mejor almacén de datos para optimizar las necesidades de la interfaz de usuario de la aplicación.

Para este patrón, considere un almacén de datos que admita directamente el origen de eventos. Azure Cosmos DB, MongoDB, Cassandra, CouchDB y RavenDB son buenos candidatos.

Al igual que con todos los patrones y tecnologías, implemente estratégicamente y cuando sea necesario. Aunque el suministro de eventos puede proporcionar un mayor rendimiento y escalabilidad, se refiere a la complejidad y la curva de aprendizaje.

>[!div class="step-by-step"]
>[Anterior](service-mesh-communication-infrastructure.md)
>[Siguiente](relational-vs-nosql-data.md)

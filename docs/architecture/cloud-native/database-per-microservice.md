---
title: Base de datos por microservicio
description: Contraste el almacenamiento de datos en aplicaciones monolíticas y nativas de la nube.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: c0c5611fa866d70f155e4bdad2eee1181b13c065
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141450"
---
# <a name="database-per-microservice"></a>Base de datos por microservicio

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Como hemos visto a lo largo de este libro, un enfoque nativo de la nube cambia la forma en que diseña, implementa y administra las aplicaciones. También cambia la forma de administrar y almacenar datos.

La Figura 5-1 contrasta las diferencias.

![Almacenamiento de datos en aplicaciones nativas de la nube](./media/distributed-data.png)

**Figura 5-1**. Gestión de datos en aplicaciones nativas de la nube

Los desarrolladores experimentados reconocerán fácilmente la arquitectura en el lado izquierdo de la figura 5-1. En esta *aplicación monolítica,* los componentes de servicio empresarial se unen en un nivel de servicios compartidos, compartiendo datos de una única base de datos relacional.

En muchos sentidos, una sola base de datos simplifica la administración de datos. Consultar datos en varias tablas es sencillo. Los cambios en los datos se actualizan juntos o todos se revierten. [Las transacciones ACID](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) garantizan una consistencia fuerte e inmediata.

Diseñando para nativos de la nube, tomamos un enfoque diferente. En el lado derecho de la Figura 5-1, observe cómo la funcionalidad empresarial se separa en microservicios pequeños e independientes. Cada microservicio encapsula una funcionalidad empresarial específica y sus propios datos. La base de datos monolítica se descompone en un modelo de datos distribuidocon muchas bases de datos más pequeñas, cada una de las que se alinea con un microservicio. Cuando el humo se borra, surge moscada con un diseño que expone una base de *datos por microservicio.*

## <a name="why"></a>¿Por qué?

Esta base de datos por microservicio proporciona muchas ventajas, especialmente para los sistemas que deben evolucionar rápidamente y admitir una escala masiva. Con este modelo...

- Los datos de dominio se encapsulan dentro del servicio
- El esquema de datos puede evolucionar sin afectar directamente a otros servicios
- Cada almacén de datos puede escalar de forma independiente
- Un error en el almacén de datos en un servicio no afectará directamente a otros servicios

La segregación de datos también permite que cada microservicio implemente el tipo de almacén de datos que mejor se optimiza para su carga de trabajo, las necesidades de almacenamiento y los patrones de lectura y escritura. Las opciones incluyen almacenes de datos relacionales, de documentos, clave-valor e incluso basados en gráficos.

La Figura 5-2 presenta el principio de persistencia políglota en un sistema nativo de la nube.

![Persistencia de datos políglotas](./media/polyglot-data-persistence.png)

**Figura 5-2**. Persistencia de datos políglotas

Tenga en cuenta en la figura anterior cómo cada microservicio admite un tipo diferente de almacén de datos.

- El microservicio de catálogo de productos consume una base de datos relacional para dar cabida a la estructura relacional enriquecida de sus datos subyacentes.
- El microservicio del carro de la compra consume una memoria caché distribuida que admite su almacén de datos de clave-valor simple.
- El microservicio de ordenación consume una base de datos de documentos NoSql para operaciones de escritura junto con un almacén de clave/valor altamente desnormalizado para dar cabida a grandes volúmenes de operaciones de lectura.
  
Aunque las bases de datos relacionales siguen siendo relevantes para microservicios con datos complejos, las bases de datos NoSQL han ganado una popularidad considerable. Proporcionan una escala masiva y alta disponibilidad. Su naturaleza sin esquemas permite a los desarrolladores alejarse de una arquitectura de clases de datos con tipo y ORM que hacen que el cambio sea costoso y consume mucho tiempo. Cubrimos bases de datos NoSQL más adelante en este capítulo.

 Aunque encapsular datos en microservicios independientes puede aumentar la agilidad, el rendimiento y la escalabilidad, también presenta muchos desafíos. En la siguiente sección, analizamos estos desafíos junto con patrones y prácticas para ayudar a superarlos.  

## <a name="cross-service-queries"></a>Consultas entre servicios

Aunque los microservicios son independientes y se centran en capacidades funcionales específicas, como inventario, envío u pedido, con frecuencia requieren integración con otros microservicios. A menudo, la integración implica un microservicio *que consulta* a otro para obtener datos. La Figura 5-3 muestra el escenario.

![Consulta a través de microservicios](./media/cross-service-query.png)

**Figura 5-3**. Consulta a través de microservicios

En la figura anterior, vemos un microservicio de cesta de la compra que agrega un elemento a la cesta de la compra de un usuario. Aunque el almacén de datos de este microservicio contiene datos de cesta y artículos de línea, no mantiene datos de productos o precios. En su lugar, esos elementos de datos son propiedad del catálogo y los microservicios de precios. Esto presenta un problema. ¿Cómo puede el microservicio de la cesta de la compra agregar un producto a la cesta de la compra del usuario cuando no tiene datos de productos ni precios en su base de datos?

Una opción que se describe en el capítulo 4 es una [llamada HTTP directa](service-to-service-communication.md#queries) desde la cesta de la compra al catálogo y a los microservicios de precios. Sin embargo, en el capítulo 4, dijimos que las llamadas HTTP sincrónicas *acoplan* microservicios, lo que reduce su autonomía y disminuye sus beneficios arquitectónicos.

También podríamos implementar un patrón de solicitud-respuesta con colas de entrada y salida independientes para cada servicio. Sin embargo, este patrón es complicado y requiere fontanería para correlacionar mensajes de solicitud y respuesta.
Aunque desacopla las llamadas de microservicio de back-end, el servicio de llamada debe esperar sincrónicamente a que se complete la llamada. Congestión de red, errores transitorios o un microservicio sobrecargado y pueden dar lugar a operaciones de larga ejecución e incluso con errores.

En su lugar, un patrón ampliamente aceptado para quitar dependencias entre servicios es el patrón de [vista materializado,](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)que se muestra en la figura 5-4.

![Patrón de vista materializado](./media/materialized-view-pattern.png)

**Figura 5-4**. Materialized View Pattern

Con este patrón, se coloca una tabla de datos local (conocida como modelo de *lectura)* en el servicio de cesta de la compra. Esta tabla contiene una copia desnormalizada de los datos necesarios del producto y los microservicios de precios. Copiar los datos directamente en el microservicio de la cesta de la compra elimina la necesidad de costosas llamadas entre servicios. Con los datos locales del servicio, se mejora el tiempo de respuesta y la fiabilidad del servicio. Además, tener su propia copia de los datos hace que el servicio de cesta de la compra sea más resistente. Si el servicio de catálogo no estuviera disponible, no afectaría directamente al servicio de cesta de la compra. La cesta de la compra puede seguir operando con los datos de su propia tienda.

La captura con este enfoque es que ahora tiene datos duplicados en el sistema. Sin embargo, duplicar *estratégicamente* los datos en sistemas nativos de la nube es una práctica establecida y no se considera un antipatrón, o una mala práctica. Tenga en cuenta que *uno y un solo servicio* pueden poseer un conjunto de datos y tener autoridad sobre él. Deberá sincronizar los modelos de lectura cuando se actualice el sistema de registro. La sincronización se implementa normalmente a través de mensajería asincrónica con un patrón de [publicación/suscripción,](service-to-service-communication.md#events)como se muestra en la figura 5.4.

## <a name="distributed-transactions"></a>Distributed transactions

Aunque es difícil consultar datos entre microservicios, implementar una transacción en varios microservicios es aún más complejo. El desafío inherente de mantener la coherencia de los datos entre orígenes de datos independientes en diferentes microservicios no se puede subestimada. La falta de transacciones distribuidas en aplicaciones nativas de la nube significa que debe administrar las transacciones distribuidas mediante programación. Usted pasa de un mundo de *consistencia inmediata* a la de *consistencia final.*

La Figura 5-5 muestra el problema.

![Transacción en patrón saga](./media/saga-transaction-operation.png)

**Figura 5-5**. Implementación de una transacción en microservicios

En la figura anterior, cinco microservicios independientes participan en una transacción distribuida que crea un pedido. Cada microservicio mantiene su propio almacén de datos e implementa una transacción local para su almacén. Para crear el pedido, la transacción local para *cada* microservicio individual debe realizarse correctamente o *todos* deben anular y revertir la operación. Aunque la compatibilidad transaccional integrada está disponible dentro de cada uno de los microservicios, no hay compatibilidad para una transacción distribuida que abarcaría los cinco servicios para mantener la coherencia de los datos.

En su lugar, debe construir esta transacción distribuida *mediante programación.*

Un patrón popular para agregar soporte transaccional distribuido es el patrón Saga. Se implementa agrupando las transacciones locales mediante programación y secuencialmente invocando cada una de ellas. Si se produce un error en alguna de las transacciones locales, Saga anula la operación e invoca un conjunto de transacciones de [compensación.](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction) Las transacciones de compensación deshacen los cambios realizados por las transacciones locales anteriores y restauran la coherencia de los datos. La figura 5-6 muestra una transacción con errores con el patrón Saga.

![Retrocede en el patrón saga](./media/saga-rollback-operation.png)

**Figura 5-6**. Revertir una transacción

En la figura anterior, la operación *Actualizar inventario* ha fallado en el microservicio Inventario. La Saga invoca un conjunto de transacciones de compensación (en rojo) para ajustar los recuentos de inventario, cancelar el pago y el pedido y devolver los datos de cada microservicio a un estado coherente.

Los patrones de Saga suelen coreografiarse como una serie de eventos relacionados, o orquestados como un conjunto de comandos relacionados. En el capítulo 4, discutimos el patrón de agregador de servicio que sería la base para una implementación orquestada de la saga. También discutimos los eventos junto con los temas de Azure Service Bus y Azure Event Grid que serían una base para una implementación de saga coreografiada.

## <a name="high-volume-data"></a>Datos de alto volumen

Las aplicaciones nativas de la nube grandes a menudo admiten requisitos de datos de gran volumen. En estos escenarios, las técnicas tradicionales de almacenamiento de datos pueden causar cuellos de botella. Para los sistemas complejos que se implementan a gran escala, la segregación de responsabilidad de comandos y consultas (CQRS) y el abastecimiento de eventos pueden mejorar el rendimiento de las aplicaciones.  

### <a name="cqrs"></a>CQRS

[CQRS](https://docs.microsoft.com/azure/architecture/patterns/cqrs), es un patrón arquitectónico que puede ayudar a maximizar el rendimiento, la escalabilidad y la seguridad. El patrón separa las operaciones que leen datos de las operaciones que escriben datos.

Para escenarios normales, el mismo modelo de entidad y el mismo objeto de repositorio de datos se utilizan *para* las operaciones de lectura y escritura.

Sin embargo, un escenario de datos de gran volumen puede beneficiarse de modelos y tablas de datos independientes para lecturas y escrituras. Para mejorar el rendimiento, la operación de lectura podría consultar una representación altamente desnormalizada de los datos para evitar combinaciones de tablas repetitivas costosas y bloqueos de tabla. La operación de *escritura,* conocida como *comando*, se actualizaría con una representación totalmente normalizada de los datos que garantizaría la coherencia. A continuación, debe implementar un mecanismo para mantener ambas representaciones sincronizadas. Normalmente, cada vez que se modifica la tabla de escritura, publica un evento que replica la modificación en la tabla de lectura.

La Figura 5-7 muestra una implementación del patrón CQRS.

![Segregación de responsabilidad de comandos y consultas](./media/cqrs-implementation.png)

**Figura 5-7**. Implementación de CQRS

En la figura anterior, se implementan modelos de comando y consulta independientes. Cada operación de escritura de datos se guarda en el almacén de escritura y, a continuación, se propaga al almacén de lectura. Preste mucha atención a cómo funciona el proceso de propagación de datos sobre el principio de [coherencia final.](http://www.cloudcomputingpatterns.org/eventual_consistency/) El modelo de lectura finalmente se sincroniza con el modelo de escritura, pero puede haber algún retraso en el proceso. Discutimos la consistencia final en la siguiente sección.

Esta separación permite que las lecturas y escrituras se escalen de forma independiente. Las operaciones de lectura usan un esquema optimizado para las consultas, mientras que las escrituras usan un esquema optimizado para las actualizaciones. Las consultas de lectura van con datos desnormalizados, mientras que la lógica empresarial compleja se puede aplicar al modelo de escritura. Además, podría imponer una seguridad más estricta en las operaciones de escritura que las que exponen las lecturas.

La implementación de CQRS puede mejorar el rendimiento de las aplicaciones para servicios nativos de la nube. Sin embargo, resulta en un diseño más complejo. Aplique este principio cuidadosamente y estratégicamente a las secciones de su aplicación nativa de la nube que se beneficiarán de él. Para obtener más información sobre CQRS, consulte el libro de Microsoft [.NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns).

### <a name="event-sourcing"></a>Abastecimiento de eventos

Otro enfoque para optimizar escenarios de datos de gran volumen implica [Event Sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

Normalmente, un sistema almacena el estado actual de una entidad de datos. Si un usuario cambia su número de teléfono, por ejemplo, el registro de cliente se actualiza con el nuevo número. Siempre sabemos el estado actual de una entidad de datos, pero cada actualización sobrescribe el estado anterior.

En la mayoría de los casos, este modelo funciona bien. Sin embargo, en sistemas de gran volumen, la sobrecarga del bloqueo transaccional y las operaciones de actualización frecuentes puede afectar al rendimiento, la capacidad de respuesta y limitar la escalabilidad de la base de datos.

Event Sourcing adopta un enfoque diferente para capturar datos. Cada operación que afecta a los datos se conserva en un almacén de eventos. En lugar de actualizar el estado de un registro de datos, anexamos cada cambio a una lista secuencial de eventos pasados, similar al libro mayor de un contable. El almacén de eventos se convierte en el sistema de registro de los datos. Se utiliza para propagar varias vistas materializadas dentro del contexto delimitado de un microservicio. La Figura 5.8 muestra el patrón.

![Aprovisionamiento de eventos](./media/event-sourcing.png)

**Figura 5-8**. Aprovisionamiento de eventos

En la figura anterior, observe cómo cada entrada (en azul) para el carro de la compra de un usuario se anexa a un almacén de eventos subyacente. En la vista materializada contigua, el sistema proyecta el estado actual reproduciendo todos los eventos asociados a cada carro de la compra. Esta vista, o modelo de lectura, se expone de nuevo a la interfaz de usuario. Los eventos también se pueden integrar con sistemas y aplicaciones externos o consultarse para determinar el estado actual de una entidad. Con este enfoque, usted mantiene la historia. No solo conoce el estado actual de una entidad, sino también cómo llegó a este estado.

Mecánicamente hablando, el abastecimiento de eventos simplifica el modelo de escritura. No hay actualizaciones ni eliminaciones. Anexar cada entrada de datos como un evento inmutable minimiza los conflictos de contención, bloqueo y simultaneidad asociados con las bases de datos relacionales. La creación de modelos de lectura con el patrón de vista materializado le permite desacoplar la vista del modelo de escritura y elegir el mejor almacén de datos para optimizar las necesidades de la interfaz de usuario de la aplicación.

Para este patrón, considere la posibilidad de un almacén de datos que admita directamente el abastecimiento de eventos. Azure Cosmos DB, MongoDB, Cassandra, CouchDB y RavenDB son buenos candidatos.

Al igual que con todos los patrones y tecnologías, implementar estratégicamente y cuando sea necesario. Si bien el abastecimiento de eventos puede proporcionar un mayor rendimiento y escalabilidad, se produce a expensas de la complejidad y una curva de aprendizaje.

>[!div class="step-by-step"]
>[Anterior](service-mesh-communication-infrastructure.md)
>[Siguiente](relational-vs-nosql-data.md)

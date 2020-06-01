---
title: Desafíos y soluciones de la administración de datos distribuidos
description: Descubra cuáles son los desafíos y soluciones de la administración de datos distribuidos en el mundo de los microservicios.
ms.date: 09/20/2018
ms.openlocfilehash: 8b91879e879db293ed61bd5f3c49dc391b9d8f5a
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144323"
---
# <a name="challenges-and-solutions-for-distributed-data-management"></a>Desafíos y soluciones de la administración de datos distribuidos

## <a name="challenge-1-how-to-define-the-boundaries-of-each-microservice"></a>Desafío n.º 1: Cómo definir los límites de cada microservicio

Definir los límites del microservicio es probablemente el primer desafío con el que nos encontramos. Cada microservicio debe formar parte de la aplicación y a la vez ser autónomo con todas las ventajas y los desafíos que eso conlleva. Pero, ¿cómo se identifican estos límites?

En primer lugar, hay que centrarse en los modelos de dominio de la lógica de la aplicación y en los datos relacionados. Procure identificar islas de datos desacopladas y otros contextos dentro de la misma aplicación. Cada contexto podría tener un lenguaje empresarial diferente (términos empresariales diferentes). Los contextos deben definirse y administrarse de forma independiente. Los términos y las entidades que se usan en esos contextos pueden parecer similares, pero es posible que un concepto empresarial se use para otro propósito según el contexto, e incluso podría tener otro nombre. Por ejemplo, un usuario puede denominarse usuario en el contexto de identidad o pertenencia, cliente en un contexto CRM, comprador en un contexto de pedidos y así sucesivamente.

La manera en que identifica los límites entre varios contextos de aplicación con un dominio diferente para cada contexto es exactamente cómo puede identificar los límites de cada microservicio de negocio con sus respectivos datos y modelo de dominio. Siempre se intenta minimizar el acoplamiento entre esos microservicios. Más adelante en esta guía se explica con más detalle este modelo de diseño de identificación y modelo de dominio en la sección [Identificación de los límites del modelo de dominio para cada microservicio](identify-microservice-domain-model-boundaries.md).

## <a name="challenge-2-how-to-create-queries-that-retrieve-data-from-several-microservices"></a>Desafío n.º 2: Cómo crear consultas que recuperen datos de varios microservicios

Un segundo desafío es implementar consultas que recuperen datos de varios microservicios, evitando al mismo tiempo un exceso de comunicación entre los microservicios y las aplicaciones cliente remotas. Un ejemplo podría ser una pantalla de una aplicación móvil que necesita mostrar información de usuario perteneciente a los microservicios de cesta de la compra, catálogo e identidad de usuario. Otro ejemplo sería un informe complejo que implica muchas tablas ubicadas en varios microservicios. La solución adecuada depende de la complejidad de las consultas. En cualquier caso, se necesita una manera de agregar información para mejorar la eficacia de las comunicaciones del sistema. Las soluciones más comunes son las siguientes:

**Puerta de enlace de API**. Para una agregación de datos simple de varios microservicios que poseen diferentes bases de datos, el enfoque recomendado es utilizar un microservicio de agregación conocido como puerta de enlace de API. No obstante, se debe tener cuidado con la implementación de este patrón, ya que puede ser un punto de obstrucción en el sistema y puede infringir el principio de autonomía de microservicio. Para mitigar esta posibilidad, puede tener varias puertas de enlace de API y que cada una se centre en un segmento vertical o área de negocio del sistema. El patrón de puerta de enlace de API se detalla más adelante en la [sección Puerta de enlace de API](direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md#why-consider-api-gateways-instead-of-direct-client-to-microservice-communication).

**CQRS con tablas de consulta o lectura**. Otra solución para la agregación de datos de varios microservicios es el [patrón de vista materializada](https://docs.microsoft.com/azure/architecture/patterns/materialized-view). En este enfoque, se genera de antemano (se preparan los datos desnormalizados antes de que se produzcan las consultas reales) una tabla de solo lectura con los datos que pertenecen a varios microservicios. La tabla tiene un formato adaptado a las necesidades de la aplicación cliente.

Piense en algo parecido a la pantalla de una aplicación móvil. Si solo tiene una base de datos, puede reunir los datos de esa pantalla mediante una consulta SQL que realiza una combinación compleja que implica varias tablas. Pero, si tiene varias bases de datos y cada una pertenece a un microservicio diferente, no se puede consultar las bases de datos y crear una instrucción join (combinación) de SQL. La consulta compleja se convierte en un desafío. Para abordar esta necesidad, se puede usar un enfoque CQRS: crear una tabla desnormalizada en otra base de datos que se use solo para las consultas. La tabla se puede diseñar específicamente para los datos que necesita para la consulta compleja, con una relación uno a uno entre los campos que son necesarios para la pantalla de la aplicación y las columnas de la tabla de consulta. También pueden utilizarse con fines informativos.

Este enfoque no solo resuelve el problema original (cómo realizar consultas y combinaciones en varios microservicios); sino que también mejora el rendimiento considerablemente si se compara con una combinación compleja, puesto que los datos que necesita la aplicación ya están en la tabla de consulta. Por supuesto, la utilización de CQRS (Segregación de responsabilidades de comandos y consultas) con tablas de consulta o lectura implica un mayor trabajo de desarrollo y debe adoptarse coherencia final. Con todo, los requisitos de rendimiento y alta escalabilidad en [escenarios de colaboración](http://udidahan.com/2011/10/02/why-you-should-be-using-cqrs-almost-everywhere/) (o escenarios competitivos, según el punto de vista) son donde se debe aplicar CQRS con varias bases de datos.

**"Datos fríos" en bases de datos centrales.** Para informes complejos y consultas que no necesiten datos en tiempo real, un enfoque común consiste en exportar los "datos dinámicos" (datos transaccionales de los microservicios) como "datos fríos" en grandes bases de datos que se utilizan solo en informes. Dicho sistema de base de datos central puede ser un sistema basado en macrodatos, como Hadoop, un almacén de datos basado por ejemplo en Azure SQL Data Warehouse, o incluso una única base de datos SQL utilizada solamente para informes (si el tamaño no es un problema).

Debe tenerse en cuenta que esta base de datos centralizada tan solo se utilizará para consultas e informes que no requieran datos en tiempo real. Las actualizaciones y las transacciones originales, como origen confiable, deben estar en los datos de microservicios. La forma en que se sincronizarían los datos sería mediante comunicación orientada a eventos (descrita en las secciones siguientes) o mediante otras herramientas de importación y exportación de infraestructura de base de datos. Si se utiliza la comunicación orientada a eventos, el proceso de integración sería similar a la manera en que se propagan los datos como se describió anteriormente para las tablas de consulta CQRS.

Pero si el diseño de la aplicación implica agregar constantemente información procedente de varios microservicios para consultas complejas, podría ser un síntoma de un diseño incorrecto: un microservicio debería estar los más aislado posible de los demás microservicios. (Esto excluye los informes o análisis que siempre deben usar bases de datos centrales de datos fríos). Si este problema se repite a menudo, podría ser un motivo para combinar los microservicios. Debe equilibrar la autonomía de la evolución y la implementación de cada microservicio con dependencias seguras, cohesión y agregación de datos.

## <a name="challenge-3-how-to-achieve-consistency-across-multiple-microservices"></a>Desafío n.º 3: Cómo lograr que varios microservicios sean coherentes

Como se mencionó anteriormente, los datos que pertenecen a cada microservicio son exclusivos de ese microservicio y solo se puede acceder a ellos mediante la API del microservicio. Por lo tanto, un desafío es cómo implementar procesos empresariales de extremo a extremo manteniendo la coherencia entre varios microservicios.

Para analizar este problema, veamos un ejemplo de la [aplicación de referencia eShopOnContainers](https://aka.ms/eshoponcontainers). El microservicio de catálogo (Catalog) mantiene información sobre todos los productos, incluido el precio del producto. El microservicio de cesta administra datos temporales sobre elementos de producto que los usuarios agregan a su cesta de la compra, lo que incluye el precio de los elementos en el momento en que se han agregado a la cesta. Cuando se actualiza el precio de un producto en el catálogo, ese precio también debe actualizarse en las cestas activas que contienen ese mismo producto, además, el sistema probablemente debería advertir al usuario de que el precio de un elemento determinado ha cambiado desde que lo agregó a su cesta.

En una hipotética versión monolítica de esta aplicación, cuando cambia el precio de la tabla de productos, el subsistema de catálogo podría simplemente usar una transacción ACID para actualizar el precio actual de la tabla Cesta.

Pero en una aplicación basada en microservicios, las tablas Productos y Cesta pertenecen a sus respectivos microservicios. Ningún microservicio debería incluir en sus propias transacciones las tablas o el almacenamiento que pertenecen a otro microservicio, ni siquiera en consultas directas, como se muestra en la figura 4-9.

![Diagrama que muestra que los datos de la base de datos de microservicios no se pueden compartir.](./media/distributed-data-management/indepentent-microservice-databases.png)

**Figura 4-9**. Un microservicio no puede acceder directamente a una tabla en otro microservicio

El microservicio de catálogo no debe actualizar directamente la tabla Cesta, dado que esta pertenece al microservicio de cesta. Para realizar una actualización en el microservicio de cesta, el microservicio de catálogo debe usar coherencia final probablemente basada en la comunicación asincrónica como eventos de integración (comunicación basada en mensajes y eventos). Así es como la aplicación de referencia [eShopOnContainers](https://aka.ms/eshoponcontainers) lleva a cabo este tipo de coherencia entre microservicios.

Como indica el [teorema CAP](https://en.wikipedia.org/wiki/CAP_theorem), debe elegir entre disponibilidad y coherencia ACID. La mayoría de los escenarios basados en microservicios exigen disponibilidad y escalabilidad elevada en lugar de coherencia fuerte. Las aplicaciones críticas deben permanecer activas y en ejecución, y los desarrolladores pueden solucionar el problema de coherencia mediante el uso de técnicas de trabajo con coherencia débil o eventual. Este es el enfoque adoptado por la mayoría de las arquitecturas basadas en microservicios.

Además, las transacciones de confirmación en dos fases de estilo ACID no solo van en contra de los principios de microservicios; la mayoría de las bases de datos NoSQL (Azure Cosmos DB, MongoDB, etc.) no son compatibles con las transacciones de confirmación en dos fases, típicas de los escenarios de bases de datos distribuidas. Pero es esencial mantener la coherencia de los datos entre los servicios y las bases de datos. Este desafío también está relacionado con la cuestión de cómo se propagan los cambios a los distintos microservicios cuando hay datos concretos que deben ser redundantes: por ejemplo, cuando necesite que el nombre o la descripción del producto estén en el microservicio de catálogo y en el microservicio de cesta.

Una buena solución para este problema consiste en usar coherencia eventual entre microservicios articulada mediante comunicación orientada a eventos y un sistema de publicación y suscripción. Estos temas se tratan más adelante en la sección [Comunicación asincrónica orientada a eventos](asynchronous-message-based-communication.md#asynchronous-event-driven-communication) de esta guía.

## <a name="challenge-4-how-to-design-communication-across-microservice-boundaries"></a>Desafío n.º 4: Cómo diseñar la comunicación entre los límites de los microservicios

Comunicarse a través de los límites de los microservicios supone un verdadero reto. En este contexto, la comunicación no hace referencia al protocolo que debe usar (HTTP y REST, AMQP, mensajería, etc.). En su lugar, aborda el estilo de comunicación que se debe utilizar y, en especial, el grado de acoplamiento que deberían tener sus microservicios. Según el nivel de acoplamiento, cuando se produzca un error, el impacto de ese error en el sistema variará considerablemente.

En un sistema distribuido como es una aplicación basada en microservicios, con tantos artefactos desplazándose y con servicios distribuidos en varios servidores o hosts, se acabará produciendo algún error en los componentes. Puesto que se van a producir errores e interrupciones incluso mayores, es necesario diseñar los microservicios y la comunicación entre ellos teniendo en cuenta los riesgos comunes en este tipo de sistemas distribuidos.

Debido a su simplicidad, un enfoque popular consiste en implementar microservicios basados en HTTP (REST). Un enfoque basado en HTTP es absolutamente aceptable; aquí el problema está relacionado con el uso que se hace de él. No hay problema si usa solicitudes y respuestas HTTP para interactuar con sus microservicios desde las aplicaciones cliente o desde las puertas de enlace de API. Pero si crea cadenas largas de llamadas HTTP sincrónicas que afectan a varios microservicios, comunicándose a través de sus límites como si los microservicios fuesen objetos en una aplicación monolítica, la aplicación acabará teniendo problemas.

Por ejemplo, imagine que la aplicación cliente realiza una llamada API HTTP a un microservicio individual como el de pedidos. Si el microservicio de pedidos llama a su vez a otros microservicios mediante HTTP en el mismo ciclo de solicitud/respuesta, estará creando una cadena de llamadas HTTP. Aunque en un principio podría parecer razonable, hay aspectos importantes que se deben tener en cuenta:

- Bloqueo y bajo rendimiento. Debido a la naturaleza sincrónica de HTTP, la solicitud original no obtiene una respuesta hasta que finalicen todas las llamadas HTTP internas. Imagine que el número de estas llamadas aumenta considerablemente y, al mismo tiempo, se bloquea una de las llamadas HTTP intermedias a un microservicio. El resultado es que el rendimiento se verá perjudicado y la escalabilidad general se verá afectada exponencialmente a medida que aumentan las solicitudes HTTP adicionales.

- Acoplamiento de microservicios con HTTP. Los microservicios empresariales no deben acoplarse con otros microservicios empresariales. Lo ideal es que "desconozcan" la existencia de otros microservicios. Si la aplicación se basa en el acoplamiento de microservicios como en el ejemplo, será casi imposible lograr la autonomía de cada microservicio.

- Error en un microservicio. Si ha implementado una cadena de microservicios vinculados mediante llamadas HTTP y se produce un error en cualquiera de los microservicios (lo que es seguro que ocurra), se producirá un error en toda la cadena de microservicios. Un sistema basado en microservicios se debe diseñar de modo que siga funcionando lo mejor posible cuando se producen errores parciales. Incluso si decide implementar la lógica de cliente que usa los reintentos con retroceso exponencial o mecanismos de disyuntor, cuanto más complejas sean las cadenas de llamadas HTTP, más difícil será implementar una estrategia contra errores basada en HTTP.

De hecho, si sus microservicios internos se comunican mediante la creación de cadenas de solicitudes HTTP tal como se ha descrito, podría argumentarse que tiene una aplicación monolítica, pero una basada en HTTP entre los procesos en lugar de mecanismos de comunicación intraprocesos.

Por lo tanto, para aplicar el principio de autonomía de microservicio y tener una mejor resistencia, se debería minimizar el uso de cadenas de comunicación de solicitud/respuesta entre los microservicios. Se recomienda usar interacción asincrónica solo para la comunicación dentro del microservicio, ya sea mediante el uso de comunicación asincrónica basada en eventos y mensajes, o bien mediante sondeo HTTP (asincrónico) independientemente del ciclo de solicitud/respuesta HTTP original.

El uso de comunicación asincrónica se explica con más detalle más adelante en esta guía, en las secciones [La integración asincrónica del microservicio obliga a su autonomía](communication-in-microservice-architecture.md#asynchronous-microservice-integration-enforces-microservices-autonomy) y [Comunicación asincrónica basada en mensajes](asynchronous-message-based-communication.md).

## <a name="additional-resources"></a>Recursos adicionales

- **Teorema CAP** \
  <https://en.wikipedia.org/wiki/CAP_theorem>

- **Coherencia de los eventos** \
  <https://en.wikipedia.org/wiki/Eventual_consistency>

- **Manual de coherencia de datos** \
  <https://docs.microsoft.com/previous-versions/msp-n-p/dn589800(v=pandp.10)>

- **Martin Fowler. [CQRS (Segregación de responsabilidades de consultas y comandos)]**  \
  <https://martinfowler.com/bliki/CQRS.html>

- **Patrón Materialized View** \
  <https://docs.microsoft.com/azure/architecture/patterns/materialized-view>

- **Charles Row. ACID vs. BASE: el cambio del pH del procesamiento de transacciones de bases de datos** \
  <https://www.dataversity.net/acid-vs-base-the-shifting-ph-of-database-transaction-processing/>

- **Transacción de compensación** \
  <https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction>

- **Udi Dahan. Service Oriented Composition (Composición orientada a servicios)**  \
  <https://udidahan.com/2014/07/30/service-oriented-composition-with-video/>

>[!div class="step-by-step"]
>[Anterior](logical-versus-physical-architecture.md)
>[Siguiente](identify-microservice-domain-model-boundaries.md)

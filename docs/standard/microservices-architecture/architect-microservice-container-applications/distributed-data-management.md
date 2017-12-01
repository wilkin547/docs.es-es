---
title: "Desafíos y soluciones de administración de datos distribuidos"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Desafíos y soluciones de administración de datos distribuidos"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f961475b40c74bf448cff1aeae04ae4866360e52
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="challenges-and-solutions-for-distributed-data-management"></a>Desafíos y soluciones de administración de datos distribuidos

## <a name="challenge-1-how-to-define-the-boundaries-of-each-microservice"></a>Desafío \#1: cómo definir los límites de cada microservicio

Definir los límites de microservicio es probablemente el primer desafío que cualquiera encuentra. Cada microservicio debe ser una parte de la aplicación y cada microservicio debe ser autónomo con todas las ventajas y los desafíos a los que transmite. Pero, ¿cómo se identifica estos límites?

En primer lugar, debe centrarse en los modelos de dominio lógica y los datos relacionados de la aplicación. Debe intentar identificar desacopladas islas de datos y contextos diferentes dentro de la misma aplicación. Cada contexto podría tener un idioma empresarial diferente (términos empresariales diferentes). Los contextos deben definirse y administran de forma independiente. Los términos y las entidades utilizadas en estos contextos diferentes podrían parecer similar, pero podría descubrir que en un contexto determinado, un concepto de negocio con uno se usa para un propósito diferente en otro contexto y podría ser necesario un nombre diferente. Por ejemplo, un usuario puede hacer referencia como un usuario en el contexto de identidad o la pertenencia a, como un cliente en un contexto CRM, como un comprador en un contexto de ordenación y así sucesivamente.

La manera de identificar los límites entre varios contextos de aplicación con un dominio diferente para cada contexto es exactamente cómo puede identificar los límites de cada microservicio de negocios y sus relacionados modelo de dominio y los datos. Siempre intenta minimizar el acoplamiento entre esas microservicios. Esta guía se explica con más detalle acerca de este diseño de modelos de identificación y el dominio en la sección [identifica los límites del modelo de dominio para cada microservicio](#identifying-domain-model-boundaries-for-each-microservice) más tarde.

## <a name="challenge-2-how-to-create-queries-that-retrieve-data-from-several-microservices"></a>Desafío \#2: cómo crear consultas que recuperan datos de varios microservicios

Un segundo problema es cómo implementar las consultas que recuperan datos de varios microservicios, evitando la comunicación locuaz a la microservicios desde aplicaciones cliente remoto. Un ejemplo podría ser una sola pantalla desde una aplicación móvil que necesita para mostrar información de usuario que pertenece a la cesta de la compra, catálogo y microservicios de identidad de usuario. Otro ejemplo sería un informe complejo que implica muchas tablas ubicadas en varios microservicios. La solución adecuada depende de la complejidad de las consultas. Pero en cualquier caso, necesitará una manera de agregar información si desea mejorar la eficacia de las comunicaciones del sistema. Las soluciones más comunes son las siguientes:

**Puerta de enlace de API**. Para la agregación de datos simple de varios microservicios que poseen diferentes bases de datos, el enfoque recomendado es un microservicio de agregación que se conoce como una puerta de enlace de API. Sin embargo, debe tener cuidado acerca de cómo implementar este patrón, ya que puede ser un punto de retracción en el sistema y puede infringir el principio de autonomía de microservicio. Para mitigar esta posibilidad, puede tener varios precisa API puertas de enlace de cada uno centrándose en un área de negocio del sistema o vertical "intervalo". El patrón de puerta de enlace de API se explica con más detalle en la sección en utilizar una puerta de enlace de API más adelante.

**CQRS con tablas de consulta/lectura**. Otra solución de agregación de datos de varios microservicios es el [patrón de vista materializa](https://docs.microsoft.com/azure/architecture/patterns/materialized-view). En este enfoque, generar, de antemano (preparar los datos sin normalizar antes de producen las consultas reales), una tabla de solo lectura con los datos que pertenecen a varios microservicios. La tabla tiene un formato que se adapte a las necesidades de la aplicación cliente.

Tenga en cuenta algo parecido a la pantalla para una aplicación móvil. Si tiene una sola base de datos, puede reunir los datos de esa pantalla mediante una consulta SQL que realiza una combinación compleja que implica varias tablas. Sin embargo, si tiene varias bases de datos, y cada base de datos pertenece a un microservicio diferentes, no se puede consultar las bases de datos y crear una combinación SQL. La consulta compleja se convierte en un desafío. Puede resolver el requisito de uso de un enfoque CQRS: crear una tabla sin normalizar en otra base de datos que se usa solo para las consultas. La tabla puede ser diseñada específicamente para los datos que necesita para la consulta compleja, con una relación uno a uno entre los campos que son necesarias para la pantalla de la aplicación y las columnas de la tabla de consulta. También pueden utilizarse con fines informativos.

Este enfoque no solo soluciona el problema original (cómo realizar consultas y combinación a través de microservicios); también aumenta el rendimiento considerablemente cuando se comparan con una combinación compleja, puesto que ya tiene los datos que necesita la aplicación en la tabla de consulta. Por supuesto, usando el comando y la segregación de responsabilidad de consulta (CQRS) con tablas de consulta/lectura significa el trabajo de desarrollo adicional y debe adoptar la coherencia final. No obstante, los requisitos de rendimiento y alta escalabilidad en [escenarios de colaboración](http://udidahan.com/2011/10/02/why-you-should-be-using-cqrs-almost-everywhere/) (o escenarios competitivos, según el punto de vista) es donde se apliquen CQRS con varias bases de datos.

**"Datos inactivos" en las bases de datos centrales**. Para informes complejos y las consultas que no necesite datos en tiempo real, un enfoque común consiste en exportar los "datos activos" (datos transaccionales de la microservicios) como "datos inactivos" en grandes bases de datos que se utilizan sólo para informes. Dicho sistema de base de datos central puede ser un sistema basado en grandes cantidades de datos, como Hadoop, un almacén de datos como en función de almacenamiento de datos de SQL Azure, o incluso una sola base de datos SQL usan solo para informes (si el tamaño no supondrá un problema).

Tenga en cuenta que esta base de datos centralizada lo se utiliza sólo para consultas e informes que no necesitan datos en tiempo real. Las actualizaciones y las transacciones, como el origen de verdad, original deben estar en los datos de microservicios. La forma en que se sincroniza datos sería mediante el uso de comunicación orientada a eventos (que se describe en las secciones siguientes) o mediante otras herramientas de importación y exportación de infraestructura de base de datos. Si se utiliza la comunicación orientada a eventos, ese proceso de integración sería similar a la manera de que propagar datos como se describió anteriormente para las tablas de consulta CQRS.

Sin embargo, si el diseño de aplicaciones implica agregar constantemente información procedente de varios microservicios para consultas complejas, podría ser un síntoma de un diseño incorrecto: debe ser como aislado como sea posible desde otros microservicios un microservicio. (Esto excluye los informes o análisis que siempre debe usar bases de datos centrales de datos de frío). Tener a menudo este problema podría ser un motivo para fusionar mediante combinación microservicios. Debe equilibrar la autonomía de la evolución y la implementación de cada microservicio con dependencias seguras, la cohesión y agregación de datos.

## <a name="challenge-3-how-to-achieve-consistency-across-multiple-microservices"></a>Desafío \#3: cómo lograr coherencia a través de varios microservicios

Como se mencionó anteriormente, los datos que pertenecen a cada microservicio es privados para ese microservicio y sólo se pueden acceder mediante la API de microservicio. Por lo tanto, un desafío presentado es cómo implementar procesos empresariales de extremo a extremo manteniendo la coherencia entre varias microservicios.

Para analizar este problema, echemos un vistazo a un ejemplo de la [eShopOnContainers hacen referencia a aplicación](http://aka.ms/eshoponcontainers). El catálogo microservicio mantiene información acerca de todos los productos, incluido su nivel estándar. El orden de microservicio administra los pedidos y debe comprobar que un nuevo pedido no supera las existencias de producto del catálogo disponibles. (O el escenario puede implicar la lógica que controla los productos del pedido pendiente). En una versión monolítica hipotética de esta aplicación, el subsistema de ordenación simplemente podría utilizar una transacción ACID para comprobar las existencias disponibles, crear el orden de la tabla Orders y actualizar las existencias disponibles en la tabla Products.

Sin embargo, en una aplicación de microservicios-según las tablas Order y producto pertenecen a sus respectivos microservicios. Ningún microservicio nunca debe incluir las bases de datos que pertenecen a otro microservicio en sus propias transacciones o consultas, tal como se muestra en la figura 4-9.

![](./media/image9.PNG)

**Figura 4-9**. Un microservicio no puede acceder directamente a una tabla en otra microservicio

El orden de microservicio no debe actualizar la tabla de productos directamente, porque es propiedad de la tabla Products la microservicio de catálogo. Para realizar una actualización en el catálogo de microservicio, el orden de microservicio siempre debe usar comunicación asincrónica como eventos de integración (mensaje y comunicación basada en eventos). Se trata cómo la [eShopOnContainers](http://aka.ms/eshoponcontainers) referencia aplicación lleva a cabo este tipo de actualización.

Como se indica por la [teorema CAP](https://en.wikipedia.org/wiki/CAP_theorem), debe elegir entre la disponibilidad y homogeneidad ACID. La mayoría de los escenarios basados en microservicio exigen elevada disponibilidad y escalabilidad en lugar de homogeneidad. Aplicaciones de misión crítica deben permanezca activo y se está ejecutando y los desarrolladores pueden solucionar homogeneidad mediante el uso de técnicas para trabajar con coherencia eventual o débil. Este es el enfoque tomado por la mayoría de las arquitecturas basadas en microservicio.

Además, estilo ACID o transacciones de confirmación en dos fases no están frente a principios de microservicios; bases de datos NoSQL mayoría (por ejemplo, base de datos de Azure Cosmos, MongoDB, etc.) no son compatibles con las transacciones de confirmación en dos fases. Sin embargo, mantener los datos de coherencia entre los servicios y las bases de datos es esencial. Este desafío también está relacionado con la pregunta sobre cómo se propagan los cambios a través de varios microservicios cuando determinados datos deben ser redundante, por ejemplo, cuando necesite tener nombre o la descripción en el catálogo de microservicio y la cesta de compra del producto microservicio.

Una buena solución para este problema consiste en usar coherencia definitiva entre microservicios articulado a través de comunicación controlado por eventos y un sistema de publicación y suscripción. En estos temas se tratan en la sección [comunicación asincrónica orientada a eventos](#async_event_driven_communication) más adelante en esta guía.

## <a name="challenge-4-how-to-design-communication-across-microservice-boundaries"></a>Desafío \#4: cómo diseñar la comunicación a través de límites de microservicio

Comunicarse a través de microservicio límites es un verdadero reto. En este contexto, la comunicación no hace referencia a qué protocolo debe usar (HTTP y REST, AMQP, mensajería y así sucesivamente). En su lugar, abordan el estilo de comunicación que se debe usar y especialmente cómo acoplamiento su microservicios deben ser. Según el nivel de acoplamiento, cuando se produce el error, el impacto de ese error en el sistema varían considerablemente.

En un sistema distribuido como una aplicación basada en microservicios, con tantos artefactos desplazarse y con servicios distribuidos en varios servidores o hosts, componentes se producir un error. Se producen un error parcial e interrupciones incluso mayores, por lo que necesita diseñar su microservicios así como la comunicación entre ellos teniendo en cuenta los riesgos comunes en este tipo de sistemas distribuidos.

Un enfoque popular consiste en implementar HTTP (REST)-según microservicios, debido a su simplicidad. Un enfoque basado en HTTP es absolutamente aceptable; aquí el problema está relacionado con cómo se usan. Si utiliza solicitudes y respuestas HTTP para interactuar con su microservicios desde aplicaciones cliente o desde las puertas de enlace de API, que es correcto. Pero si crea cadenas largas de las llamadas sincrónicas de HTTP a través de microservicios, comunicarse a través de sus límites como si fueron de la microservicios objetos en una aplicación monolítico, se ejecutará la aplicación finalmente problemas.

Por ejemplo, imagine que la aplicación cliente realiza una llamada de API de HTTP para un microservicio individual como el orden de microservicio. Si el orden de microservicio a su vez llama adicional del ciclo de microservicios usando HTTP en la misma solicitud/respuesta, está creando una cadena de llamadas HTTP. Podría parecer razonable inicialmente. Sin embargo, hay consideraciones importantes que tener en cuenta al bajan esta ruta de acceso:

-   Rendimiento de bloqueo y baja. Debido a la naturaleza sincrónica de HTTP, la solicitud original no obtendrá una respuesta hasta que finalicen todas las llamadas HTTP internas. Imagine si el número de estas llamadas aumenta considerablemente y se bloquea al mismo tiempo uno intermedio HTTP llama a un microservicio. El resultado es que se ve afectado el rendimiento y la escalabilidad global se verán afectada exponencialmente como aumento de las solicitudes HTTP adicional.

-   Acoplar microservicios con HTTP. Business microservicios no deben acoplarse con otras microservicios de negocios. Idealmente, debe no "saben" sobre la existencia de otros microservicios. Si la aplicación se basa en microservicios como en el ejemplo de acoplamiento, para lograr la autonomía por microservicio será casi imposible.

-   Error en cualquier un microservicio. Si implementa una cadena de microservicios vinculadas mediante llamadas HTTP, si se produce un error en cualquiera de los microservicios (y finalmente se producirá un error) en toda la cadena de microservicios se producirá un error. Un sistema basado en microservicio se debe diseñar para continuar trabajando, así como posibles durante errores parciales. Incluso si decide implementar lógica de cliente que usa los reintentos con retroceso exponencial o mecanismos de disyuntor, las cadenas de llamadas más complejo HTTP son, cuanto más compleja es implementar una estrategia de error basada en HTTP.

De hecho, si sus microservicios internos se comunican mediante la creación de cadenas de solicitudes HTTP como se describe, se puede argumentar que tiene una aplicación monolítica, pero una basada en HTTP entre los procesos en lugar de mecanismos de comunicación intraprocess.

Por lo tanto, para exigir la autonomía de microservicio y tener una mejor resistencia, debería minimizar el uso de cadenas de comunicación de solicitud/respuesta entre microservicios. Se recomienda usar interacción asincrónica solo para la comunicación entre redes de microservicio, ya sea mediante el uso de comunicación asincrónica basado en eventos y mensajes, o mediante sondeo HTTP independientemente del ciclo de solicitud/respuesta HTTP original.

El uso de comunicación asincrónica se explica con más detalle más adelante en esta guía en las secciones [microservicio asincrónica integración aplica la autonomía de microservicio](#asynchronous-microservice-integration-enforce-microservices-autonomy) y [asincrónico comunicación basada en mensajes](#asynchronous-message-based-communication).

## <a name="additional-resources"></a>Recursos adicionales

-   **Teorema de CAP**
    [*https://en.wikipedia.org/wiki/CAP\_teorema*](https://en.wikipedia.org/wiki/CAP_theorem)

-   **Coherencia definitiva**
    [*https://en.wikipedia.org/wiki/Eventual\_coherencia*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Manual de coherencia de datos**
    [*https://msdn.microsoft.com/library/dn589800.aspx*](https://msdn.microsoft.com/library/dn589800.aspx)

-   **Martin Fowler. CQRS (comando y segregación de responsabilidad de consulta)**
    [*http://martinfowler.com/bliki/CQRS.html*](http://martinfowler.com/bliki/CQRS.html)

-   **Materializar la vista**
    [*https://docs.microsoft.com/azure/architecture/patterns/materialized-view*](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

-   **Charles fila. Vs ACID. BASE: Shifting pH de procesamiento de transacciones de base de datos**
    [*http://www.dataversity.net/acid-vs-base-the-shifting-ph-of-database-transaction-processing/*](http://www.dataversity.net/acid-vs-base-the-shifting-ph-of-database-transaction-processing/)

-   **Transacciones de compensación**
    [*https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction*](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

-   **UDI Dahan. Composición orientadas a servicios**
    [*http://udidahan.com/2014/07/30/service-oriented-composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)


>[!div class="step-by-step"]
[Anterior] (lógico-frente a-física-architecture.md) [siguiente] (identificar-microservicio-dominio-modelo-boundaries.md)

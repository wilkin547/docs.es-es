---
title: "Diseñar una aplicación orientada a servicios de microservicio"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Diseñar una aplicación orientada a servicios de microservicio"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1e1dc919c7e35580576c86b4cf9872b4f8cea2c2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="designing-a-microservice-oriented-application"></a>Diseñar una aplicación orientada a servicios de microservicio

En esta sección se centra en desarrollar una aplicación hipotética empresarial de servidor.

## <a name="application-specifications"></a>Especificaciones de la aplicación

La aplicación hipotética controla las solicitudes mediante la ejecución lógica de negocios, obtener acceso a las bases de datos y, a continuación, devolver respuestas HTML, JSON o XML. Le dirá que la aplicación debe admitir una variedad de clientes, incluidos los exploradores de escritorio que ejecutan aplicaciones de una sola página (SPAs), las aplicaciones web tradicionales, las aplicaciones web móviles y aplicaciones móviles nativas. La aplicación también podría exponer una API de otros fabricantes consumir. También debe ser capaz de integrar su microservicios o las aplicaciones externas de forma asincrónica, por lo que el enfoque ayudará resistencia de la microservicios en el caso de errores parciales.

La aplicación constará de estos tipos de componentes:

-   Componentes de presentación. Se trata de un responsables de controlar la interfaz de usuario y el consumo de servicios remotos.

-   Dominio o la lógica empresarial. Se trata de la lógica de dominio de la aplicación.

-   Lógica de acceso de la base de datos. Se compone de data access components para responsables de obtener acceso a bases de datos (SQL o NoSQL).

-   Lógica de integración de la aplicación. Se trata de un canal de mensajería, principalmente en función de los agentes de mensajes.

La aplicación solicitará alta escalabilidad, permitiendo sus subsistemas verticales escalar horizontalmente de forma autónoma, porque ciertos subsistemas requerirá mayor escalabilidad que otros usuarios.

La aplicación debe ser capaz de implementarse en varios entornos de infraestructura (varias nubes públicas y locales) y debe ser multiplataforma, puede mover fácilmente de Linux en Windows (o viceversa).

## <a name="development-team-context"></a>Contexto de equipo de desarrollo

También se supone lo siguiente sobre el proceso de desarrollo de la aplicación:

-   Tiene varios equipos de desarrollo centrarse en áreas de empresarial diferente de la aplicación.

-   Los miembros del equipo nuevo deben ser más productivos rápidamente, y la aplicación debe ser fácil de entender y modificar.

-   La aplicación tendrá una evolución a largo plazo y reglas de negocio cambiantes.

-   Necesita el buen mantenimiento a largo plazo, lo que significa tener agilidad al implementar los nuevos cambios en el futuro mientras se pueda actualizar varios subsistemas con un impacto mínimo en los otros subsistemas.

-   Desea la integración continua práctica y la implementación continua de la aplicación.

-   Desea aprovechar las ventajas de nuevas tecnologías (marcos, de programación de idiomas, etc.) durante la evolución de la aplicación. ¿Desea realizar migraciones completas de la aplicación cuando se mueven a las nuevas tecnologías, ya podría dar lugar a altos costos y afectar a la capacidad de predicción y la estabilidad de la aplicación.

## <a name="choosing-an-architecture"></a>Elección de una arquitectura

¿Cuál debe ser la arquitectura de implementación de aplicación? Las especificaciones de la aplicación, junto con el contexto de desarrollo, es recomendable que debe diseñar la aplicación, descomponiendo en subsistemas autónomos en forma de colaborar microservicios y contenedores, donde un microservicio es un contenedor.

En este enfoque, cada servicio (contenedor) implementa un conjunto de funciones coherente y sigan relacionados. Por ejemplo, una aplicación puede constar de servicios como el servicio de catálogo, orden de servicio, el servicio de la cesta de compras, servicio de perfiles de usuario, etcetera.

Microservicios comunican utilizando protocolos como HTTP (REST), pero también de forma asincrónica (es decir, AMQP) siempre que sea posible, especialmente cuando propagar las actualizaciones con eventos de integración.

Microservicios se desarrollan y se implementa como contenedores de forma independiente entre sí. Esto significa que un equipo de desarrollo se puede desarrollar e implementar un microservicio determinado sin afectar a otros subsistemas.

Cada microservicio tiene su propia base de datos, lo que le permite totalmente se separa de otras microservicios. Cuando sea necesario, la coherencia entre las bases de datos de diferentes microservicios se logra mediante eventos de integración de nivel de aplicación (a través de un bus de eventos lógicos), tal y como se controla en el comando y la segregación de responsabilidad de consulta (CQRS). Debido a eso, las restricciones de negocio deben contemplar coherencia definitiva entre las múltiples microservicios y bases de datos relacionadas.

### <a name="eshoponcontainers-a-reference-application-for-net-core-and-microservices-deployed-using-containers"></a>eShopOnContainers: una aplicación de referencia de .NET Core y microservicios implementado con contenedores

Para que pueda centrarse en la arquitectura y las tecnologías en lugar de pensar en un dominio de negocio hypothetic que es posible que no sepa, hemos seleccionado un dominio de negocio conocido:; es decir, una aplicación de comercio electrónico simplificado (e-shop) que presenta un catálogo de productos, recibe pedidos de clientes, comprueba el inventario y realiza otras funciones de negocio. Este código de origen de la aplicación basada en el contenedor está disponible en la [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) repositorio de GitHub.

La aplicación consta de varios subsistemas, incluidos varios almacén UI servidores front-end (una aplicación Web y una aplicación nativa móvil), junto con las microservicios de back-end y los contenedores para todas las operaciones de servidor necesarios. Figura 8-1 muestra la arquitectura de la aplicación de referencia.

![](./media/image1.png)

**Figura 8-1**. El eShopOnContainers hacen referencia a aplicación, que muestra una comunicación de cliente a microservicio directa y el bus de eventos

**Entorno de hospedaje**. En la figura 8-1, verá varios contenedores que implementan dentro de un único host de Docker. Que sería el caso cuando se implementa en un único host de Docker con el docker-crear comando. Sin embargo, si está utilizando organizador o clúster de contenedor, cada contenedor pueden ejecutarse en otro host (nodo) y cualquier nodo podría ejecutar cualquier número de contenedores, tal y como se explicó anteriormente en la sección de arquitectura.

**Arquitectura de comunicación**. La aplicación eShopOnContainers utiliza dos tipos de comunicación, según el tipo de la acción funcional (consultas frente a transacciones y actualizaciones):

-   Comunicación de cliente a microservicio directa. Esto se utiliza para las consultas y al aceptar la actualización o comandos transaccionales desde las aplicaciones cliente.

-   Comunicación asincrónica basado en eventos. Esto se produce a través de un bus de eventos para propagar las actualizaciones a través de microservicios o para integrar con aplicaciones externas. El bus de eventos se puede implementar con cualquier tecnología de infraestructura de mensajería del agente como RabbitMQ, o mediante bus de servicio de nivel superiores como Service Bus de Azure, NServiceBus, MassTransit o Brighter.

La aplicación se implementa como un conjunto de microservicios en forma de contenedores. Las aplicaciones cliente pueden comunicarse con los contenedores, así como la comunicación entre microservicios. Como se mencionó, esta arquitectura inicial está usando una arquitectura de comunicación de cliente a microservicio directa, lo que significa que una aplicación cliente puede realizar solicitudes en cada uno de los microservicios directamente. Cada microservicio tiene un extremo público como https://servicename.applicationname.companyname. Si es necesario, cada microservicio puede usar un puerto TCP diferente. En producción, que la dirección URL debería asignar al equilibrador de carga de la microservicios, que distribuye las solicitudes entre las instancias de microservicio disponible.

**Nota importante en vs de puerta de enlace de API. Comunicación directa en eShopOnContainers.** Como se explica en la sección de la arquitectura de esta guía, la arquitectura de comunicación de cliente a microservicio directa puede tener inconvenientes cuando se está generando una aplicación basada en microservicio grande y compleja. Pero puede ser lo suficientemente bueno como para una aplicación pequeña, como en la eShopOnContainers, aplicación, cuyo objetivo es centrarse en una más fácil inicia aplicaciones basados en el contenedor de Docker y no queríamos crear un único monolítico API de puerta de enlace que pueden afectar a la autonomía de desarrollo de microservicios.

Sin embargo, si va a diseñar una aplicación basada en microservicio grande con decenas de microservicios, se recomienda encarecidamente que tener en cuenta el patrón de puerta de enlace de API, tal y como se explica en la sección de arquitectura.
Esta decisión arquitectura se pudieron refactorizar una vez que pensar en las aplicaciones para entornos de producción y frontales fabrican expresamente para clientes remotos. Tener varias las puertas de enlace de API personalizada según el factor de forma de las aplicaciones cliente puede proporcionar ventajas con respecto a la agregación de datos diferente por cada aplicación de cliente más puede ocultar microservicios interno o las API a las aplicaciones cliente y autorizar en ese nivel único. 

Sin embargo y como se ha mencionado, tenga cuidado con grandes monolítico API puertas de enlace y que podría terminar la autonomía de desarrollo de su microservicios.

### <a name="data-sovereignty-per-microservice"></a>Soberanía de datos por microservicio

En la aplicación de ejemplo, cada microservicio posee su propia base de datos o el origen de datos y cada base de datos o el origen de datos se implementa como otro contenedor. Se tomó esta decisión de diseño solo para que sea fácil para un desarrollador obtener el código de GitHub, clonarlo y ábralo en Visual Studio o código de Visual Studio. O bien, como alternativa, facilita compilar las imágenes de Docker personalizadas mediante .NET Core CLI y la CLI de Docker y, a continuación, implementar y ejecutarlos en un entorno de desarrollo de Docker. En cualquier caso, con los contenedores de datos orígenes permite a los desarrolladores compilarán e implementación en cuestión de minutos sin tener que proporcionar una base de datos externo o cualquier otro origen de datos con dependencias en la infraestructura (en la nube o local).

En un entorno de producción real, de alta disponibilidad y escalabilidad, las bases de datos deben basarse en los servidores de base de datos en la nube o local, pero no en contenedores.

Por lo tanto, las unidades de implementación de microservicios (e incluso para bases de datos de esta aplicación) son contenedores de Docker y la aplicación de referencia es una aplicación de contenedor múltiples que acoja microservicios principios.

### <a name="additional-resources"></a>Recursos adicionales

-   **eShopOnContainers repositorio de GitHub. Código de la aplicación de referencia de origen**
    *https://aka.ms/eShopOnContainers/*

## <a name="benefits-of-a-microservice-based-solution"></a>Ventajas de una solución basada en microservicio

Una solución de microservicio en función de este tiene muchas ventajas:

**Cada microservicio es relativamente pequeña, fácil de administrar y desarrollar**. De manera específica:

-   Es fácil para un desarrollador entender y empezar a trabajar rápidamente con buena productividad.

-   Contenedores de inicio rápido, lo que permite a los desarrolladores más productivo.

-   Un IDE como Visual Studio puede cargar proyectos más pequeños con más rapidez, aumentando la productividad de los desarrolladores.

-   Cada microservicio puede diseñado, desarrollarse e implementarse independientemente de otros microservicios, que proporciona agilidad porque es más fácil de implementar nuevas versiones de microservicios con frecuencia.

**Es posible escalar horizontalmente áreas individuales de la aplicación**. Por ejemplo, el servicio de catálogo o el servicio de la cesta de compras deba ser escalado, pero no el proceso de pedido. Una infraestructura de microservicios será mucho más eficaz con respecto a los recursos que usa mientras se escala horizontalmente, lo que sería una arquitectura monolítica.

**Puede dividir el trabajo entre varios equipos de desarrollo**. Cada servicio puede ser propiedad de un equipo de desarrollo único. Cada equipo puede administrar, desarrollar, implementar y escalar su servicio, independientemente del resto de los equipos.

**Problemas son más aislados**. Si hay un problema en un servicio, solo a ese servicio inicialmente se ve afectado (excepto cuando se usa el diseño incorrecto con dependencias directas entre microservicios) y pueden continuar con otros servicios controlar las solicitudes. En cambio, un componente en mal estado en una arquitectura de implementación monolítico puede aportar hacia abajo todo el sistema, especialmente al implica recursos, como una pérdida de memoria. Además, cuando se ha resuelto un problema en un microservicio, puede implementar simplemente la microservicio afectado sin influir en el resto de la aplicación.

**Puede utilizar las tecnologías más recientes**. Ya puede empezar a desarrollar servicios de forma independiente y ejecutarlas en paralelo (gracias a contenedores y .NET Core), puede comenzar a usar las últimas tecnologías y marcos de trabajo de forma oportuna en lugar de quedarse atascado en una pila o marco de trabajo para el conjunto anterior aplicación.

## <a name="downsides-of-a-microservice-based-solution"></a>Desventajas de una solución basada en microservicio

Una solución de microservicio según así también tiene algunas desventajas:

**Aplicación distribuida**. Distribuir la aplicación, agrega una complejidad para los desarrolladores cuando se diseñar y crear los servicios. Por ejemplo, los programadores deben implementar interservicios comunicación mediante protocolos como HTTP o AMPQ, que agrega complejidad para las pruebas y control de excepciones. También agrega latencia en el sistema.

**Complejidad de la implementación**. Una aplicación que tiene docenas de tipos de microservicios y que necesitan alta escalabilidad (debe ser capaz de crear varias instancias por cada servicio y el equilibrio de dichos servicios a través de varios hosts) significa un alto grado de complejidad de la implementación para la administración y operaciones de TI. Si no se usa una infraestructura orientada a servicios de microservicio (por ejemplo, un orchestrator y programador), que la complejidad adicional puede requerir mucho más los esfuerzos de desarrollo de la propia aplicación de negocios.

**Las transacciones atómicas**. Las transacciones atómicas entre varios microservicios normalmente no son posibles. Los requisitos empresariales deben adoptar coherencia definitiva entre varios microservicios.

**Aumentar los recursos globales que se necesitan** (total de memoria, las unidades y recursos de red para todos los hosts o servidores). En muchos casos, al reemplazar una aplicación monolítica con un enfoque microservicios, la cantidad de recursos globales necesaria para la nueva aplicación basada en microservicio será mayor que las necesidades de infraestructura de la aplicación monolítica original. Esto es porque el mayor grado de granularidad y servicios distribuidos requiere recursos de índole más globales. Sin embargo, dado el bajo costo de recursos en general y la ventaja de poder escalar horizontalmente solo determinadas áreas de la aplicación en comparación con los costos a largo plazo de hora de desarrollar aplicaciones monolíticas, el aumento del uso de recursos es normalmente un buen equilibrio para grandes, aplicaciones a largo plazo.

**Problemas de comunicación directa client‑to‑microservice**. Cuando la aplicación es grande, con docenas de microservicios, hay problemas y limitaciones si la aplicación requiere las comunicaciones de cliente a microservicio directa. Un problema es un error de coincidencia potencial entre las necesidades del cliente y las API expuestas por cada uno de los microservicios. En algunos casos, la aplicación cliente deba hacer varias solicitudes independientes para crear la interfaz de usuario, que puede ser ineficaz a través de Internet y pueden resultar poco a través de una red móvil. Por lo tanto, se deben minimizar las solicitudes de la aplicación cliente para el sistema back-end.

Otro problema con las comunicaciones de cliente a microservicio directa es que algunos microservicios pueden estar usando los protocolos que no son aptos para la Web. Un servicio puede usar un protocolo binario, mientras que otro servicio puede utilizar mensajería de AMQP. Estos protocolos no son firewall‑friendly y son útiles internamente. Normalmente, una aplicación debe utilizar protocolos como HTTP y WebSockets para la comunicación fuera del firewall.

Todavía otra desventaja con este enfoque client‑to‑service directa es que resulta difícil refactorizar los contratos para los microservicios. Con el tiempo a los desarrolladores posible que desee cambiar la forma en que el sistema se divide en servicios. Por ejemplo, puede combinar los dos servicios o dividir un servicio en dos o más servicios. Sin embargo, si los clientes se comunican directamente con los servicios, realizar este tipo de refactorización puede interrumpir la compatibilidad con aplicaciones de cliente.

Como se mencionó en la sección de arquitectura, al diseñar y crear una aplicación compleja basada en microservicios, considere el uso de varias las puertas de enlace de API específica en lugar de al enfoque más sencillo de comunicación directa client‑to‑microservice.

**Creación de particiones de la microservicios**. Por último, independientemente del método que seguir para que la arquitectura de microservicio, otro desafío consiste en decidir cómo dividir una aplicación to-end en varios microservicios. Como se indicó en la sección de la arquitectura de la guía, hay varias técnicas y enfoques que puede realizar. Básicamente, debe identificar las áreas de la aplicación que se separa de las demás áreas y que tienen un número reducido de dependencias. En muchos casos, esto se alinea los servicios de creación de particiones por caso de uso. Por ejemplo, en nuestra aplicación e shop, tenemos un servicio de ordenación que se encarga de toda la lógica de negocios relacionados con el proceso de pedido. También tenemos el servicio del catálogo y el servicio de la cesta de compras que implementan otras capacidades. Idealmente, cada servicio debe tener solo un pequeño conjunto de responsabilidades. Esto es similar al principio de responsabilidad única (SRP) aplicado a las clases, que indica que una clase debe tener sólo un motivo para cambiarlo. Pero en este caso, trata microservicios, por lo que el ámbito será mayor que una sola clase. Más de todo un microservicio tiene que ser completamente autónomo, de principio a fin, incluida la responsabilidad de sus propios orígenes de datos.

## <a name="external-versus-internal-architecture-and-design-patterns"></a>Externa frente a los patrones de arquitectura y el diseño internos

La arquitectura externa es la arquitectura de microservicio compuesta por varios servicios, siguiendo los principios descritos en la sección de la arquitectura de esta guía. Sin embargo, según la naturaleza de cada microservicio e independiente de la arquitectura de alto nivel microservicio que elija, es común y a veces es aconsejable tener distintas arquitecturas internas, basados en patrones diferentes, para diferentes microservicios. Incluso pueden utilizar el microservicios diversas tecnologías y lenguajes de programación. Figura 8-2 muestra esta diversidad.

![](./media/image2.png)

**Figura 8-2**. Externa frente a la arquitectura interna y diseño

Por ejemplo, en nuestro *eShopOnContainers* microservicios de perfil de ejemplo, el catálogo, la cesta de compras y usuario son simples (básicamente, los subsistemas de CRUD). Por lo tanto, su arquitectura interna y el diseño es sencillo. Sin embargo, puede que tenga otros microservicios, como la ordenación microservicio, que es más complejo y representa las reglas de negocios cambiantes con un alto grado de complejidad del dominio. En estos casos, puede implementar modelos más avanzados dentro de un microservicio determinado, como las que se define con los enfoques de diseño basado en dominio (DDD), como se hace el *eShopOnContainers* orden microservicio. (Se tratarán estos patrones DDD más adelante la sección que explica la implementación de la *eShopOnContainers* ordenación microservicio.)

Otra razón para una tecnología distinta por microservicio podría ser la naturaleza de cada microservicio. Por ejemplo, podría ser mejor usar un lenguaje de programación funcional como F\#, o incluso un lenguaje como R si desea usar AI y dominios, en lugar de un lenguaje de programación más orientada a objetos como C de aprendizaje automático\#.

La conclusión es que cada microservicio puede tener una arquitectura interna diferente basándose en patrones de diseño diferentes. Microservicios no todas las deben implementarse mediante patrones DDD avanzados, ya podría ser excesiva de ingeniería ellos. Del mismo modo, no deberían implementarse microservicios complejos con lógica de negocios cambiante como componentes CRUD o puede acabar con código de baja calidad.



## <a name="the-new-world-multiple-architectural-patterns-and-polyglot-microservices"></a>El nuevo mundo: varios modelos arquitectónicos y microservicios polyglot

Hay muchos patrones arquitectónicos utilizados por los programadores y arquitectos de software. Los siguientes son algunos (combinación de estilos de arquitectura y patrones de arquitectura):

-   Simple CRUD, nivel único, una capa.

-   [Tradicional N capas](https://msdn.microsoft.com/en-us/library/ee658109.aspx#Layers).

-   [Dominio controlada por diseño en capas N](https://blogs.msdn.microsoft.com/cesardelatorre/2011/07/03/published-first-alpha-version-of-domain-oriented-n-layered-architecture-v2-0/).

-   [Limpiar arquitectura](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html) (como se utiliza con [eShopOnWeb](http://aka.ms/WebAppArchitecture))

-   [Comando y consultar la segregación de responsabilidad](https://martinfowler.com/bliki/CQRS.html) (CQRS).

-   [Arquitectura controlada por eventos](https://en.wikipedia.org/wiki/Event-driven_architecture) (EDA).

También puede compilar microservicios con muchas tecnologías y lenguajes, como las API Web de ASP.NET Core, NancyFx, ASP.NET Core SignalR (disponible con .NET Core 2), F\#, Node.js, Python, Java, C++, GoLang y mucho más.

Lo importante es que ningún patrón de arquitectura determinada o estilo ni cualquier tecnología en particular, es adecuado para todas las situaciones. Figura 8-3 muestra algunos enfoques y las tecnologías (aunque no en ningún orden concreto) que podía utilizarse en microservicios diferentes.

![](./media/image3.png)

**Figura 8-3**. Los patrones arquitectónicos múltiple y el mundo microservicios polyglot

Como se muestra en figura 8-3, en aplicaciones formada por muchas microservicios (limitado contextos en terminología de diseño basado en dominio, o simplemente "subsistemas" como microservicios autónomo), podría implementar cada microservicio de forma diferente. Cada uno de ellos podría cuentan con un patrón de arquitectura diferente y usar distintos idiomas y las bases de datos según la naturaleza de la aplicación, los requisitos empresariales y prioridades. En algunos casos el microservicios podrían ser similar. Pero que no es normalmente el caso, porque el límite del contexto y los requisitos de cada subsistema normalmente son diferentes.

Por ejemplo, para una aplicación de mantenimiento CRUD simple, no podría no sentido diseñar e implementar patrones DDD. Pero para el dominio principal o el negocio principal, es posible que deba aplicar patrones más avanzadas para abordar la complejidad de negocio con reglas de negocios cambiantes.

Especialmente cuando se trabaja con aplicaciones de gran tamaño compuestas por varios subsistemas, no se debe aplicar una única arquitectura de nivel superior en función de un modelo de arquitectura de inicio único. Por ejemplo, CQRS no se debe aplicar como una arquitectura de nivel superior para una aplicación completa, pero podría ser útil para un conjunto específico de servicios.

No hay ninguna solución mágica o un patrón de arquitectura correcta para cada caso especificado. No puede tener "un patrón de arquitectura descarte todos ellos." Dependiendo de las prioridades de cada microservicio, debe elegir un enfoque diferente para cada uno, como se explica en las secciones siguientes.


>[!div class="step-by-step"]
[Anterior] (index.md) [siguiente] (datos-controlada por-crud-microservice.md)

---
title: "Comunicación de cliente a microservicio directa en comparación con el patrón de puerta de enlace de API"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Comunicación de cliente a microservicio directa en comparación con el patrón de puerta de enlace de API"
keywords: Docker, Microservicios, ASP.NET, contenedor, puerta de enlace de API
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c8227ec47888c7cf361f34c4c85a09c0666f886e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="direct-client-to-microservice-communication-versus-the-api-gateway-pattern"></a>Comunicación de cliente a microservicio directa en comparación con el patrón de puerta de enlace de API

En una arquitectura microservicios, cada microservicio expone un conjunto de extremos de fine‑grained (normalmente). Este hecho puede afectar a la comunicación client‑to‑microservice, como se explica en esta sección.

## <a name="direct-client-to-microservice-communication"></a>Comunicación de cliente a microservicio directa

Un posible enfoque es usar una arquitectura de comunicación de cliente a microservicio directa. En este enfoque, una aplicación cliente puede realizar solicitudes directamente a algunas de las microservicios, tal como se muestra en la figura 4-12.

![](./media/image12.png)

**Figura 4-12**. Uso de una arquitectura de comunicación de cliente a microservicio directa

En este enfoque. cada microservicio tiene un extremo público, a veces con un puerto TCP diferente para cada microservicio. Un ejemplo de una dirección URL para un servicio determinado podría ser la siguiente dirección URL en Azure:

<http://eshoponcontainers.westus.cloudapp.Azure.com:88 />

En un entorno de producción basado en un clúster, que la dirección URL debería asignar al equilibrador de carga que se utiliza en el clúster, que a su vez distribuye las solicitudes entre el microservicios. En entornos de producción, podría tener un controlador de entrega de aplicaciones (ADC) como [puerta de enlace de aplicaciones de Azure](https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction) entre los microservicios e Internet. Esto actúa como una capa transparente que no sólo realiza el equilibrio de carga, pero protege sus servicios, ya que ofrece la terminación SSL. Esto mejora la carga de los hosts mediante la descarga de terminación SSL de la CPU y otros derechos de enrutamientos para la puerta de enlace de aplicaciones de Azure. En cualquier caso, un equilibrador de carga y el ADC son transparentes desde un punto de la arquitectura de aplicación lógica de vista.

Una arquitectura de comunicación de cliente a microservicio directa podría bastar para una pequeña aplicación basada en microservicio, especialmente si la aplicación cliente es una aplicación de servidor web como una aplicación de ASP.NET MVC. Sin embargo, al compilar aplicaciones grandes y complejas en función de microservicio (por ejemplo, al administrar docenas de tipos de microservicio), y sobre todo cuando las aplicaciones de cliente son aplicaciones móviles remotas o las aplicaciones web SPA, este enfoque enfrenta a algunos de los problemas.

Al desarrollar una aplicación de gran tamaño en función de microservicios, tenga en cuenta las siguientes preguntas:

-   *¿Cómo pueden aplicaciones cliente minimizar el número de solicitudes en el back-end y reducir la comunicación locuaz a microservicios varios?*

Interactuar con varios microservicios para crear una pantalla de interfaz de usuario única, aumenta el número de idas y vueltas a través de Internet. Esto aumenta la latencia y la complejidad en el lado de la interfaz de usuario. Idealmente, las respuestas se deberían agregar eficazmente en el lado del servidor, esto reduce la latencia, ya que varios fragmentos de datos vuelven a estar en paralelo y alguna interfaz de usuario puede mostrar los datos tan pronto como está listo.

-   *¿Cómo se puede controlar las preocupaciones transversales como autorización, transformaciones de datos y enviar solicitud dinámica?*

Implementación de seguridad y problemas de corte del cruce como seguridad y la autorización en cada microservicio pueden requerir un esfuerzo de desarrollo significativo. Un posible enfoque es que los servicios en el host Docker o interna del clúster, con el fin de restringir el acceso directo a ellos desde el exterior y para implementar estas inquietudes transversales en un lugar centralizado, como una puerta de enlace de API.

-   *¿Cómo pueden las aplicaciones cliente comunicarse con servicios que usan protocolos compatible con Internet?*

Normalmente, protocolos usados en el lado del servidor (por ejemplo, AMQP o protocolos binarios) no se admiten en aplicaciones cliente. Por lo tanto, las solicitudes deben realizarse a través de protocolos como HTTP/HTTPS y convierte a los demás protocolos posteriormente. A *man-in-the-middle* enfoque puede ayudar a esta situación.

-   *¿Cómo puede dar forma a una fachada realizada especialmente para las aplicaciones móviles?*

La API de microservicios varios no podría ser bien diseñada para las necesidades de las diferentes aplicaciones cliente. Por ejemplo, las necesidades de una aplicación móvil pueden ser diferentes que las necesidades de una aplicación web. Para las aplicaciones móviles, tendrá que optimizar aún más para que las respuestas de datos pueden ser más eficaces. Puede hacerlo mediante la agregación de datos de varios microservicios y devolver un único conjunto de datos y, a veces, lo que elimina los datos en la respuesta que no es necesaria para la aplicación móvil. Y, por supuesto, puede comprimir los datos. Una vez más, una fachada o API entre la aplicación móvil y el microservicios puede ser conveniente para este escenario.

## <a name="using-an-api-gateway"></a>Usar una puerta de enlace de API

Al diseñar y crear aplicaciones basadas en microservicio de grandes o complejas con varios clientes de aplicaciones, puede ser un buen método para tener en cuenta un [puerta de enlace de API](http://microservices.io/patterns/apigateway.html). Se trata de un servicio que proporciona un único punto de entrada para determinados grupos de microservicios. Es similar a la [patrón de fachada](https://en.wikipedia.org/wiki/Facade_pattern) desde el diseño de object‑oriented, pero en este caso, es parte de un sistema distribuido. El patrón de puerta de enlace de API en ocasiones también se conoce como "back-end para front-end" [(BFF)](http://samnewman.io/patterns/architectural/bff/) porque se genera al pensar en las necesidades de la aplicación cliente.

Figura 4-13 muestra cómo puede incorporar una puerta de enlace de API personalizada en una arquitectura basada en microservicio.
Es importante resaltar que en ese diagrama, que va a utilizar un único servicio de puerta de enlace de API personalizado con conexión a varios y las aplicaciones de cliente diferente. Que hecho puede ser un riesgo importante porque el servicio de puerta de enlace de API se creciendo y evolucionando se basa en muchos de los diferentes requisitos de las aplicaciones cliente. Finalmente, aumentará debido a las distintas necesidades y eficazmente podría ser bastante similar a una aplicación monolítico o servicio monolítico. Para eso están muy se recomienda dividir la puerta de enlace de API en varios servicios o varios más pequeños API puertas de enlace, uno por cada tipo de factor de forma, por ejemplo.

![](./media/image13.png)

**Figura 4-13**. Usar una puerta de enlace de API implementa como un servicio de API Web personalizado

En este ejemplo, la puerta de enlace de API se implementa como un servicio de API Web personalizado que se ejecuta como un contenedor.

Como se mencionó, debe implementar varias puertas de enlace de API para que pueda tener una fachada diferentes para las necesidades de cada aplicación de cliente. Cada puerta de enlace de API puede proporcionar otra API adaptados para cada aplicación de cliente, posiblemente incluso según el factor de forma de cliente mediante la implementación de código que debajo llamadas varios microservicios interna del adaptador específico.

Puesto que una puerta de enlace de API personalizada es normalmente un agregador de datos, debe tener cuidado con él. No suele ser una buena idea de tener una única puerta de enlace de API agregar todos los microservicios internos de la aplicación. Si es así, actúa como un agregador monolítico o orchestrator e infringe la autonomía de microservicio por todos los microservicios de acoplamiento. Por lo tanto, las puertas de enlace de API se deberían segregar en función de los límites del negocio y no actúa como un agregador para toda la aplicación.

En ocasiones, una puerta de enlace de API específico puede ser también un microservicio por sí mismos e incluso tener un dominio o nombre de la empresa y datos relacionados. Con los límites de la puerta de enlace del API dictados por el negocio o dominio le ayudará a obtener un mejor diseño.

Granularidad en el nivel de puerta de enlace de API puede ser especialmente útil para aplicaciones más avanzadas, compuestas interfaz de usuario en función de microservicios, dado que el concepto de una puerta de enlace de API específica es similar a un servicio de composición de la interfaz de usuario. Hablar sobre esto más adelante en el [crear la interfaz de usuario compuesta basado en microservicios](#creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices).

Por lo tanto, para muchas aplicaciones de tamaño por medio y grande, mediante una puerta de enlace de API personalizada es normalmente un enfoque adecuado, pero no como un único agregador monolítico o único central personalizado API de puerta de enlace.

Otro enfoque consiste en utilizar un producto como [administración de API de Azure](https://azure.microsoft.com/services/api-management/) tal como se muestra en la figura 4-14. Este enfoque no sólo resuelve sus necesidades de puerta de enlace de API, sino que también proporciona características como la recopilación de información de las API. Si está utilizando una solución de administración de API, una puerta de enlace de API es sólo un componente dentro de dicha solución de administración de API completa.

![](./media/image14.png)

**Figura 4-14**. Uso de administración de API de Azure para la puerta de enlace de API

En este caso, cuando usando un producto como administración de API de Azure, el hecho de que es posible que tenga una sola puerta de enlace de API no es tan arriesgado porque estos tipos de puertas de enlace de API son "más estrechos", lo que significa que no implementan código C# personalizado que podría evolucionar hacia un monolítico componente. 

Este tipo de producto más actúa como un proxy inverso para la comunicación de entrada, donde se puede filtrar las API desde el microservicios interno y aplicar la autorización a las API publicadas en este nivel solo también.

La información disponible en un ayuda de sistema de administración de API obtener una descripción de cómo se usan las API y cómo están realizando. Para ello, lo que le permite ver cerca de los informes de análisis en tiempo real e identificar las tendencias que podrían afectar a su negocio. Además, puede tener registros sobre la actividad de solicitud y respuesta para su posterior análisis en línea y sin conexión.

Con la administración de API de Azure, puede proteger sus API con una clave, un símbolo (token) y el filtrado de IP. Estas características le permiten aplicar cuotas flexibles y específicas y límites de frecuencia, modificar la forma y el comportamiento de las API mediante directivas y mejorar el rendimiento con las respuestas en caché.

En esta guía y la aplicación de ejemplo de referencia (eShopOnContainers), nos estamos limitar la arquitectura para una arquitectura más sencilla y un objeto personalizada en contenedores para que pueda centrarse en los contenedores sin formato sin utilizar productos de PaaS, como administración de API de Azure. Pero con grandes microservicio-las aplicaciones que se implementan en Microsoft Azure, le recomendamos que revise y adoptar la administración de API de Azure como base para las puertas de enlace de API.

## <a name="drawbacks-of-the-api-gateway-pattern"></a>Desventajas del patrón de puerta de enlace de API

-   El inconveniente más importante es que, al implementar una puerta de enlace de API, se acoplar ese nivel con el microservicios interno. Acoplamiento parecido a esto podría provocar problemas graves para la aplicación. Clemens Vaster, arquitecto en el equipo de Service Bus de Azure, hace referencia a esta dificultad posible como "ESB nuevo" en su "[mensajería y Microservicios](https://www.youtube.com/watch?v=rXi5CLjIQ9k)" sesión al GOTO 2016.

-   Usando una puerta de enlace de API de microservicios crea un adicional posible punto de error único.

-   Una puerta de enlace de API puede introducir el tiempo de respuesta mayor debido a la llamada de red adicional. Sin embargo, esta llamada adicional normalmente tiene menor impacto de tener un cliente de la interfaz es demasiado locuaz llamar directamente a la microservicios interno.

-   Si no escalar horizontalmente correctamente, la puerta de enlace de API puede convertirse en un cuello de botella.

-   Una puerta de enlace de API requiere un costo de desarrollo adicionales y mantenimiento futuro si incluye lógica personalizada y agregación de datos. Los desarrolladores deben actualizar la puerta de enlace de API con el fin de exponer puntos de conexión de cada microservicio. Además, los cambios de implementación en el microservicios interno pueden provocar cambios de código en el nivel de puerta de enlace de API. Sin embargo, si la puerta de enlace de API simplemente es aplicar seguridad, registro y control de versiones (como al utilizar administración de API de Azure), este costo de desarrollo adicional podría no ser aplicable.

-   Si la puerta de enlace de API se ha desarrollado por un único equipo, puede haber un cuello de botella de desarrollo. Este es otro motivo por qué es un enfoque más adecuado tener varias precisa API las puertas de enlace que responda a las necesidades de cliente diferente. También puede separar la puerta de enlace de API internamente en varias áreas o capas que pertenecen a los diferentes equipos que trabajan en el microservicios interno.

## <a name="additional-resources"></a>Recursos adicionales

-   **Charles Richardson. Patrón: Puerta de enlace de API / back-end para front-end**
    [*http://microservices.io/patterns/apigateway.html*](http://microservices.io/patterns/apigateway.html)

-   **Administración de API de Azure**
    [*https://azure.microsoft.com/services/api-management/*](https://azure.microsoft.com/services/api-management/)

-   **UDI Dahan. Composición orientadas a servicios**\
    [*http://UdiDahan.com/2014/07/30/Service-Oriented-Composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)

-   **Clemens Vasters. Mensajería y Microservicios en 2016 GOTO** (vídeo) [ *https://www.youtube.com/watch?v=rXi5CLjIQ9k*](https://www.youtube.com/watch?v=rXi5CLjIQ9k)


>[!div class="step-by-step"]
[Anterior] (identificar-microservicio-dominio-modelo-boundaries.md) [siguiente] (comunicación-en-microservicio-architecture.md)

---
title: Comunicación directa de cliente a microservicio frente al patrón de puerta de enlace de API
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Comunicación directa de cliente a microservicio frente al patrón de puerta de enlace de API
keywords: Docker, microservicios, ASP.NET, contenedor, puerta de enlace de API
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fa3f4bb97cf942ee7698b1efa1dcd09b3f2ca571
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="direct-client-to-microservice-communication-versus-the-api-gateway-pattern"></a>Comunicación directa de cliente a microservicio frente al patrón de puerta de enlace de API

En una arquitectura de microservicios, cada microservicio expone un conjunto de puntos de conexión específicos (normalmente). Este hecho puede afectar a la comunicación entre el cliente y el microservicio, tal como se explica en esta sección.

## <a name="direct-client-to-microservice-communication"></a>Comunicación directa de cliente a microservicio

Un posible enfoque es usar una arquitectura de comunicación directa de cliente a microservicio. En este enfoque, una aplicación cliente puede realizar solicitudes directamente a algunos de los microservicios, tal como se muestra en la figura 4-12.

![](./media/image12.png)

**Figura 4-12**. Uso de una arquitectura de comunicación directa de cliente a microservicio

En este enfoque, cada microservicio tiene un punto de conexión público, a veces con un puerto TCP distinto para cada microservicio. La siguiente dirección URL de Azure sería un ejemplo de URL de un servicio determinado:

<http://eshoponcontainers.westus.cloudapp.azure.com:88/>

En un entorno de producción basado en un clúster, la dirección URL anterior estaría asignada al equilibrador de carga que se utiliza en el clúster, que a su vez distribuye las solicitudes entre los microservicios. En entornos de producción, se puede tener un controlador de entrega de aplicaciones (ADC) como [Azure Application Gateway](https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction) entre los microservicios e Internet. Este controlador actúa como una capa transparente que no solo realiza el equilibrio de carga, sino que también protege sus servicios, ya que ofrece terminación SSL. Esto mejora la carga de los hosts, puesto que Azure Application Gateway se descarga de la terminación SSL y de otras tareas de enrutamiento que consumen mucha CPU. En cualquier caso, un equilibrador de carga y el ADC son transparentes desde un punto de vista de la arquitectura de aplicación lógica.

Una arquitectura de comunicación directa de cliente a microservicio podría bastar para una pequeña aplicación basada en microservicio, especialmente si se trata de una aplicación web del lado cliente como, por ejemplo, una aplicación de ASP.NET MVC. Pero al compilar aplicaciones grandes y complejas basadas en microservicios (por ejemplo, al administrar docenas de tipos de microservicio) y, sobre todo, cuando las aplicaciones cliente son aplicaciones móviles remotas o aplicaciones web SPA, este enfoque se enfrenta a algunos problemas.

Al desarrollar una aplicación de gran tamaño basada en microservicios, considere las siguientes preguntas:

-   *¿Cómo pueden las aplicaciones cliente minimizar el número de solicitudes al back-end y reducir el exceso de comunicación con varios microservicios?*

Interactuar con varios microservicios para crear una única pantalla de interfaz de usuario aumenta el número de recorridos de ida y vuelta a través de Internet. Esto aumenta la latencia y la complejidad en el lado de la interfaz de usuario. Idealmente, las respuestas se deberían agregar eficazmente en el lado del servidor (esto reduce la latencia, ya que varios fragmentos de datos regresan en paralelo y alguna interfaz de usuario puede mostrar los datos tan pronto como están listos).

-   *¿Cómo se pueden controlar cuestiones transversales como la autorización, las transformaciones de datos y la distribución de solicitudes dinámicas?*

La implementación de seguridad y cuestiones transversales como la seguridad y la autorización en cada microservicio pueden requerir un esfuerzo de desarrollo importante. Un posible enfoque es tener esos servicios en el host Docker o en un clúster interno para así restringir el acceso directo a ellos desde el exterior e implementar estas cuestiones transversales en un lugar centralizado, como puede ser una puerta de enlace de API.

-   *¿Cómo pueden las aplicaciones cliente comunicarse con servicios que usan protocolos no compatible con Internet?*

Normalmente, los protocolos usados en el lado del servidor (por ejemplo, AMQP o protocolos binarios) no se admiten en aplicaciones cliente. Por lo tanto, las solicitudes deben realizarse a través de protocolos como HTTP/HTTPS y convertirse posteriormente a los demás protocolos. Un enfoque *man-in-the-middle* puede ser útil en esta situación.

-   *¿Cómo se puede dar forma a una fachada realizada especialmente para las aplicaciones móviles?*

El diseño de la API de varios microservicios podría no adaptarse a las necesidades de diferentes aplicaciones cliente. Por ejemplo, las necesidades de una aplicación móvil pueden ser diferentes a las necesidades de una aplicación web. Para las aplicaciones móviles, la optimización debe ser incluso mayor para que las respuestas de datos sean más eficaces. Para lograr esto, puede agregar los datos de varios microservicios y devolver un único conjunto de datos y, a veces, eliminar los datos de la respuesta que no son necesarios para la aplicación móvil. Y, por supuesto, puede comprimir los datos. Una vez más, una fachada o API entre la aplicación móvil y los microservicios puede ser conveniente para este escenario.

## <a name="using-an-api-gateway"></a>Uso de una puerta de enlace de API

Al diseñar y crear aplicaciones basadas en microservicios grandes o complejas con varias aplicaciones cliente, un buen planteamiento podría ser una [puerta de enlace de API](https://microservices.io/patterns/apigateway.html). Se trata de un servicio que proporciona un punto de entrada único para determinados grupos de microservicios. Es similar al [patrón de fachada](https://en.wikipedia.org/wiki/Facade_pattern) del diseño orientado a objetos, pero en este caso es parte de un sistema distribuido. En ocasiones, el patrón de puerta de enlace de API también se conoce como "back-end para front-end" [(BFF)](https://samnewman.io/patterns/architectural/bff/) porque en la compilación se tienen en cuenta las necesidades de la aplicación cliente.

La figura 4-13 muestra el encaje de una puerta de enlace de API personalizada en una arquitectura basada en microservicios.
Es importante resaltar que en ese diagrama se utiliza un único servicio de puerta de enlace de API personalizado con conexión a varias aplicaciones de cliente distintas. Ese hecho puede suponer un riesgo importante porque el servicio de puerta de enlace de API irá creciendo y evolucionando en función de los muchos requisitos de las aplicaciones cliente. Finalmente, se verá sobredimensionado debido a las distintas necesidades y en la práctica podría ser bastante similar a una aplicación o un servicio monolíticos. Por eso es muy recomendable dividir la puerta de enlace de API en varios servicios o varias puertas de enlace de API más pequeñas, por ejemplo, uno por cada tipo de factor de forma.

![](./media/image13.png)

**Figura 4-13**. Uso de una puerta de enlace de API implementada como un servicio API Web personalizado

En este ejemplo, la puerta de enlace de API se implementa como un servicio API Web personalizado que se ejecuta como un contenedor.

Como se ha mencionado, debe implementar varias puertas de enlace de API para poder disponer de una fachada diferente para las necesidades de cada aplicación cliente. Cada puerta de enlace de API puede proporcionar una API distinta adaptada a cada aplicación cliente, posiblemente basada incluso en el factor de forma de cliente, mediante la implementación de código adaptador que llame por debajo a varios servicios internos.

Puesto que una puerta de enlace de API personalizada es normalmente un agregador de datos, hay que tener cuidado con ella. No suele ser una buena idea de tener una única puerta de enlace de API en la que se agreguen todos los microservicios internos de la aplicación. Si es así, actúa como un orquestador o agregador monolítico e infringe la autonomía de los microservicios al acoplarlos todos. Por lo tanto, las puertas de enlace de API se deberían segregar en función de los límites del negocio y no deberían actuar como un agregador para toda la aplicación.

En ocasiones, una puerta de enlace de API específica puede ser también un microservicio por sí misma, e incluso tener un dominio o nombre de empresa y datos relacionados. El tener los límites de la puerta de enlace de API dictados por el negocio o el dominio le ayudará a lograr un mejor diseño.

La granularidad en el nivel de puerta de enlace de API puede ser especialmente útil para aplicaciones de interfaz de usuario compuesta más avanzadas basadas en microservicios, dado que el concepto de una puerta de enlace de API específica es similar a un servicio de composición de la interfaz de usuario. Hablaremos de esto más adelante en [Crear la interfaz de usuario compuesta en función de microservicios](#creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices).

Por lo tanto, para muchas aplicaciones de tamaño medio y grande, la utilización de una puerta de enlace de API personalizada es normalmente un enfoque adecuado, pero no como un único agregador monolítico ni una única puerta de enlace de API personalizada central.

Otro enfoque consiste en utilizar un producto como [Azure API Management](https://azure.microsoft.com/services/api-management/) tal como se muestra en la figura 4-14. Este enfoque no solo resuelve sus necesidades de puerta de enlace de API, sino que también proporciona características como la recopilación de información de las API. Si está utilizando una solución de administración de API, una puerta de enlace de API es solo un componente dentro de toda esa solución de administración de API.

![](./media/image14.png)

**Figura 4-14**. Uso de Azure API Management para la puerta de enlace de API

En este caso, cuando se usa un producto como Azure API Management, el hecho de tener una sola puerta de enlace de API no es tan arriesgado porque estos tipos de puertas de enlace de API son "más estrechos", lo que significa que no implementan código C# personalizado que podría evolucionar hacia un componente monolítico. 

Este tipo de producto actúa más como un proxy inverso para la comunicación de entrada, en el que se pueden filtrar las API de los microservicios internos y también aplicar la autorización a las API publicadas en este nivel único.

La información disponible desde un sistema API le ayuda a comprender cómo se están utilizando las API y cuál es su rendimiento. Para ello, le permiten ver informes de análisis prácticamente en tiempo real e identificar las tendencias que podrían afectar a su negocio. Además, puede obtener registros sobre la actividad de solicitudes y respuestas para su posterior análisis en línea y sin conexión.

Con Azure API Management, puede proteger sus API con una clave, un token y el filtrado de IP. Estas características le permiten aplicar cuotas flexibles y específicas y límites de frecuencia, modificar la forma y el comportamiento de las API mediante directivas y mejorar el rendimiento con el almacenamiento de respuestas en caché.

En esta guía y en la aplicación de ejemplo de referencia (eShopOnContainers), nos limitamos a una arquitectura en contenedores más sencilla y personalizada para que pueda centrarse en los contenedores sin formato sin utilizar productos de PaaS como Azure API Management. Pero para las grandes aplicaciones basadas en microservicios que se implementan en Microsoft Azure, le recomendamos que revise y adopte Azure API Management como base para las puertas de enlace de API.

## <a name="drawbacks-of-the-api-gateway-pattern"></a>Desventajas del patrón de puerta de enlace de API

-   El inconveniente más importante es que, al implementar una puerta de enlace de API, se acopla ese nivel con los microservicios internos. Un acoplamiento así podría provocar problemas graves para la aplicación. Clemens Vaster, arquitecto del equipo Azure Service Bus, se refiere a esta posible dificultad como "el nuevo ESB" en su sesión sobre [mensajería y microservicios](https://www.youtube.com/watch?v=rXi5CLjIQ9k) de GOTO 2016.

-   Usar una puerta de enlace de API de microservicios crea un posible único punto de error adicional.

-   Una puerta de enlace de API puede incrementar el tiempo de respuesta debido a la llamada de red adicional. Pero esta llamada adicional suele tener menor impacto que una interfaz de cliente que realiza demasiadas llamadas a los microservicios internos.

-   Si no se escala horizontalmente de manera correcta, la puerta de enlace de API puede dar lugar a un cuello de botella.

-   Una puerta de enlace de API exige un mayor desarrollo y mantenimiento futuro si incluye lógica personalizada y agregación de datos. Los desarrolladores deben actualizar la puerta de enlace de API con el fin de exponer los puntos de conexión de cada microservicio. Además, los cambios de implementación en los microservicios internos pueden provocar cambios de código en el nivel de la puerta de enlace de API. Pero si la puerta de enlace de API simplemente aplica seguridad, registro y control de versiones (como al utilizar Azure API Management), este costo de desarrollo adicional podría no ser aplicable.

-   Si la puerta de enlace de API ha sido desarrollada por un único equipo, puede haber un cuello de botella de desarrollo. Este es otro de los motivos por el que es más adecuado tener varias puertas de enlace de API específicas que respondan a las distintas necesidades del cliente. También puede separar la puerta de enlace de API internamente en varias áreas o capas que pertenezcan a los diferentes equipos que trabajan en los microservicios internos.

## <a name="additional-resources"></a>Recursos adicionales

-   **Charles Richardson. Pattern: API Gateway / Backend for Front-End (Patrón: back-end o puerta de enlace de API para front-end)**
    [*https://microservices.io/patterns/apigateway.html*](https://microservices.io/patterns/apigateway.html)

-   **Azure API Management**
    [*https://azure.microsoft.com/services/api-management/*](https://azure.microsoft.com/services/api-management/)

-   **Udi Dahan. Service Oriented Composition (Composición orientada a servicios)** \
    [*http://udidahan.com/2014/07/30/service-oriented-composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)

-   **Clemens Vasters. Messaging and Microservices at GOTO 2016** (Mensajería y microservicios en GOTO 2016; vídeo) [*https://www.youtube.com/watch?v=rXi5CLjIQ9k*](https://www.youtube.com/watch?v=rXi5CLjIQ9k)


>[!div class="step-by-step"]
[Anterior] (identify-microservice-domain-model-boundaries.md) [Siguiente] (communication-in-microservice-architecture.md)

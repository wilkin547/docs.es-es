---
title: Diferencias entre el patrón de puerta de enlace de API y la comunicación directa de cliente a microservicio
description: Obtenga más información sobre las diferencias y los usos del patrón de puerta de enlace de API y la comunicación directa de cliente a microservicio.
ms.date: 01/07/2019
ms.openlocfilehash: 88cea3b7c2fdd09bec605431308df8783c343332
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240607"
---
# <a name="the-api-gateway-pattern-versus-the-direct-client-to-microservice-communication"></a>Diferencias entre el patrón de puerta de enlace de API y la comunicación directa de cliente a microservicio

En una arquitectura de microservicios, cada microservicio expone un conjunto de puntos de conexión específicos (normalmente). Este hecho puede afectar a la comunicación entre el cliente y el microservicio, como se explica en esta sección.

## <a name="direct-client-to-microservice-communication"></a>Comunicación directa de cliente a microservicio

Un posible enfoque es usar una arquitectura de comunicación directa de cliente a microservicio. En este enfoque, una aplicación cliente puede realizar solicitudes directamente a algunos de los microservicios, tal como se muestra en la figura 4-12.

![Diagrama que muestra la arquitectura de comunicación directa de cliente a microservicio.](./media/direct-client-to-microservice-communication.png)

**Figura 4-12**. Uso de una arquitectura de comunicación directa de cliente a microservicio

En este enfoque, cada microservicio tiene un punto de conexión público, a veces con un puerto TCP distinto para cada microservicio. La siguiente dirección URL de Azure sería un ejemplo de URL de un servicio determinado:

`http://eshoponcontainers.westus.cloudapp.azure.com:88/`

En un entorno de producción basado en un clúster, la dirección URL anterior estaría asignada al equilibrador de carga que se utiliza en el clúster, que a su vez distribuye las solicitudes entre los microservicios. En entornos de producción, se puede tener un controlador de entrega de aplicaciones (ADC) como [Azure Application Gateway](/azure/application-gateway/application-gateway-introduction) entre los microservicios e Internet. Este controlador actúa como una capa transparente que no solo realiza el equilibrio de carga, sino que también protege sus servicios, ya que ofrece terminación SSL. Esto mejora la carga de los hosts, puesto que Azure Application Gateway se descarga de la terminación SSL y de otras tareas de enrutamiento que consumen mucha CPU. En cualquier caso, un equilibrador de carga y el ADC son transparentes desde un punto de vista de la arquitectura de aplicación lógica.

Una arquitectura de comunicación directa de cliente a microservicio podría bastar para una pequeña aplicación basada en microservicio, especialmente si se trata de una aplicación web del lado cliente como, por ejemplo, una aplicación de ASP.NET MVC. Pero al compilar aplicaciones grandes y complejas basadas en microservicios (por ejemplo, al administrar docenas de tipos de microservicio) y, sobre todo, cuando las aplicaciones cliente son aplicaciones móviles remotas o aplicaciones web SPA, este enfoque se enfrenta a algunos problemas.

Al desarrollar una aplicación de gran tamaño basada en microservicios, considere las siguientes preguntas:

- *¿Cómo pueden las aplicaciones cliente minimizar el número de solicitudes al back-end y reducir el exceso de comunicación con varios microservicios?*

Interactuar con varios microservicios para crear una única pantalla de interfaz de usuario aumenta el número de recorridos de ida y vuelta a través de Internet. Esto aumenta la latencia y la complejidad en el lado de la interfaz de usuario. Idealmente, las respuestas se deberían agregar eficazmente en el lado del servidor. Esto reduce la latencia, ya que varios fragmentos de datos regresan en paralelo y alguna interfaz de usuario puede mostrar los datos tan pronto como estén listos.

- *¿Cómo se pueden controlar cuestiones transversales como la autorización, las transformaciones de datos y la distribución de solicitudes dinámicas?*

La implementación de seguridad y cuestiones transversales como la seguridad y la autorización en cada microservicio pueden requerir un esfuerzo de desarrollo importante. Un posible enfoque es tener esos servicios en el host de Docker o en un clúster interno para así restringir el acceso directo a ellos desde el exterior, e implementar estas cuestiones transversales en un lugar centralizado, como una puerta de enlace de API.

- *¿Cómo pueden las aplicaciones cliente comunicarse con servicios que usan protocolos no compatible con Internet?*

Normalmente, los protocolos usados en el lado del servidor (por ejemplo, AMQP o protocolos binarios) no se admiten en aplicaciones cliente. Por lo tanto, las solicitudes deben realizarse a través de protocolos como HTTP/HTTPS y convertirse posteriormente a los demás protocolos. Un enfoque *man-in-the-middle* puede ser útil en esta situación.

- *¿Cómo se puede dar forma a una fachada creada especialmente para las aplicaciones móviles?*

El diseño de la API de varios microservicios podría no adaptarse a las necesidades de diferentes aplicaciones cliente. Por ejemplo, las necesidades de una aplicación móvil pueden ser diferentes a las necesidades de una aplicación web. Para las aplicaciones móviles, la optimización debe ser incluso mayor para que las respuestas de datos sean más eficaces. Para lograr esto, puede agregar los datos de varios microservicios y devolver un único conjunto de datos y, a veces, eliminar los datos de la respuesta que no son necesarios para la aplicación móvil. Y, por supuesto, puede comprimir los datos. Una vez más, una fachada o API entre la aplicación móvil y los microservicios puede ser conveniente para este escenario.

## <a name="why-consider-api-gateways-instead-of-direct-client-to-microservice-communication"></a>Por qué considerar las puertas de enlace de API en lugar de la comunicación directa de cliente a microservicio

En una arquitectura de microservicios, las aplicaciones cliente generalmente necesitan consumir funcionalidades de más de un microservicio. Si ese consumo se realiza directamente, el cliente debe controlar varias llamadas a los puntos de conexión de microservicio. ¿Qué ocurre cuando la aplicación evoluciona y se introducen nuevos microservicios o se actualizan microservicios existentes? Si la aplicación tiene muchos microservicios, controlar tantos puntos de conexión desde las aplicaciones cliente puede ser una pesadilla. Puesto que la aplicación cliente debería acoplarse a esos puntos de conexión internos, la evolución de los microservicios en el futuro podría provocar un alto impacto para las aplicaciones cliente.

Por lo tanto, disponer de un nivel intermedio o un nivel de direccionamiento indirecto (puerta de enlace) puede ser muy práctico para las aplicaciones basadas en microservicios. Si no dispone de las puertas de enlace de API, las aplicaciones cliente deben enviar solicitudes directamente a los microservicios y eso genera problemas, como los siguientes:

- **Acoplamiento**: Sin el patrón de puerta de enlace de API, las aplicaciones cliente se acoplan a los microservicios internos. Las aplicaciones cliente necesitan saber cómo se descomponen las diferentes áreas de la aplicación en microservicios. Al hacer evolucionar y refactorizar los microservicios internos, esas acciones tienen un impacto en el mantenimiento porque provocan cambios bruscos en las aplicaciones cliente debido a la referencia directa a los microservicios internos desde las aplicaciones cliente. Las aplicaciones cliente deben actualizarse con frecuencia, lo que dificulta la evolución de la solución.

- **Demasiados ciclos de ida y vuelta**: Una única pantalla o página en la aplicación cliente puede requerir varias llamadas a varios servicios. Esto puede dar como resultado múltiples recorridos de ida y vuelta entre el cliente y el servidor, lo cual agrega una latencia significativa. La agregación controlada en un nivel intermedio podría mejorar el rendimiento y la experiencia del usuario para la aplicación cliente.

- **Problemas de seguridad**: Sin una puerta de enlace, todos los microservicios se deben exponer al "mundo externo", haciendo que la superficie del ataque sea mayor que si se ocultan los microservicios internos que las aplicaciones cliente no usan de forma directa. Cuanto menor sea la superficie de ataque, más segura será la aplicación.

- **Intereses transversales**: Cada microservicio difundido de manera pública debe ocuparse de cuestiones tales como la autorización y SSL. En muchos casos, estas cuestiones podrían controlarse en un solo nivel de manera que se simplifiquen los microservicios internos.

## <a name="what-is-the-api-gateway-pattern"></a>¿Qué es el patrón de puerta de enlace de API?

Al diseñar y crear aplicaciones basadas en microservicios grandes o complejas con varias aplicaciones cliente, un buen planteamiento podría ser una [puerta de enlace de API](https://microservices.io/patterns/apigateway.html). Se trata de un servicio que proporciona un punto de entrada único para determinados grupos de microservicios. Es similar al [patrón de fachada](https://en.wikipedia.org/wiki/Facade_pattern) del diseño orientado a objetos, pero en este caso forma parte de un sistema distribuido. En ocasiones, el patrón de puerta de enlace de API también se conoce como "back-end para front-end" ([BFF](https://samnewman.io/patterns/architectural/bff/)) porque en la compilación se tienen en cuenta las necesidades de la aplicación cliente.

Por lo tanto, la puerta de enlace de API se encuentra entre las aplicaciones cliente y los microservicios. Actúa como un proxy inverso, enrutando las solicitudes de los clientes a los servicios. También puede proporcionar características transversales adicionales, como autenticación, terminación SSL y caché.

La figura 4-13 muestra el encaje de una puerta de enlace de API personalizada en una arquitectura basada en microservicios simplificada con solo algunos microservicios.

![Diagrama que muestra una puerta de enlace de API implementada como un servicio personalizado.](./media/direct-client-to-microservice-communication-versus-the-API-Gateway-pattern/custom-service-api-gateway.png)

**Figura 4-13**. Uso de una puerta de enlace de API implementada como un servicio personalizado

Las aplicaciones se conecten a un único punto de conexión (la puerta de enlace de API) configurado para reenviar solicitudes a los microservicios individuales. En este ejemplo, la puerta de enlace de API se implementa como un servicio ASP.NET Core WebHost personalizado que se ejecuta como un contenedor.

Es importante resaltar que en ese diagrama se usa un único servicio de puerta de enlace de API personalizado con conexión a varias aplicaciones cliente distintas. Ese hecho puede suponer un riesgo importante porque el servicio de puerta de enlace de API irá creciendo y evolucionando en función de los muchos requisitos de las aplicaciones cliente. Finalmente, se verá sobredimensionado debido a las distintas necesidades y, en la práctica, podría ser similar a una aplicación o un servicio monolíticos. Por eso es muy recomendable dividir la puerta de enlace de API en varios servicios o varias puertas de enlace de API más pequeñas, por ejemplo, una por cada tipo de factor de forma de aplicación cliente.

Debe tener cuidado al implementar el patrón de puerta de enlace de API. No suele ser una buena idea de tener una única puerta de enlace de API en la que se agreguen todos los microservicios internos de la aplicación. Si es así, actúa como un orquestador o agregador monolítico e infringe la autonomía de los microservicios al acoplarlos todos.

Por lo tanto, las puertas de enlace de API se deberían segregar en función de los límites del negocio y las aplicaciones cliente no deberían actuar como un simple agregador para todos los microservicios internos.

Al dividir el nivel de puerta de enlace de API en múltiples puertas de enlace de API, si la aplicación tiene varias aplicaciones cliente, puede servir de pivote principal al identificar los múltiples tipos de puertas de enlace de API, de manera que puede tener otra fachada para las necesidades de cada aplicación cliente. Este caso es un patrón denominado "back-end para front-end" ([BFF](https://samnewman.io/patterns/architectural/bff/)), donde cada puerta de enlace de API puede proporcionar una API distinta adaptada a cada tipo de aplicación cliente, posiblemente basada incluso en el factor de forma de cliente, mediante la implementación de código adaptador específico que llame, de forma subyacente, a varios servicios internos, como se muestra en la imagen siguiente:

![Diagrama que muestra varias puertas de enlace de API personalizadas.](./media/direct-client-to-microservice-communication-versus-the-API-Gateway-pattern/multiple-custom-api-gateways.png)

**Figura 4-13.1**. Uso de varias puertas de enlace de API personalizadas

Figura 4-13.1 que muestra puertas de enlace de API personalizadas, segregadas por tipo de cliente; una para los clientes móviles y otra para los clientes web. Una aplicación web tradicional se conecta a un microservicio MVC que usa la puerta de enlace de API web. En el ejemplo se muestra una arquitectura simplificada con varias puertas de enlace de API específicas. En este caso, los límites identificados para cada puerta de enlace de API se basan estrictamente en el patrón "back-end para front-end" ([BFF](https://samnewman.io/patterns/architectural/bff/)); por tanto, se basan solo en la API necesaria para cada aplicación cliente. Pero en aplicaciones más grandes también debe ir más allá y crear otras puertas de enlace de API basadas en los límites del negocio como un segundo pivote de diseño.

## <a name="main-features-in-the-api-gateway-pattern"></a>Características principales en el patrón de puerta de enlace de API

Una puerta de enlace de API puede ofrecer varias características. Dependiendo del producto, podría ofrecer características más completas o más sencillas; sin embargo, las características más importantes y fundamentales para cualquier puerta de enlace de API son los siguientes patrones de diseño:

**Proxy inverso o enrutamiento de puerta de enlace**. La puerta de enlace de API ofrece un proxy inverso para redirigir o enrutar las solicitudes (enrutamiento de capa 7, normalmente solicitudes HTTP) a los puntos de conexión de los microservicios internos. La puerta de enlace proporciona un único punto de conexión o dirección URL para las aplicaciones cliente y, a continuación, asigna internamente las solicitudes a un grupo de microservicios internos. Esta característica de enrutamiento ayuda a desconectar las aplicaciones cliente de los microservicios, pero también resulta práctica al modernizar una API monolítica colocando la puerta de enlace de API entre la API monolítica y las aplicaciones cliente; de este modo, se pueden agregar nuevas API como nuevos microservicios mientras se sigue usando la API monolítica heredada hasta que se divida en muchos microservicios en el futuro. Debido a la puerta de enlace de API, las aplicaciones cliente no notarán si las API que se usan se implementan como microservicios internos o una API monolítica y, lo que es más importante, al evolucionar y refactorizar la API monolítica en microservicios, gracias al enrutamiento de la puerta de enlace de API, las aplicaciones cliente no se verán afectadas por ningún cambio de URI.

Para obtener más información, consulte [Patrón Gateway Routing](/azure/architecture/patterns/gateway-routing).

**Agregación de solicitudes.** Como parte del patrón de puerta de enlace, es posible agregar varias solicitudes de cliente (normalmente las solicitudes HTTP) dirigidas a varios microservicios internos en una sola solicitud de cliente. Este patrón es especialmente útil cuando una página o pantalla de cliente necesita información de varios microservicios. Con este enfoque, la aplicación cliente envía una solicitud única a la puerta de enlace de API que envía varias solicitudes a los microservicios internos y, a continuación, agrega los resultados y envía todo el contenido de nuevo a la aplicación cliente. La ventaja principal y el objetivo de este patrón de diseño radica en la reducción del intercambio de mensajes entre las aplicaciones cliente y la API de back-end, lo cual es especialmente importante para las aplicaciones remotas fuera del centro de datos donde residen los microservicios, como aplicaciones móviles o solicitudes de aplicaciones SPA que provienen de JavaScript en exploradores de cliente remotos. En el caso de las aplicaciones web normales que realizan las solicitudes en el entorno del servidor (como una aplicación web ASP.NET Core MVC), este patrón no es tan importante, ya que la latencia es mucho menor que para las aplicaciones cliente remotas.

Dependiendo del producto de puerta de enlace de API que use, es posible que pueda realizar esta agregación. Pero en muchos casos resulta más flexible crear microservicios de agregación en el ámbito de la puerta de enlace de API, de manera que la agregación se define en el código (es decir, código de C#):

Para obtener más información, consulte [Patrón Gateway Aggregation](/azure/architecture/patterns/gateway-aggregation).

**Cuestiones transversales o descarga de puerta de enlace.** Dependiendo de las características que ofrece cada producto de puerta de enlace de API, puede descargar la funcionalidad de microservicios individuales a la puerta de enlace, lo que simplifica la implementación de cada microservicio consolidando las cuestiones transversales en un nivel. Esto resulta especialmente útil para las características especializadas, que pueden ser bastante complicadas de implementar correctamente en cada microservicio interno, como la funcionalidad siguiente:

- Autenticación y autorización
- Integración del servicio de detección
- Almacenamiento en caché de respuestas
- Directivas de reintento, interruptor y QoS
- Limitación de velocidad
- Equilibrio de carga
- Registro, seguimiento, correlación
- Encabezados, cadenas de consulta y transformación de notificaciones
- Adición a la lista de direcciones IP permitidas

Para obtener más información, consulte [Patrón Gateway Offloading](/azure/architecture/patterns/gateway-offloading).

## <a name="using-products-with-api-gateway-features"></a>Uso de productos con características de puerta de enlace de API

Puede haber muchas más cuestiones transversales ofrecidas por los productos de las puertas de enlace de API dependiendo de cada implementación. Aquí trataremos los siguientes puntos:

- [Azure API Management](https://azure.microsoft.com/services/api-management/)
- [Ocelot](https://github.com/ThreeMammals/Ocelot)

### <a name="azure-api-management"></a>Azure API Management

[Azure API Management](https://azure.microsoft.com/services/api-management/) (como se muestra en la figura 4-14) no solo resuelve las necesidades de puerta de enlace de API, sino que también proporciona características como la recopilación de información de las API. Si se usa una solución de administración de API, una puerta de enlace de API es solo un componente dentro de esa solución de administración de API completa.

![Diagrama que muestra cómo usar Azure API Management como la puerta de enlace de API.](./media/direct-client-to-microservice-communication-versus-the-API-Gateway-pattern/api-gateway-azure-api-management.png)

**Figura 4-14**. Uso de Azure API Management para la puerta de enlace de API

Azure API Management resuelve las necesidades de administración y de puerta de enlace de API, como el registro, la seguridad, la medición, etc. En este caso, cuando se usa un producto como Azure API Management, el hecho de tener una sola puerta de enlace de API no es tan arriesgado porque estos tipos de puertas de enlace de API son "más estrechos", lo que significa que no implementan código C# personalizado que podría evolucionar hacia un componente monolítico.

Los productos de puerta de enlace de API suelen actuar más como un proxy inverso para la comunicación de entrada, en el que se pueden filtrar las API de los microservicios internos y también aplicar la autorización a las API publicadas en este nivel único.

La información disponible desde un sistema API le ayuda a comprender cómo se están utilizando las API y cuál es su rendimiento. Para ello, le permiten ver informes de análisis prácticamente en tiempo real e identificar las tendencias que podrían afectar a su negocio. Además, puede obtener registros sobre la actividad de solicitudes y respuestas para su posterior análisis en línea y sin conexión.

Con Azure API Management, puede proteger sus API con una clave, un token y el filtrado de IP. Estas características le permiten aplicar cuotas flexibles y específicas y límites de frecuencia, modificar la forma y el comportamiento de las API mediante directivas y mejorar el rendimiento con el almacenamiento de respuestas en caché.

En esta guía y en la aplicación de ejemplo de referencia (eShopOnContainers), nos limitamos a una arquitectura en contenedores más sencilla y personalizada para que pueda centrarse en los contenedores sin formato sin utilizar productos de PaaS como Azure API Management. Pero para las grandes aplicaciones basadas en microservicios que se implementan en Microsoft Azure, le recomendamos que valore Azure API Management como base para las puertas de enlace de API en producción.

### <a name="ocelot"></a>Ocelot

[Ocelot](https://github.com/ThreeMammals/Ocelot) es una puerta de enlace de API ligera, recomendada para enfoques más simples. Ocelot es una puerta de enlace de API de código abierto basada en .NET Core especialmente diseñada para las arquitecturas de microservicios que necesitan puntos de entrada unificados en sus sistemas. Es ligera, rápida y escalable, y proporciona enrutamiento y autenticación, entre muchas otras características.

La razón principal para elegir Ocelot para la [aplicación de referencia eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) es porque es una puerta de enlace de API ligera de .NET Core que se puede implementar en el mismo entorno de implementación de aplicaciones en el que se implementan los microservicios y contenedores, como Docker Host, Kubernetes, etc. Y puesto que se basa en .NET Core, es multiplataforma, así que la puede implementar en Linux o Windows.

Los diagramas anteriores que muestran puertas de enlace de API personalizadas que se ejecutan en contenedores son precisamente la forma en que también puede ejecutar Ocelot en una aplicación basada en contenedor y microservicio.

Además, hay otros muchos productos en el mercado que ofrecen características de puertas de enlace de API, como Apigee, Kong, MuleSoft o WSO2, y otros productos, como Linkerd y Istio, para características de controlador de ingreso de malla de servicio.

Después de las secciones iniciales de explicación de arquitectura y patrones, las siguientes secciones explican cómo implementar puertas de enlace de API con [Ocelot](https://github.com/ThreeMammals/Ocelot).

## <a name="drawbacks-of-the-api-gateway-pattern"></a>Desventajas del patrón de puerta de enlace de API

- El inconveniente más importante es que, al implementar una puerta de enlace de API, se acopla ese nivel con los microservicios internos. Un acoplamiento así podría provocar problemas graves para la aplicación. Clemens Vaster, arquitecto del equipo de Azure Service Bus, se refiere a esta posible dificultad como "el nuevo ESB" en su sesión sobre "[mensajería y microservicios](https://www.youtube.com/watch?v=rXi5CLjIQ9k)" de GOTO 2016.

- Usar una puerta de enlace de API de microservicios crea un posible único punto de error adicional.

- Una puerta de enlace de API puede incrementar el tiempo de respuesta debido a la llamada de red adicional. Pero esta llamada adicional suele tener menor impacto que una interfaz de cliente que realiza demasiadas llamadas a los microservicios internos.

- Si no se escala horizontalmente de manera correcta, la puerta de enlace de API puede dar lugar a un cuello de botella.

- Una puerta de enlace de API exige un mayor desarrollo y mantenimiento futuro si incluye lógica personalizada y agregación de datos. Los desarrolladores deben actualizar la puerta de enlace de API con el fin de exponer los puntos de conexión de cada microservicio. Además, los cambios de implementación en los microservicios internos pueden provocar cambios de código en el nivel de la puerta de enlace de API. Pero si la puerta de enlace de API simplemente aplica seguridad, registro y control de versiones (como al utilizar Azure API Management), este costo de desarrollo adicional podría no ser aplicable.

- Si la puerta de enlace de API ha sido desarrollada por un único equipo, puede haber un cuello de botella de desarrollo. Este es otro de los motivos por el que es más adecuado tener varias puertas de enlace de API específicas que respondan a las distintas necesidades del cliente. También puede separar la puerta de enlace de API internamente en varias áreas o capas que pertenezcan a los diferentes equipos que trabajan en los microservicios internos.

## <a name="additional-resources"></a>Recursos adicionales

- **Chris Richardson. Patrón: Puerta de enlace de API o back-end para front-end** \
  <https://microservices.io/patterns/apigateway.html>

- **Puertas de enlace de API** \
  <https://docs.microsoft.com/azure/architecture/microservices/gateway>

- **Patrón de agregación y composición** \
  <https://microservices.io/patterns/data/api-composition.html>

- **Azure API Management** \
  <https://azure.microsoft.com/services/api-management/>

- **Udi Dahan. Service Oriented Composition (Composición orientada a servicios)**  \
  <https://udidahan.com/2014/07/30/service-oriented-composition-with-video/>

- **Clemens Vasters. Mensajería y microservicios en GOTO 2016; vídeo** \
  <https://www.youtube.com/watch?v=rXi5CLjIQ9k>

- **Puerta de enlace de API en resumen** (Serie de tutoriales de puerta de enlace de API de ASP.NET Core) \
  <https://www.pogsdotnet.com/2018/08/api-gateway-in-nutshell.html>

>[!div class="step-by-step"]
>[Anterior](identify-microservice-domain-model-boundaries.md)
>[Siguiente](communication-in-microservice-architecture.md)

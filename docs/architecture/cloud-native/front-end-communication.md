---
title: Comunicación de cliente front-end
description: Descubra cómo los clientes front-end se comunican con sistemas nativos de la nube
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: af26873381509df7807db6ecb37a7d73669adb37
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989082"
---
# <a name="front-end-client-communication"></a>Comunicación de cliente front-end

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

En un sistema nativo de la nube, los clientes front-end (aplicaciones móviles, web y de escritorio) requieren un canal de comunicación para interactuar con microservicios back-end independientes.  

¿Cuáles son las opciones?

Para mantener las cosas simples, un cliente front-end podría *comunicarse directamente* con los microservicios de back-end, que se muestran en la figura 4-2.

![Comunicación directa de cliente a servicio](./media/direct-client-to-service-communication.png)

**Figura 4-2.** Comunicación directa de cliente a servicio

Con este enfoque, cada microservicio tiene un punto de conexión público al que pueden acceder los clientes front-end. En un entorno de producción, colocaría un equilibrador de carga delante de los microservicios, enrutando el tráfico proporcionalmente.

Aunque es fácil de implementar, la comunicación directa del cliente solo sería aceptable para aplicaciones de microservicio simples. Este patrón acopla estrechamente a los clientes front-end con los servicios back-end principales, abriendo la puerta para una serie de problemas, incluyendo:

- Susceptibilidad del cliente a la refactorización del servicio back-end.
- Una superficie de ataque más amplia como servicios de back-end principales se exponen directamente.
- Duplicación de preocupaciones transversales en cada microservicio.
- Código de cliente demasiado complejo: los clientes deben realizar un seguimiento de varios puntos de conexión y controlar los errores de forma resistente.

En su lugar, un patrón de diseño de nube ampliamente aceptado es implementar un servicio de puerta de enlace de [API](../microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md) entre las aplicaciones front-end y los servicios back-end. El patrón se muestra en la Figura 4-3.

![Patrón de puerta de enlace de API](./media/api-gateway-pattern.png)

**Figura 4-3.** Patrón de puerta de enlace de API

En la figura anterior, observe cómo el servicio API Gateway abstrae los microservicios principales de back-end. Implementado como una API web, actúa como un *proxy inverso,* enrutando el tráfico entrante a los microservicios internos.

La puerta de enlace aísla al cliente de la partición y refactorización de servicios internos. Si cambia un servicio back-end, se adapta a él en la puerta de enlace sin interrumpir el cliente. También es su primera línea de defensa para preocupaciones transversales, como identidad, almacenamiento en caché, resistencia, medición y limitación. Muchas de estas preocupaciones transversales se pueden descargar de los servicios principales de back-end a la puerta de enlace, lo que simplifica los servicios back-end.

Se debe tener cuidado de mantener API Gateway simple y rápida. Normalmente, la lógica de negocios se mantiene fuera de la puerta de enlace. Una puerta de enlace compleja corre el riesgo de convertirse en un cuello de botella y, finalmente, en un monolito. Los sistemas más grandes a menudo exponen varias puertas de enlace de API segmentadas por tipo de cliente (móvil, web, escritorio) o funcionalidad back-end. El patrón [Backend for Frontends](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) proporciona la dirección para implementar varias puertas de enlace. El patrón se muestra en la Figura 4-4.

![Patrón de puerta de enlace de API](./media/backend-for-frontend-pattern.png)

**Figura 4-4.** Backend para el patrón front-end

Tenga en cuenta en la figura anterior cómo se envía el tráfico entrante a una puerta de enlace de API específica, en función del tipo de cliente: web, móvil o aplicación de escritorio. Este enfoque tiene sentido, ya que las capacidades de cada dispositivo difieren significativamente entre las limitaciones de factor de forma, rendimiento y visualización. Normalmente, las aplicaciones móviles exponen menos funcionalidad que un explorador o aplicaciones de escritorio. Cada puerta de enlace se puede optimizar para que coincida con las capacidades y la funcionalidad del dispositivo correspondiente.

Para empezar, puede crear su propio servicio de API Gateway. Una búsqueda rápida de GitHub proporcionará muchos ejemplos. Sin embargo, hay varios marcos y productos de pasarela comercial disponibles.

## <a name="ocelot-gateway"></a>Puerta de enlace de Ocelot

Para aplicaciones nativas de nube de .NET simples, puede considerar La puerta de enlace de [Ocelot](https://github.com/ThreeMammals/Ocelot). Ocelot es una puerta de enlace de API de código abierto creada para microservicios de .NET que requieren un punto de entrada unificado en su sistema. Es ligero, rápido, escalable.

Al igual que cualquier puerta de enlace de API, su funcionalidad principal es reenviar las solicitudes HTTP entrantes a los servicios de nivel inferior. Además, admite una amplia variedad de capacidades que se pueden configurar en una canalización de middleware de .NET Core. Su conjunto de características se presenta en la siguiente tabla.

|Características del ocelote  | |
| :-------- | :-------- |
| Enrutamiento | Authentication |
| Agregación de solicitudes | Authorization |
| Detección de servicio (con Cónsul y Eureka) | Limitaciones |
| Equilibrio de carga | Registro, Seguimiento |
| Almacenamiento en memoria caché | Transformación de encabezados/cadena de consulta |
| Paso de correlación | Middleware personalizado |
| Calidad de servicio | Políticas de reintento |

Cada puerta de enlace de Ocelot especifica las direcciones ascendentes y descendentes y las características configurables en un archivo de configuración JSON. El cliente envía una solicitud HTTP a la puerta de enlace de Ocelot. Una vez recibido, Ocelot pasa el objeto HttpRequest a través de su canalización que lo manipula al estado especificado por su configuración. Al final de la canalización, Ocelot crea un nuevo HTTPResponseObject y lo pasa al servicio de nivel inferior. Para la respuesta, Ocelot invierte la canalización y devuelve la respuesta al cliente.

Ocelot está disponible como un paquete NuGet. Tiene como destino NET Standard 2.0, por lo que es compatible con los tiempos de ejecución de .NET Core 2.0+ y .NET Framework 4.6.1+. Ocelot se integra con cualquier cosa que hable HTTP y se ejecute en las plataformas que .NET Core admite: Linux, macOS y Windows. Ocelot es extensible y admite muchas plataformas modernas, incluidos contenedores Docker, Azure Kubernetes Services u otras nubes públicas.  Ocelot se integra con paquetes de código abierto como [Consul,](https://www.consul.io) [GraphQL](https://graphql.org)y [Eureka](https://github.com/Netflix/eureka)de Netflix.

Considere Ocelot para aplicaciones nativas de la nube simples que no requieren el conjunto de características enriquecido de una puerta de enlace de API comercial.

## <a name="azure-application-gateway"></a>Azure Application Gateway

Para los requisitos de puerta de enlace simples, puede considerar [Azure Application Gateway](https://docs.microsoft.com/azure/application-gateway/overview). Disponible como [servicio de PaaS](https://azure.microsoft.com/overview/what-is-paas/)de Azure, incluye características básicas de puerta de enlace como enrutamiento de direcciones URL, terminación SSL y un firewall de aplicaciones web. El servicio admite capacidades de equilibrio de carga de [Capa 7.](https://www.nginx.com/resources/glossary/layer-7-load-balancing/) Con la capa 7, usted puede rutear las peticiones basadas en el contenido real de un mensaje HTTP, no solamente los paquetes de red TCP de bajo nivel.

A lo largo de este libro, evangelizamos los sistemas nativos de la nube en [Kubernetes.](https://www.infoworld.com/article/3268073/what-is-kubernetes-your-next-application-platform.html) Kubernetes, un orquestador de contenedores, automatiza las preocupaciones operativas, de implementación y escalado de cargas de trabajo en contenedores. Azure Application Gateway se puede configurar como una puerta de enlace de API para el clúster de [Azure Kubernetes Service.](https://azure.microsoft.com/services/kubernetes-service/)

[Application Gateway Ingress Controller](https://azure.github.io/application-gateway-kubernetes-ingress/) permite que Azure Application Gateway funcione directamente con Azure [Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/). La figura 4.5 muestra la arquitectura.

![Controlador de entrada de Application Gateway](./media/application-gateway-ingress-controller.png)

**Figura 4-5.** Controlador de entrada de Application Gateway

Kubernetes incluye una característica integrada que admite el equilibrio de carga HTTP (Nivel 7), denominado [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/). Ingress define un conjunto de reglas para cómo se pueden exponer las instancias de microservicios dentro de AKS al mundo exterior. En la imagen anterior, el controlador de entrada interpreta las reglas de entrada configuradas para el clúster y configura automáticamente Azure Application Gateway. En función de esas reglas, Application Gateway enruta el tráfico a los microservicios que se ejecutan dentro de AKS. El controlador de entrada escucha los cambios en las reglas de entrada y realiza los cambios adecuados en Azure Application Gateway.

## <a name="azure-api-management"></a>Azure API Management

Para sistemas nativos de nube de escala moderada a grande, puede considerar [Azure API Management](https://azure.microsoft.com/services/api-management/). Es un servicio basado en la nube que no solo resuelve las necesidades de API Gateway, sino que proporciona una experiencia administrativa y de desarrollador completa. API Management se muestra en la Figura 4-6.

![Azure API Management](./media/azure-api-management.png)

**Figura 4-6.** Azure API Management

Para empezar, API Management expone un servidor de puerta de enlace que permite el acceso controlado a servicios back-end basados en reglas y directivas configurables. Estos servicios pueden estar en la nube de Azure, el centro de datos disponible u otras nubes públicas. Las claves de API y los tokens JWT determinan quién puede hacer qué. Todo el tráfico se registra con fines analíticos.

Para los desarrolladores, API Management ofrece un portal para desarrolladores que proporciona acceso a servicios, documentación y código de ejemplo para invocarlos. Los desarrolladores pueden usar Swagger/Open API para inspeccionar los puntos de conexión de servicio y analizar su uso. El servicio funciona en las principales plataformas de desarrollo: .NET, Java, Golang y más.

El portal del publicador expone un panel de administración donde los administradores exponen las API y administran su comportamiento. Se puede conceder acceso al servicio, supervisar el estado del servicio y recopilar telemetría de servicio. Los administradores aplican *directivas* a cada punto de conexión para afectar al comportamiento. [Las directivas](https://docs.microsoft.com/azure/api-management/api-management-howto-policies) son instrucciones precompiladas que se ejecutan secuencialmente para cada llamada de servicio.  Las directivas se configuran para una llamada entrante, una llamada saliente o se invocan en un error. Las directivas se pueden aplicar en diferentes ámbitos de servicio para habilitar el orden determinista al combinar directivas. El producto se suministra con un gran número de [políticas preconstruidas.](https://docs.microsoft.com/azure/api-management/api-management-policies)

A continuación se muestran ejemplos de cómo las políticas pueden afectar al comportamiento de los servicios nativos de la nube:  

- Restringir el acceso al servicio.
- Aplicar la autenticación.  
- Limite las llamadas desde un único origen, si es necesario.
- Activación del almacenamiento en caché.
- Bloquear llamadas desde direcciones IP específicas.
- Controle el flujo del servicio.
- Convierta solicitudes de SOAP a REST o entre diferentes formatos de datos, como de XML a JSON.

Azure API Management puede exponer servicios back-end hospedados en cualquier lugar: en la nube o en el centro de datos. Para los servicios heredados que puede exponer en los sistemas nativos de la nube, admite las API REST y SOAP. Incluso otros servicios de Azure se pueden exponer a través de API Management. Puede colocar una API administrada encima de un servicio de respaldo de Azure como [Azure Service Bus](https://azure.microsoft.com/services/service-bus/) o Azure Logic [Apps.](https://azure.microsoft.com/services/logic-apps/) Azure API Management no incluye compatibilidad integrada con el equilibrio de carga y debe usarse junto con un servicio de equilibrio de carga.

Azure API Management está disponible en [cuatro niveles diferentes:](https://azure.microsoft.com/pricing/details/api-management/)

- Desarrollador
- Básica
- Estándar
- Premium

El nivel de desarrollador está diseñado para cargas de trabajo y evaluación que no son de producción. Los otros niveles ofrecen progresivamente más potencia, características y acuerdos de nivel de servicio (SLA) superiores. El nivel Premium proporciona compatibilidad con [Azure Virtual Network](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) y varias [regiones.](https://docs.microsoft.com/azure/api-management/api-management-howto-deploy-multi-region) Todos los niveles tienen un precio fijo por hora.

Recientemente, Microsoft anunció un [nivel sin servidor](https://azure.microsoft.com/blog/announcing-azure-api-management-for-serverless-architectures/) de API Management para Azure API Management. Conocido como el plan de tarifa de *consumo,* el servicio es una variante de API Management diseñada en torno al modelo informático sin servidor. A diferencia de los planes de tarifa "preasignados" mostrados anteriormente, el nivel de consumo proporciona aprovisionamiento instantáneo y precios de pago por acción.

Habilita las características de API Gateway para los siguientes casos de uso:

- Microservicios implementados con tecnologías sin servidor como [Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-overview) y Azure [Logic Apps.](https://azure.microsoft.com/services/logic-apps/)
- Recursos de servicio de respaldo de Azure, como colas y temas de Service Bus, Azure Storage y otros.
- Microservicios donde el tráfico tiene picos grandes ocasionales pero permanece bajo la mayor parte del tiempo.

El nivel de consumo utiliza los mismos componentes subyacentes de API Management de servicio, pero emplea una arquitectura completamente diferente basada en recursos asignados dinámicamente. Se alinea perfectamente con el modelo informático sin servidor:

- No hay infraestructura que administrar.
- Sin capacidad de inactividad.
- Alta disponibilidad.
- Escalado automático.
- El costo se basa en el uso real.
  
El nuevo nivel de consumo es una gran opción para los sistemas nativos de la nube que exponen recursos sin servidor como API.

> En el momento de escribir, el nivel de consumo está en versión preliminar en la nube de Azure.

## <a name="real-time-communication"></a>Comunicación en tiempo real

La comunicación en tiempo real o push es otra opción para aplicaciones front-end que se comunican con sistemas nativos de nube back-end a través de HTTP. Las aplicaciones, como las actualizaciones financieras, de educación en línea, de juegos y de progreso en el trabajo, requieren respuestas instantáneas en tiempo real desde el back-end. Con la comunicación HTTP normal, no hay forma de que el cliente sepa cuándo hay nuevos datos disponibles. El cliente debe *sondear* o enviar continuamente solicitudes al servidor. Con la comunicación *en tiempo real,* el servidor puede insertar nuevos datos en el cliente en cualquier momento.

Los sistemas en tiempo real a menudo se caracterizan por flujos de datos de alta frecuencia y un gran número de conexiones de cliente simultáneas. La implementación manual de conectividad en tiempo real puede volverse rápidamente compleja, lo que requiere una infraestructura no trivial para garantizar la escalabilidad y la mensajería confiable a los clientes conectados. Puede encontrarse administrando una instancia de Azure Redis Cache y un conjunto de equilibradores de carga configurados con sesiones adhesivas para la afinidad de cliente.

[Azure SignalR Service](https://azure.microsoft.com/services/signalr-service/) es un servicio de Azure totalmente administrado que simplifica la comunicación en tiempo real para las aplicaciones nativas de la nube. Los detalles técnicos de implementación, como el aprovisionamiento de capacidad, el escalado y las conexiones persistentes, se abstraen. Se manejan para usted con un acuerdo de nivel de servicio del 99,9 %. Se centra en las características de la aplicación, no en la plomería de infraestructura.

Una vez habilitado, un servicio HTTP basado en la nube puede enviar actualizaciones de contenido directamente a los clientes conectados, incluidas las aplicaciones de navegador, móvil y de escritorio. Los clientes se actualizan sin necesidad de sondear el servidor. Azure SignalR abstrae las tecnologías de transporte que crean conectividad en tiempo real, incluidos WebSockets, eventos del lado del servidor y sondeo largo. Los desarrolladores se centran en enviar mensajes a todos o a subconjuntos específicos de clientes conectados.

En la figura 4-7 se muestra un conjunto de clientes HTTP que se conectan a una aplicación nativa de la nube con Azure SignalR habilitado.

![Azure SignalR](./media/azure-signalr-service.png)

**Figura 4-7.** Azure SignalR

Otra ventaja de Azure SignalR Service consiste en implementar servicios nativos de nube sin servidor. Tal vez el código se ejecuta a petición con desencadenadores de Azure Functions. Este escenario puede ser complicado porque el código no mantiene conexiones largas con los clientes. Azure SignalR Service puede encargarse de esta situación, ya que el servicio ya administra las conexiones por usted.

Azure SignalR Service se integra estrechamente con otros servicios de Azure, como Azure SQL Database, Service Bus o Redis Cache, lo que abre muchas posibilidades para las aplicaciones nativas de la nube.

>[!div class="step-by-step"]
>[Anterior](communication-patterns.md)
>[Siguiente](service-to-service-communication.md)

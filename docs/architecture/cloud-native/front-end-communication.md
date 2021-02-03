---
title: Comunicación de cliente front-end
description: Obtenga información sobre cómo los clientes front-end se comunican con sistemas nativos de la nube
author: robvet
ms.date: 01/19/2021
ms.openlocfilehash: 089f55f8f6b9320fe552602eb40bb83be28f119b
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506245"
---
# <a name="front-end-client-communication"></a>Comunicación de cliente front-end

En un sistema nativo de la nube, los clientes front-end (aplicaciones móviles, Web y de escritorio) requieren un canal de comunicación para interactuar con microservicios de back-end independientes.  

¿Cuáles son las opciones?

Para simplificar las cosas, un cliente front-end podría *comunicarse directamente* con los microservicios de back-end, que se muestran en la figura 4-2.

![Comunicación directa de cliente a servicio](./media/direct-client-to-service-communication.png)

**Figura 4-2.** Comunicación directa de cliente a servicio

Con este enfoque, cada microservicio tiene un punto de conexión público al que pueden acceder los clientes front-end. En un entorno de producción, debe colocar un equilibrador de carga delante de los microservicios, enrutando el tráfico proporcionalmente.

Aunque es fácil de implementar, la comunicación directa del cliente solo sería aceptable para las aplicaciones de microservicios simples. Este patrón acopla estrechamente los clientes front-end a los servicios back-end básicos, lo que abre la puerta de una serie de problemas, entre los que se incluyen:

- Susceptibilidad del cliente con la refactorización del servicio back-end.
- Una superficie de ataque más amplia como servicios back-end principales se expone directamente.
- Duplicación de cuestiones transversales en cada microservicio.
- Código de cliente demasiado complejo: los clientes deben realizar un seguimiento de varios puntos de conexión y controlar los errores de manera resistente.

En su lugar, un modelo de diseño en la nube ampliamente aceptado es implementar un [servicio de puerta de enlace de API](../microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md) entre las aplicaciones front-end y los servicios back-end. El patrón se muestra en la figura 4-3.

![Patrón de puerta de enlace de API](./media/api-gateway-pattern.png)

**Figura 4-3.** Patrón de puerta de enlace de API

En la ilustración anterior, observe cómo el servicio de puerta de enlace de API abstrae los microservicios principales de back-end. Implementado como una API Web, actúa como un *proxy inverso* y enruta el tráfico entrante a los microservicios internos.

La puerta de enlace aísla al cliente de la creación de particiones y refactorización del servicio interno. Si cambia un servicio back-end, lo acomoda en la puerta de enlace sin interrumpir el cliente. También es la primera línea de defensa para cuestiones transversales, como la identidad, el almacenamiento en caché, la resistencia, la medición y la limitación. Muchas de estas cuestiones transversales se pueden descargar de los servicios principales de back-end a la puerta de enlace, lo que simplifica los servicios back-end.

Se debe tener cuidado para mantener la puerta de enlace de API sencilla y rápida. Normalmente, la lógica de negocios se mantiene fuera de la puerta de enlace. Una puerta de enlace compleja arriesga a convertirse en un cuello de botella y, finalmente, a un monolítico. Los sistemas más grandes a menudo exponen varias puertas de enlace de API segmentadas por tipo de cliente (móvil, Web, escritorio) o funcionalidad de back-end. El [back-end para el patrón de Front-](/azure/architecture/patterns/backends-for-frontends) ends proporciona la dirección para implementar varias puertas de enlace. El patrón se muestra en la figura 4-4.

![Patrón de puerta de enlace de API](./media/backend-for-frontend-pattern.png)

**Figura 4-4.** Patrón back-end para front-end

Tenga en cuenta en la figura anterior cómo se envía el tráfico entrante a una puerta de enlace de API específica según el tipo de cliente: aplicación Web, móvil o de escritorio. Este enfoque tiene sentido a medida que las capacidades de cada dispositivo difieren significativamente en cuanto al factor de forma, el rendimiento y las limitaciones de visualización. Normalmente, las aplicaciones móviles exponen menos funcionalidad que las aplicaciones de escritorio o explorador. Cada puerta de enlace se puede optimizar para que coincida con las capacidades y la funcionalidad del dispositivo correspondiente.

Para empezar, puede crear su propio servicio de puerta de enlace de API. Una búsqueda rápida de GitHub proporcionará muchos ejemplos. Sin embargo, hay varios marcos y productos de puerta de enlace comerciales disponibles.

## <a name="ocelot-gateway"></a>Puerta de enlace de Ocelot

En el caso de las aplicaciones nativas de la nube de .NET, puede considerar la [puerta de enlace de Ocelot](https://github.com/ThreeMammals/Ocelot). Ocelot es una puerta de enlace de API de código abierto creada para microservicios de .NET que requiere un punto de entrada unificado en su sistema. Es ligero, rápido y escalable.

Al igual que cualquier puerta de enlace de API, su funcionalidad principal es reenviar las solicitudes HTTP entrantes a los servicios de bajada. Además, admite una amplia variedad de capacidades que se pueden configurar en una canalización de middleware de .NET. Su conjunto de características se presenta en la tabla siguiente.

|Características de Ocelot  | |
| :-------- | :-------- |
| Enrutamiento | Autenticación |
| Solicitar agregación | Autorización |
| Detección de servicios (con Consul y Eureka) | Limitaciones |
| Equilibrio de carga | Registro, seguimiento |
| Almacenamiento en memoria caché | Encabezados/transformación de cadena de consulta |
| Pass-Through de correlación | Middleware personalizado |
| Calidad de servicio | Directivas de reintento |

Cada puerta de enlace de Ocelot especifica las direcciones ascendentes y descendentes, y las características configurables en un archivo de configuración JSON. El cliente envía una solicitud HTTP a la puerta de enlace de Ocelot. Una vez recibida, Ocelot pasa el objeto HttpRequest a través de su canalización y lo manipula en el estado especificado por su configuración. Al final de la canalización, Ocelot crea un nuevo HTTPResponseObject y lo pasa al servicio de bajada. En la respuesta, Ocelot invierte la canalización y envía la respuesta de vuelta al cliente.

Ocelot está disponible como un paquete NuGet. Tiene como destino el estándar NET 2,0, por lo que es compatible con los tiempos de ejecución de .NET Core 2.0 + y .NET Framework 4.6.1 +. Ocelot se integra con cualquier elemento que hable HTTP y se ejecute en las plataformas compatibles con .NET Core: Linux, macOS y Windows. Ocelot es extensible y admite muchas plataformas modernas, entre las que se incluyen contenedores de Docker, Azure Kubernetes Services u otras nubes públicas.  Ocelot se integra con paquetes de código abierto, como [Consul](https://www.consul.io), [GraphQL](https://graphql.org)y Netflix de [Eureka](https://github.com/Netflix/eureka).

Considere la posibilidad de Ocelot para aplicaciones nativas en la nube simples que no requieran un amplio conjunto de características de una puerta de enlace de API comercial.

## <a name="azure-application-gateway"></a>Azure Application Gateway

En cuanto a los requisitos de puerta de enlace simples, puede considerar [aplicación de Azure puerta de enlace](/azure/application-gateway/overview). Disponible como [servicio PaaS](https://azure.microsoft.com/overview/what-is-paas/)de Azure, incluye características básicas de puerta de enlace, como el enrutamiento de direcciones URL, la terminación SSL y un firewall de aplicaciones Web. El servicio admite capacidades [de equilibrio de carga de nivel 7](https://www.nginx.com/resources/glossary/layer-7-load-balancing/) . Con el nivel 7, puede enrutar las solicitudes en función del contenido real de un mensaje HTTP, no solo de los paquetes de red TCP de bajo nivel.

A lo largo de este libro, se proponen los sistemas nativos en la nube de hospedaje en [Kubernetes](https://www.infoworld.com/article/3268073/what-is-kubernetes-your-next-application-platform.html). Un orquestador de contenedores, Kubernetes automatiza la implementación, el escalado y los aspectos operativos de las cargas de trabajo en contenedores. Aplicación de Azure puerta de enlace se puede configurar como una puerta de enlace de API para el clúster de [Azure Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/) .

El [controlador de entrada Application Gateway](https://azure.github.io/application-gateway-kubernetes-ingress/) habilita aplicación de Azure puerta de enlace para que funcione directamente con [Azure Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/). En la figura 4,5 se muestra la arquitectura.

![Controlador de entrada de Application Gateway](./media/application-gateway-ingress-controller.png)

**Figura 4-5.** Controlador de entrada de Application Gateway

Kubernetes incluye una característica integrada que admite el equilibrio de carga HTTP (nivel 7), denominado [entrada](https://kubernetes.io/docs/concepts/services-networking/ingress/). Entrada define un conjunto de reglas sobre cómo se pueden exponer las instancias de microservicio dentro de AKS al mundo exterior. En la imagen anterior, el controlador de entrada interpreta las reglas de entrada configuradas para el clúster y configura automáticamente la puerta de enlace de Aplicación de Azure. En función de estas reglas, el Application Gateway enruta el tráfico a los microservicios que se ejecutan dentro de AKS. El controlador de entrada escucha los cambios en las reglas de entrada y realiza los cambios adecuados en la puerta de enlace de Aplicación de Azure.

## <a name="azure-api-management"></a>Azure API Management

En el caso de los sistemas nativos en la nube a gran escala, puede considerar [Azure API Management](https://azure.microsoft.com/services/api-management/). Es un servicio basado en la nube que no solo resuelve sus necesidades de puerta de enlace de API, pero proporciona una experiencia de desarrollador y administrativa completa. API Management se muestra en la figura 4-6.

![Azure API Management](./media/azure-api-management.png)

**Figura 4-6.** Azure API Management

Para empezar, API Management expone un servidor de puerta de enlace que permite el acceso controlado a los servicios back-end en función de las reglas y directivas configurables. Estos servicios pueden estar en la nube de Azure, en el centro de datos local o en otras nubes públicas. Las claves de API y los tokens de JWT determinan quién puede hacer qué. Todo el tráfico se registra con fines analíticos.

Para los desarrolladores, API Management ofrece un portal para desarrolladores que proporciona acceso a los servicios, la documentación y el código de ejemplo para invocarlos. Los desarrolladores pueden usar Swagger/Open API para inspeccionar los puntos de conexión de servicio y analizar su uso. El servicio funciona en las principales plataformas de desarrollo: .NET, Java, Golang, etc.

El portal para editores expone un panel de administración en el que los administradores exponen las API y administran su comportamiento. Se puede conceder acceso al servicio, supervisar el estado del servicio y la telemetría de servicio recopilada. Los administradores aplican *directivas* a cada punto de conexión para que afecten al comportamiento. [Las directivas](/azure/api-management/api-management-howto-policies) son instrucciones pregeneradas que se ejecutan secuencialmente para cada llamada de servicio.  Las directivas se configuran para una llamada entrante, una llamada saliente o se invocan después de un error. Las directivas se pueden aplicar en ámbitos de servicio diferentes para habilitar la ordenación determinista al combinar directivas. El producto se distribuye con un gran número de [directivas](/azure/api-management/api-management-policies)creadas previamente.

Estos son algunos ejemplos de cómo las directivas pueden afectar al comportamiento de los servicios nativos de la nube:  

- Restrinja el acceso al servicio.
- Aplique la autenticación.  
- Limite las llamadas de un solo origen, si es necesario.
- Activación del almacenamiento en caché.
- Bloquear las llamadas de direcciones IP específicas.
- Controlar el flujo del servicio.
- Convierta solicitudes de SOAP a REST o entre diferentes formatos de datos, como de XML a JSON.

Azure API Management puede exponer servicios back-end que se hospedan en cualquier lugar: en la nube o en el centro de datos. En el caso de los servicios heredados que puede exponer en los sistemas nativos de la nube, es compatible con las API de REST y SOAP. Incluso otros servicios de Azure se pueden exponer a través de API Management. Podría colocar una API administrada sobre un servicio de respaldo de Azure, como [Azure Service Bus](https://azure.microsoft.com/services/service-bus/) o [Azure Logic apps](https://azure.microsoft.com/services/logic-apps/). Azure API Management no incluye compatibilidad integrada con el equilibrio de carga y debe usarse junto con un servicio de equilibrio de carga.

Azure API Management está disponible en [cuatro niveles distintos](https://azure.microsoft.com/pricing/details/api-management/):

- Desarrollador
- Básico
- Estándar
- Premium

El nivel de desarrollador está diseñado para cargas de trabajo y evaluación que no son de producción. Los otros niveles ofrecen más potencia, características y acuerdos de nivel de servicio (SLA) superiores. El nivel Premium proporciona soporte técnico de [Azure Virtual Network](/azure/virtual-network/virtual-networks-overview) y [de varias regiones](/azure/api-management/api-management-howto-deploy-multi-region). Todos los niveles tienen un precio fijo por hora.

La nube de Azure también ofrece un [nivel sin servidor](https://azure.microsoft.com/blog/announcing-azure-api-management-for-serverless-architectures/) para Azure API Management. Conocido como el *plan de tarifa de consumo*, el servicio es una variante de API Management diseñado en torno al modelo de informática sin servidor. A diferencia de los planes de tarifa "preasignados" previamente mostrados, el nivel de consumo proporciona el aprovisionamiento instantáneo y los precios de pago por acción.

Habilita las características de puerta de enlace de API para los siguientes casos de uso:

- Los microservicios implementados mediante tecnologías sin servidor como [Azure Functions](/azure/azure-functions/functions-overview) y [Azure Logic apps](https://azure.microsoft.com/services/logic-apps/).
- Recursos del servicio de respaldo de Azure, como Service Bus colas y temas, Azure Storage y otros.
- Los microservicios en los que el tráfico tiene picos de gran tamaño, pero permanecen bajo la mayor parte del tiempo.

El nivel de consumo utiliza el mismo servicio subyacente API Management componentes, pero emplea una arquitectura totalmente diferente basada en recursos asignados dinámicamente. Se alinea perfectamente con el modelo de informática sin servidor:

- No hay que administrar ninguna infraestructura.
- No hay capacidad inactiva.
- Alta disponibilidad.
- Escalado automático.
- El costo se basa en el uso real.
  
El nuevo nivel de consumo es una excelente opción para sistemas nativos en la nube que exponen recursos sin servidor como API.

## <a name="real-time-communication"></a>Comunicación en tiempo real

La comunicación en tiempo real, o de extracción, es otra opción para aplicaciones front-end que se comunican con sistemas nativos en la nube de back-end a través de HTTP. Las aplicaciones, como los tableros de cotizaciones, la educación en línea, los juegos y las actualizaciones de progreso de los trabajos, requieren respuestas instantáneas en tiempo real del back-end. Con la comunicación HTTP normal, no hay forma de que el cliente sepa cuándo están disponibles los nuevos datos. El cliente debe *sondear* o enviar continuamente solicitudes al servidor. Con la comunicación en *tiempo real* , el servidor puede introducir nuevos datos en el cliente en cualquier momento.

Los sistemas en tiempo real se caracterizan a menudo por flujos de datos de alta frecuencia y un gran número de conexiones de cliente simultáneas. La implementación manual de la conectividad en tiempo real puede ser compleja, lo que requiere una infraestructura no trivial para garantizar la escalabilidad y la mensajería confiable a los clientes conectados. Podría encontrarse con la administración de una instancia de Azure Redis Cache y un conjunto de equilibradores de carga configurados con sesiones permanentes para la afinidad de cliente.

[Azure signalr Service](https://azure.microsoft.com/services/signalr-service/) es un servicio de Azure totalmente administrado que simplifica la comunicación en tiempo real para las aplicaciones nativas en la nube. Los detalles técnicos de la implementación, como el aprovisionamiento de la capacidad, el escalado y las conexiones persistentes, se abstraen. Se administran automáticamente con un acuerdo de nivel de servicio del 99,9%. Se centra en las características de la aplicación, no en la infraestructura.

Una vez habilitado, un servicio HTTP basado en la nube puede enviar actualizaciones de contenido directamente a los clientes conectados, incluidas las aplicaciones de explorador, móviles y de escritorio. Los clientes se actualizan sin necesidad de sondear el servidor. Azure Signalr abstrae las tecnologías de transporte que crean conectividad en tiempo real, incluidos WebSockets, eventos de Server-Side y sondeos largos. Los desarrolladores se centran en enviar mensajes a todos o a subconjuntos específicos de clientes conectados.

En la figura 4-7 se muestra un conjunto de clientes HTTP que se conectan a una aplicación nativa en la nube con Azure Signalr habilitado.

![Azure SignalR](./media/azure-signalr-service.png)

**Figura 4-7.** Azure SignalR

Otra ventaja de Azure Signalr Service incluye la implementación de servicios de nube nativa sin servidor. Quizás el código se ejecute a petición con desencadenadores Azure Functions. Este escenario puede ser complicado porque el código no mantiene conexiones largas con los clientes. Azure SignalR Service puede encargarse de esta situación, ya que el servicio ya administra las conexiones por usted.

Azure Signalr Service se integra estrechamente con otros servicios de Azure, como Azure SQL Database, Service Bus o Redis Cache, lo que abre muchas posibilidades para las aplicaciones nativas en la nube.

>[!div class="step-by-step"]
>[Anterior](communication-patterns.md)
>[Siguiente](service-to-service-communication.md)

---
title: Asignación de eShopOnContainers a los servicios de Azure
description: Asignación de eShopOnContainers a servicios de Azure como Azure Kubernetes Service, API Gateway y Azure Service Bus.
ms.date: 05/13/2020
ms.openlocfilehash: e938bf9a8f93f9e375a22ffb94395b9e85b0fe63
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155269"
---
# <a name="mapping-eshoponcontainers-to-azure-services"></a>Asignación de eShopOnContainers a los servicios de Azure

Aunque no es necesario, Azure es idóneo para admitir eShopOnContainers porque el proyecto se creó para ser una aplicación nativa en la nube. La aplicación se compila con .NET Core, por lo que se puede ejecutar en contenedores de Linux o Windows, en función del host de Docker. La aplicación se compone de varios microservicios autónomos, cada uno con sus propios datos. Los diferentes microservicios exhiben diferentes enfoques, desde operaciones CRUD simples hasta patrones DDD y CQRS más complejos. Los microservicios se comunican con los clientes a través de HTTP y entre sí a través de la comunicación basada en mensajes. La aplicación también admite varias plataformas para los clientes, ya que adopta HTTP como protocolo de comunicación estándar e incluye ASP.NET Core y Xamarin Mobile Apps que se ejecutan en plataformas Android, iOS y Windows.

La arquitectura de la aplicación se muestra en la figura 2-5. A la izquierda se encuentran las aplicaciones cliente, divididas en aplicaciones móviles, web tradicionales y de aplicación de una sola página web (SPA). A la derecha están los componentes del lado servidor que componen el sistema y cada uno de ellos se puede hospedar en los contenedores de Docker y en los clústeres de Kubernetes. La aplicación web tradicional se basa en la ASP.NET Core aplicación MVC que se muestra en amarillo. Esta aplicación y las aplicaciones móviles y Web SPA se comunican con los microservicios individuales a través de una o varias puertas de enlace de API. Las puertas de enlace de API siguen el patrón "back-ends para front-ends" (BFF), lo que significa que cada puerta de enlace está diseñada para admitir un cliente de front-end determinado. Los microservicios individuales se enumeran a la derecha de las puertas de enlace de API e incluyen la lógica de negocios y algún tipo de almacén de persistencia. Los diferentes servicios hacen uso de SQL Server bases de datos, instancias de caché en Redis y almacenes MongoDB/CosmosDB. En el extremo derecho se encuentra el bus de eventos del sistema, que se usa para la comunicación entre los microservicios.

![eShopOnContainers arquitectura de la ](./media/eshoponcontainers-architecture.png)
 **figura 2-5**. Arquitectura de eShopOnContainers.

Todos los componentes del lado servidor de esta arquitectura se asignan fácilmente a los servicios de Azure.

## <a name="container-orchestration-and-clustering"></a>Orquestación de contenedores y agrupación en clústeres

Los servicios hospedados en contenedores de la aplicación, desde ASP.NET Core aplicaciones MVC hasta los microservicios de catálogo y de ordenación, se pueden hospedar y administrar en Azure Kubernetes Service (AKS). La aplicación se puede ejecutar localmente en Docker y Kubernetes, y los mismos contenedores se pueden implementar en entornos de ensayo y producción hospedados en AKS. Este proceso se puede automatizar, como veremos en la sección siguiente.

AKS proporciona servicios de administración para clústeres individuales de contenedores. La aplicación implementará clústeres de AKS independientes para cada microservicio que se muestra en el diagrama de arquitectura anterior. Este enfoque permite escalar cada servicio individual de forma independiente según sus necesidades de recursos. Cada microservicio también se puede implementar de forma independiente y, idealmente, estas implementaciones deberían incurrir en tiempo de inactividad del sistema.

## <a name="api-gateway"></a>API Gateway

La aplicación eShopOnContainers tiene varios clientes front-end y varios servicios back-end diferentes. No hay una correspondencia uno a uno entre las aplicaciones cliente y los microservicios que las admiten. En este escenario, puede haber una gran complejidad al escribir software cliente para interactuar con los distintos servicios back-end de una manera segura. Cada cliente tendría que abordar esta complejidad por su cuenta, lo que provocaría la duplicación y muchos lugares en los que realizar las actualizaciones a medida que los servicios cambian o se implementan nuevas directivas.

Azure API Management (APIM) ayuda a las organizaciones a publicar API de un modo coherente y manejable. APIM consta de tres componentes: la puerta de enlace de API y el portal de administración (el Azure Portal) y un portal para desarrolladores.

La puerta de enlace de API acepta llamadas API y las enruta a la API de back-end adecuada. También puede proporcionar servicios adicionales, como la comprobación de claves de API o tokens JWT y la transformación de API sobre la marcha sin modificaciones en el código (por ejemplo, para dar cabida a los clientes que esperan una interfaz anterior).

En el Azure Portal se define el esquema de la API y se empaquetan diferentes API en productos. También puede configurar el acceso de usuario, ver informes y configurar directivas para cuotas o transformaciones.

El portal para desarrolladores sirve como recurso principal para los desarrolladores. Proporciona a los desarrolladores la documentación de la API, una consola de prueba interactiva e informa sobre su propio uso. Los desarrolladores también usan el portal para crear y administrar sus propias cuentas, incluida la compatibilidad con la suscripción y la clave de API.

Con APIM, las aplicaciones pueden exponer varios grupos diferentes de servicios, cada uno de los cuales proporciona un back-end para un cliente de front-end determinado. Se recomienda APIM para escenarios complejos. Para las necesidades más sencillas, se puede usar la puerta de enlace de API ligera Ocelot. La aplicación eShopOnContainers usa Ocelot debido a su simplicidad y porque se puede implementar en el mismo entorno de aplicación que la propia aplicación. [Más información acerca de eShopOnContainers, APIM y Ocelot.](../microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md#azure-api-management)

Otra opción si la aplicación usa AKS es implementar el controlador de entrada de puerta de enlace de Azure como Pod en el clúster de AKS. Esto permite que el clúster se integre con una puerta de enlace de Aplicación de Azure, lo que permite que la puerta de enlace equilibre la carga del tráfico a los pods de AKS. [Obtenga más información sobre el controlador de entrada de puerta de enlace de Azure para AKS](https://github.com/Azure/application-gateway-kubernetes-ingress).

## <a name="data"></a>data

Los diversos servicios de back-end que usa eShopOnContainers tienen requisitos de almacenamiento diferentes. Varios microservicios utilizan bases de datos de SQL Server. El microservicio de cesta aprovecha la caché en Redis para su persistencia. El microservicio locations espera una API de MongoDB para sus datos. Azure admite cada uno de estos formatos de datos.

Por SQL Server compatibilidad con bases de datos, Azure tiene productos para todo, desde bases de datos únicas hasta grupos elásticos de gran escalabilidad SQL Database. Los microservicios individuales se pueden configurar para comunicarse con sus propias bases de datos de SQL Server individuales de forma rápida y sencilla. Estas bases de datos se pueden escalar según sea necesario para admitir cada microservicio independiente según sus necesidades.

La aplicación eShopOnContainers almacena la cesta de la compra actual del usuario entre las solicitudes. Lo administra el microservicio de cesta que almacena los datos en una caché en Redis. En desarrollo, esta caché se puede implementar en un contenedor, mientras que en producción puede usar caché de Azure para Redis. Caché de Azure para Redis es un servicio totalmente administrado que ofrece un alto rendimiento y confiabilidad sin necesidad de implementar y administrar instancias o contenedores de Redis por su cuenta.

El microservicio de ubicaciones utiliza una base de datos de MongoDB NoSQL para su persistencia. Durante el desarrollo, la base de datos se puede implementar en su propio contenedor, mientras que en producción el servicio puede aprovechar la [API de Azure Cosmos dB para MongoDB](/azure/cosmos-db/mongodb-introduction). Una de las ventajas de Azure Cosmos DB es su capacidad para aprovechar varios protocolos de comunicación diferentes, entre los que se incluyen una API de SQL y las API NoSQL comunes, como MongoDB, Cassandra, Gremlin y Azure Table Storage. Azure Cosmos DB ofrece una base de datos totalmente administrada y distribuida globalmente como servicio que se puede escalar para satisfacer las necesidades de los servicios que la usan.

Los datos distribuidos en aplicaciones nativas en la nube se describen con más detalle en el [capítulo 5](distributed-data.md).

## <a name="event-bus"></a>Bus de eventos

La aplicación utiliza eventos para comunicar cambios entre distintos servicios. Esta funcionalidad se puede implementar con una variedad de implementaciones y localmente la aplicación eShopOnContainers usa [RabbitMQ](https://www.rabbitmq.com/). Cuando se hospeda en Azure, la aplicación aprovecharía [Azure Service Bus](/azure/service-bus/) para su mensajería. Azure Service Bus es un agente de mensajes de integración totalmente administrado que permite a las aplicaciones y servicios comunicarse entre sí de forma desacoplada, confiable y asincrónica. Azure Service Bus admite colas individuales, así como *temas* independientes para admitir escenarios de suscriptor de publicador. La aplicación eShopOnContainers aprovecharía temas con Azure Service Bus para admitir la distribución de mensajes de un microservicio a cualquier otro microservicio que necesitaba reaccionar a un mensaje determinado.

## <a name="resiliency"></a>Resistencia

Una vez implementada en producción, la aplicación eShopOnContainers podría aprovecharse de varios servicios de Azure disponibles para mejorar su resistencia. La aplicación publica comprobaciones de estado, que se pueden integrar con Application Insights para proporcionar informes y alertas en función de la disponibilidad de la aplicación. Los recursos de Azure también proporcionan registros de diagnóstico que se pueden usar para identificar y corregir errores y problemas de rendimiento. Los registros de recursos proporcionan información detallada sobre cuándo y cómo se usan los distintos recursos de Azure en la aplicación. Obtendrá más información sobre las características de resistencia nativa en la nube en el [capítulo 6](resiliency.md).

>[!div class="step-by-step"]
>[Anterior](introduce-eshoponcontainers-reference-app.md)
>[Siguiente](deploy-eshoponcontainers-azure.md)

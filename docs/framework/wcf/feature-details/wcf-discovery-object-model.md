---
title: Modelo de objetos de Detección de WCF
ms.date: 03/30/2017
ms.assetid: 8365a152-eacd-4779-9130-bbc48fa5c5d9
ms.openlocfilehash: 06984766fa8199a18197255c57492863a888e3aa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281942"
---
# <a name="wcf-discovery-object-model"></a>Modelo de objetos de Detección de WCF

Detección de WCF consta de un conjunto de tipos que proporcionan un modelo de programación unificado que le permite escribir servicios reconocibles durante el tiempo de ejecución y clientes que encuentran y utilizan estos servicios.  
  
## <a name="making-a-service-discoverable-and-finding-services"></a>Hacer que un servicio sea reconocible y buscar servicios  

 Para hacer que un servicio de WCF sea reconocible, agregue <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> a <xref:System.ServiceModel.Description.ServiceDescription> del host de servicio y agregue un extremo de detección. Si un servicio se configura para enviar mensajes de anuncio (agregando una clase <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>), se envía el anuncio cuando el host de servicio se abre y se cierra.  
  
 Un cliente que desea realizar escuchas de mensajes de anuncio del servicio hospeda un servicio de anuncio y agrega uno o más extremos de anuncio. El servicio de anuncio recibe mensajes de anuncio y genera eventos de anuncio.  
  
 El cliente utiliza la clase <xref:System.ServiceModel.Discovery.DiscoveryClient> para buscar servicios disponibles. La aplicación cliente crea instancias de la clase <xref:System.ServiceModel.Discovery.DiscoveryClient>, pasando un punto de conexión de detección que especifica dónde se deben enviar los mensajes de detección. El cliente llama al método <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, que envía una solicitud `Probe`. Los servicios que realizan escuchas de los mensajes de detección reciben esta solicitud `Probe`. Si el servicio coincide con los criterios especificados en `Probe`, devuelve un mensaje `ProbeMatch` al cliente.  
  
## <a name="object-model"></a>Modelo de objetos  

 La API de Detección de WCF define las clases siguientes:  
  
- <xref:System.ServiceModel.Discovery.AnnouncementClient>  
  
- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
  
- <xref:System.ServiceModel.Discovery.AnnouncementService>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryClient>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryMessageSequenceGenerator>  
  
- <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryProxy>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryService>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryVersion>  
  
- <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
  
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>  
  
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>  
  
- <xref:System.ServiceModel.Discovery.FindCriteria>  
  
- <xref:System.ServiceModel.Discovery.FindRequestContext>  
  
- <xref:System.ServiceModel.Discovery.FindResponse>  
  
- <xref:System.ServiceModel.Discovery.ResolveCriteria>  
  
- <xref:System.ServiceModel.Discovery.ResolveResponse>  
  
- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>  

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
  
- <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
  
## <a name="announcementclient"></a>AnnouncementClient  

 La clase <xref:System.ServiceModel.Discovery.AnnouncementClient> proporciona métodos sincrónicos y asincrónicos para enviar los mensajes de anuncio. Hay dos tipos de mensajes de anuncio: Hola y Adiós. Un mensaje Hola se envía para indicar que un servicio se ha vuelto disponible y un mensaje Adiós se envía para indicar que un servicio existente se ha vuelto no disponible. El desarrollador crea una instancia <xref:System.ServiceModel.Discovery.AnnouncementClient>, pasando una instancia de <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> como un parámetro de constructor.  
  
## <a name="announcementendpoint"></a>AnnouncementEndpoint  

 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> representa un extremo estándar con un contrato de anuncio fijo. Lo utiliza un servicio o cliente para enviar y recibir mensajes de anuncio. De forma predeterminada, la clase <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> se establece para utilizar la versión de protocolo 11 de WS_Discovery.  
  
## <a name="announcementservice"></a>AnnouncementService  

 <xref:System.ServiceModel.Discovery.AnnouncementService> es una implementación proporcionada por el sistema de un servicio de anuncio que recibe y procesa mensajes de anuncio. Cuando se recibe un mensaje de Hola o Adiós, la instancia <xref:System.ServiceModel.Discovery.AnnouncementService> llama a <xref:System.ServiceModel.Discovery.AnnouncementService.OnBeginOnlineAnnouncement%2A> del método virtual correspondiente o a <xref:System.ServiceModel.Discovery.AnnouncementService.OnBeginOfflineAnnouncement%2A>, que genera eventos de anuncio.  
  
## <a name="discoveryclient"></a>DiscoveryClient  

 Una aplicación cliente utiliza la clase <xref:System.ServiceModel.Discovery.DiscoveryClient> para buscar y resolver los servicios disponibles. Proporciona métodos sincrónicos y asincrónicos para buscar y resolver servicios basados respectivamente en las clases <xref:System.ServiceModel.Discovery.FindCriteria> y <xref:System.ServiceModel.Discovery.ResolveCriteria> especificadas. El desarrollador crea una instancia de <xref:System.ServiceModel.Discovery.DiscoveryClient> y ofrece una instancia de <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> como parámetro de constructor.  
  
 Para buscar un servicio, el desarrollador invoca el método `Find` sincrónico o asincrónico, que proporciona una instancia <xref:System.ServiceModel.Discovery.FindCriteria> que contiene el criterio de búsqueda que se debe usar. <xref:System.ServiceModel.Discovery.DiscoveryClient> crea un mensaje `Probe` con los encabezados adecuados y envía la solicitud de búsqueda. Dado que puede haber más de una solicitud `Find` pendiente en cualquier momento, el cliente pone en correlación las respuestas recibidas y valida la respuesta. A continuación, entrega los resultados al autor de llamada de la operación `Find` mediante <xref:System.ServiceModel.Discovery.FindResponse>.  
  
 Para resolver un servicio conocido, el desarrollador invoca el método `Resolve` sincrónico o asincrónico que proporciona una instancia de <xref:System.ServiceModel.Discovery.ResolveCriteria> que contiene <xref:System.ServiceModel.EndpointAddress> del servicio conocido. <xref:System.ServiceModel.Discovery.DiscoveryClient> crea el mensaje `Resolve` con los encabezados adecuados y envía la solicitud de resolución. La respuesta recibida se pone en correlación con las solicitudes de resolución pendientes y el resultado se entrega al autor de llamada de la operación `Resolve` mediante <xref:System.ServiceModel.Discovery.ResolveResponse>.  
  
 Si un proxy de detección está presente en la red y <xref:System.ServiceModel.Discovery.DiscoveryClient> envía la solicitud de detección en modo de multidifusión, el proxy de detección puede responder con el mensaje Hola de supresión de multidifusión. <xref:System.ServiceModel.Discovery.DiscoveryClient> genera el evento `ProxyAvailable` cuando recibe los mensajes de Hola en respuesta a solicitudes `Find` o `Resolve` pendientes. El evento `ProxyAvailable` contiene la clase <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> sobre el proxy de detección. El empleo de esta información para cambiar del modo ad hoc al modo administrativo depende del desarrollador.  
  
## <a name="discoveryendpoint"></a>DiscoveryEndpoint  

 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> representa un extremo estándar con un contrato de detección. Lo emplea un servicio o cliente para enviar o recibir mensajes de detección. De forma predeterminada, <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> se establece para utilizar el modo <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode.Managed?displayProperty=nameWithType> y la versión WSDiscovery11 de WS-Discovery.  
  
## <a name="discoverymessagesequencegenerator"></a>DiscoveryMessageSequenceGenerator  

 <xref:System.ServiceModel.Discovery.DiscoveryMessageSequenceGenerator> se utiliza para generar <xref:System.ServiceModel.Discovery.DiscoveryMessageSequence> cuando el servicio envía mensajes de detección o de anuncio.  
  
## <a name="discoveryservice"></a>DiscoveryService  

 La clase abstracta <xref:System.ServiceModel.Discovery.DiscoveryService> proporciona un marco para recibir y procesar mensajes `Probe` y `Resolve`. Cuando se recibe un mensaje `Probe`, <xref:System.ServiceModel.Discovery.DiscoveryService> crea una instancia de <xref:System.ServiceModel.Discovery.FindRequestContext> basada en el mensaje entrante e invoca el método virtual <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginFind%2A>. Cuando se recibe un mensaje `Resolve`, <xref:System.ServiceModel.Discovery.DiscoveryService> invoca el método virtual <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginResolve%2A>. Puede heredar de esta clase para proporcionar una implementación personalizada del servicio de detección.  
  
## <a name="discoveryproxy"></a>DiscoveryProxy  

 La clase abstracta <xref:System.ServiceModel.Discovery.DiscoveryProxy> proporciona un marco de trabajo para recibir y procesar mensajes de detección y de anuncio. Hereda de esta clase cuando implementa un proxy de detección personalizado. Cuando un mensaje `Probe` se recibe en multidifusión, la clase <xref:System.ServiceModel.Discovery.DiscoveryProxy> llama al método virtual `BeginShouldRedirectFind` para determinar si se debe enviar un mensaje de supresión de multidifusión. Si el desarrollador decide no enviar un mensaje de supresión de multidifusión o si el mensaje `Probe` se ha recibido en unidifusión, crea una instancia de la clase <xref:System.ServiceModel.Discovery.FindRequestContext> basada en el mensaje entrante e invoca el método virtual `OnBeginFind`. Cuando un mensaje `Resolve` se recibe en multidifusión, la clase <xref:System.ServiceModel.Discovery.DiscoveryProxy> llama al método virtual `ShouldRedirectResolve` para determinar si se debe enviar un mensaje de supresión de multidifusión. Si el desarrollador decide no enviar un mensaje de supresión de multidifusión o si el mensaje `Resolve` se ha recibido en unidifusión, crea una instancia de la clase <xref:System.ServiceModel.Discovery.ResolveCriteria> basada en el mensaje entrante e invoca el método virtual `OnBeginResolve`. Cuando se recibe un mensaje de Hola o Adiós, la clase <xref:System.ServiceModel.Discovery.DiscoveryProxy> llama al método virtual apropiado (`OnBeginOnlineAnnouncement` o `OnBeingOfflineAnnouncement`), que genera eventos de anuncio.  
  
## <a name="discoveryversion"></a>DiscoveryVersion  

 La clase <xref:System.ServiceModel.Discovery.DiscoveryVersion> representa la versión del protocolo de detección que se debe utilizar.  
  
## <a name="endpointdiscoverybehavior"></a>EndpointDiscoveryBehavior  

 La clase <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> se usa para controlar la detectabilidad de un punto de conexión, especificar las extensiones, los nombres de tipo de contrato adicionales. y los ámbitos asociados a ese punto de conexión. Este comportamiento se agrega a un punto de conexión de la aplicación para configurar su <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>. Cuando <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> se agrega al host de servicio, todos los puntos de conexión de la aplicación hospedados por el host del servicio se vuelven reconocibles de forma predeterminada. El desarrollador puede desactivar la detección para un extremo concreto estableciendo la propiedad <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> en `false`.  
  
## <a name="endpointdiscoverymetadata"></a>EndpointDiscoveryMetadata  

 La clase <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> proporciona una representación independiente de la versión de un extremo publicado por el servicio. Contiene las direcciones de los extremos, los URI de escucha, los nombres del tipo de contrato, los ámbitos, la versión de metadatos y las extensiones especificados por el desarrollador del servicio. La clase <xref:System.ServiceModel.Discovery.FindCriteria> enviada por el cliente durante una operación `Probe` se compara con <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>. Si los criterios coinciden, <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> se devuelve al cliente. La dirección del extremo en <xref:System.ServiceModel.Discovery.ResolveCriteria> se compara con la dirección del extremo de <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>. Si los criterios coinciden, <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> se devuelve al cliente.  
  
## <a name="findcriteria"></a>FindCriteria  

 La clase <xref:System.ServiceModel.Discovery.FindCriteria> es una clase independiente de la versión usada para especificar los criterios usados al buscar un servicio. Admite totalmente los criterios definidos por WS-Discovery para servicios coincidentes. También tiene extensiones que pueden usar los desarrolladores para especificar valores personalizados que se pueden usar durante el proceso de coincidencia. El desarrollador puede proporcionar los criterios de finalización para la operación `Find` especificando <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A>, que especifica el número total de servicios que busca el desarrollador o que indica <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>, que es el valor que determina cuánto tiempo espera el cliente para obtener respuestas.  
  
## <a name="findrequestcontext"></a>FindRequestContext  

 Se crean instancias de la clase <xref:System.ServiceModel.Discovery.FindRequestContext> mediante el servicio de detección en función del mensaje `Probe` que recibe cuando un cliente inicia una operación `Find`. Contiene una instancia de <xref:System.ServiceModel.Discovery.FindCriteria> especificada por el cliente.  
  
## <a name="findresponse"></a>FindResponse  

 La clase <xref:System.ServiceModel.Discovery.FindResponse> se devuelve al realizador de la llamada de <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> con las respuestas de la operación `Find`. También se encuentra en <xref:System.ServiceModel.Discovery.FindCompletedEventArgs>. Contiene una colección de <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>, que es la colección de puntos de conexión detectados y un diccionario de <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> y <xref:System.ServiceModel.Discovery.DiscoveryMessageSequence>.  
  
## <a name="resolvecriteria"></a>ResolveCriteria  

 La clase <xref:System.ServiceModel.Discovery.ResolveCriteria> es una clase independiente de la versión usada para especificar los criterios empleados al resolver un servicio conocido. Contiene la dirección del punto de conexión del servicio conocido. El desarrollador puede proporcionar los criterios de finalización para la operación de resolución especificando <xref:System.ServiceModel.Discovery.ResolveCriteria.Duration%2A>, que especifica cuánto tiempo espera el cliente para recibir respuestas.  
  
## <a name="resolveresponse"></a>ResolveResponse  

 La clase <xref:System.ServiceModel.Discovery.ResolveResponse> se devuelve al realizador de la llamada del método <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> con la respuesta de la operación `Resolve`. También se encuentra en <xref:System.ServiceModel.Discovery.ResolveCompletedEventArgs>. Contiene una instancia de <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>, que son los puntos de conexión detectados y una instancia de <xref:System.ServiceModel.Discovery.DiscoveryMessageSequence>.  
  
## <a name="servicediscoverybehavior"></a>ServiceDiscoveryBehavior  

 La clase <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> permite al desarrollador agregar la característica de detección a un servicio. Agregue este comportamiento a <xref:System.ServiceModel.ServiceHost>. La clase <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> itera en los extremos de la aplicación agregados al host de servicio y crea una recopilación de <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> de los extremos reconocibles. Todos los puntos de conexión son reconocibles de forma predeterminada. La detectabilidad de un extremo determinado se puede controlar agregando <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> a ese extremo del particular. Si los extremos de anuncio se agregan a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>, el anuncio de todos los extremos reconocibles se envía a cada uno de los extremos de anuncio cuando el host de servicio se abre o se cierra.  
  
## <a name="udpannouncementendpoint"></a>UdpAnnouncementEndpoint  

 La clase <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> es un punto de conexión de anuncio estándar que se pre-configura para el anuncio en un enlace de multidifusión de UDP. De forma predeterminada, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> se establece para utilizar la versión WSApril2005 de WS_Discovery.  
  
## <a name="udpdiscoveryendpoint"></a>UdpDiscoveryEndpoint  

 La clase <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> es un punto de conexión de detección estándar que se pre-configura para la detección en un enlace de multidifusión de UDP. De forma predeterminada, <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> se establece para usar la versión WSDiscovery11 de WS-Discovery y el modo <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode.Adhoc?displayProperty=nameWithType>.

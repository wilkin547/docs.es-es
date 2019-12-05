---
title: Resoluciones del mismo nivel
ms.date: 03/30/2017
ms.assetid: d86d12a1-7358-450f-9727-b6afb95adb9c
ms.openlocfilehash: 33afffcbf11d757dfd003d1fd2bc9a17a3047a69
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837381"
---
# <a name="peer-resolvers"></a>Resoluciones del mismo nivel
Para conectar a una malla, un nodo del mismo nivel necesita las direcciones IP de otros nodos. Las direcciones IP se obtienen al establecer contacto con un servicio de resolución, que toma el identificador de la malla y devuelve una lista de direcciones que corresponden a los nodos registrados con ese identificador de malla concreto. La resolución mantiene una lista de direcciones registradas, que crea mediante el registro de cada nodo de la malla en el servicio.  
  
 Puede especificar qué servicio PeerResolver se debe usar mediante la propiedad `Resolver` de <xref:System.ServiceModel.NetPeerTcpBinding>.  
  
## <a name="supported-peer-resolvers"></a>Resoluciones del mismo nivel compatibles  
 El canal del mismo nivel admite dos tipos de resoluciones: protocolo de resolución de nombres del mismo nivel (PNRP) y servicios de resolución personalizados.  
  
 De forma predeterminada, el canal del mismo nivel usa el servicio de resolución del mismo nivel PNRP para la detección de iguales y vecinos en la malla. En situaciones o plataformas en las que PNRP no está disponible o es viable, Windows Communication Foundation (WCF) proporciona un servicio de detección alternativo basado en servidor, el <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>. También puede definir explícitamente un servicio de resolución personalizado escribiendo una clase que implemente la interfaz <xref:System.ServiceModel.PeerResolvers.IPeerResolverContract>.  
  
### <a name="peer-name-resolution-protocol-pnrp"></a>Protocolo de resolución de nombres del mismo nivel (PNRP)  
 PNRP, el solucionador predeterminado para Windows Vista, es un servicio de resolución de nombres distribuido y sin servidor. PNRP también se puede utilizar en [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)] instalando el paquete de conexión de red avanzada. Cualquiera de los dos clientes que ejecuten la misma versión de PNRP pueden localizarse mediante este protocolo, siempre y cuando cumplan ciertas condiciones (como la falta de un firewall corporativo intermedio). Tenga en cuenta que la versión de PNRP que se incluye con Windows Vista es más reciente que la versión incluida en el paquete de redes avanzadas. Compruebe en el Centro de descarga de Microsoft si hay actualizaciones de PNRP para [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)].  
  
### <a name="custom-resolver-services"></a>Servicios de resolución personalizados  
 Cuando el servicio PNRP no está disponible o cuando se desea el control absoluto de la forma de la malla, se puede usar un servicio de resolución personalizado basado en servidor. Este servicio se puede definir explícitamente escribiendo una clase de resolución que implemente la interfaz <xref:System.ServiceModel.PeerResolvers.IPeerResolverContract> o utilizando la implementación predeterminada de la bandeja de entrada, <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>.  
  
 Bajo la implementación predeterminada del servicio, los registros de cliente expiran después de una cierta cantidad de tiempo si el cliente no actualiza explícitamente el registro. Los clientes que usen el servicio de resolución deben reconocer el límite máximo de la latencia cliente-servidor para actualizar a tiempo y correctamente los registros. Esto implica elegir un tiempo de espera de actualización adecuado (`RefreshInterval`) en el servicio de resolución. (Para obtener más información, vea [dentro de CustomPeerResolverService: Client registrations](../../../../docs/framework/wcf/feature-details/inside-the-custompeerresolverservice-client-registrations.md)).  
  
 El escritor de la aplicación también ha de tener en cuenta la seguridad de la conexión entre los clientes y el servicio de resolución personalizado. Puede hacer esto mediante la configuración de seguridad en <xref:System.ServiceModel.NetTcpBinding> que los clientes usan para ponerse en contacto con el servicio de resolución. Debe especificar las credenciales (si se usan) en el `ChannelFactory` que se usa para crear el canal del mismo nivel. Estas credenciales se pasan a `ChannelFactory` que se usa para crear los canales a la resolución personalizada.  
  
> [!NOTE]
> Al utilizar redes locales e improvisadas con una resolución personalizada, se aconseja que las aplicaciones que usen o admitan redes locales e improvisadas incluyan una lógica que seleccione una dirección única de vínculo local que se use a la hora de la conexión. Esto evita cualquier confusión potencial producida por equipos con varias direcciones de vínculo local. De acuerdo con esto, el canal del mismo nivel solo admite el uso de una única dirección de vínculo local en un momento determinado. Puede especificar esta dirección con la propiedad `ListenIpAddress` en el <xref:System.ServiceModel.NetPeerTcpBinding>.  
  
 Para obtener una demostración de cómo implementar un solucionador personalizado, vea [resolución del mismo nivel personalizada del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90)).  
  
## <a name="in-this-section"></a>Esta sección  
 [Dentro de CustomPeerResolverService: registros de cliente](../../../../docs/framework/wcf/feature-details/inside-the-custompeerresolverservice-client-registrations.md)  
  
## <a name="see-also"></a>Vea también

- [Conceptos del canal del mismo nivel](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md)
- [Seguridad del canal del mismo nivel](../../../../docs/framework/wcf/feature-details/peer-channel-security.md)
- [Creación de una aplicación de canal del mismo nivel](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)

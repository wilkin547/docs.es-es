---
title: Resoluciones del mismo nivel
ms.date: 03/30/2017
ms.assetid: d86d12a1-7358-450f-9727-b6afb95adb9c
ms.openlocfilehash: ef72f44a7dd7f3e8f3108e4f77dcdbdf8ef1b1b7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554637"
---
# <a name="peer-resolvers"></a>Resoluciones del mismo nivel
Para conectar a una malla, un nodo del mismo nivel necesita las direcciones IP de otros nodos. Las direcciones IP se obtienen al establecer contacto con un servicio de resolución, que toma el identificador de la malla y devuelve una lista de direcciones que corresponden a los nodos registrados con ese identificador de malla concreto. La resolución mantiene una lista de direcciones registradas, que crea mediante el registro de cada nodo de la malla en el servicio.  
  
 Puede especificar qué servicio PeerResolver se debe usar mediante la propiedad `Resolver` de <xref:System.ServiceModel.NetPeerTcpBinding>.  
  
## <a name="supported-peer-resolvers"></a>Resoluciones del mismo nivel compatibles  
 El canal del mismo nivel admite dos tipos de resoluciones: protocolo de resolución de nombres del mismo nivel (PNRP) y servicios de resolución personalizados.  
  
 De forma predeterminada, el canal del mismo nivel usa el servicio de resolución del mismo nivel PNRP para la detección de iguales y vecinos en la malla. En situaciones o plataformas donde PNRP no está disponible o es viable, Windows Communication Foundation (WCF) proporciona un servicio de detección alternativo basado en servidor: el <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> . También puede definir explícitamente un servicio de resolución personalizado escribiendo una clase que implemente la interfaz <xref:System.ServiceModel.PeerResolvers.IPeerResolverContract>.  
  
### <a name="peer-name-resolution-protocol-pnrp"></a>Protocolo de resolución de nombres del mismo nivel (PNRP)  
 PNRP, el solucionador predeterminado para Windows Vista, es un servicio de resolución de nombres distribuido y sin servidor. PNRP también se puede usar en Windows XP SP2 mediante la instalación del paquete de red avanzada. Cualquiera de los dos clientes que ejecuten la misma versión de PNRP pueden localizarse mediante este protocolo, siempre y cuando cumplan ciertas condiciones (como la falta de un firewall corporativo intermedio). Tenga en cuenta que la versión de PNRP que se incluye con Windows Vista es más reciente que la versión incluida en el paquete de redes avanzadas. Consulte el centro de descarga de Microsoft para obtener las actualizaciones de PNRP para Windows XP SP2.  
  
### <a name="custom-resolver-services"></a>Servicios de resolución personalizados  
 Cuando el servicio PNRP no está disponible o cuando se desea el control absoluto de la forma de la malla, se puede usar un servicio de resolución personalizado basado en servidor. Este servicio se puede definir explícitamente escribiendo una clase de resolución que implemente la interfaz <xref:System.ServiceModel.PeerResolvers.IPeerResolverContract> o utilizando la implementación predeterminada de la bandeja de entrada, <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>.  
  
 Bajo la implementación predeterminada del servicio, los registros de cliente expiran después de una cierta cantidad de tiempo si el cliente no actualiza explícitamente el registro. Los clientes que usen el servicio de resolución deben reconocer el límite máximo de la latencia cliente-servidor para actualizar a tiempo y correctamente los registros. Esto implica elegir un tiempo de espera de actualización adecuado (`RefreshInterval`) en el servicio de resolución. (Para obtener más información, vea [dentro de CustomPeerResolverService: Client registrations](inside-the-custompeerresolverservice-client-registrations.md)).  
  
 El escritor de la aplicación también ha de tener en cuenta la seguridad de la conexión entre los clientes y el servicio de resolución personalizado. Puede hacer esto mediante la configuración de seguridad en <xref:System.ServiceModel.NetTcpBinding> que los clientes usan para ponerse en contacto con el servicio de resolución. Debe especificar las credenciales (si se usan) en el `ChannelFactory` que se usa para crear el canal del mismo nivel. Estas credenciales se pasan a `ChannelFactory` que se usa para crear los canales a la resolución personalizada.  
  
> [!NOTE]
> Al utilizar redes locales e improvisadas con una resolución personalizada, se aconseja que las aplicaciones que usen o admitan redes locales e improvisadas incluyan una lógica que seleccione una dirección única de vínculo local que se use a la hora de la conexión. Esto evita cualquier confusión potencial producida por equipos con varias direcciones de vínculo local. De acuerdo con esto, el canal del mismo nivel solo admite el uso de una única dirección de vínculo local en un momento determinado. Puede especificar esta dirección con la propiedad `ListenIpAddress` en el <xref:System.ServiceModel.NetPeerTcpBinding>.  
  
 Para obtener una demostración de cómo implementar un solucionador personalizado, vea [resolución del mismo nivel personalizada del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90)).  
  
## <a name="in-this-section"></a>En esta sección  
 [Dentro de CustomPeerResolverService: registros de cliente](inside-the-custompeerresolverservice-client-registrations.md)  
  
## <a name="see-also"></a>Vea también

- [Conceptos del canal del mismo nivel](peer-channel-concepts.md)
- [Seguridad del canal del mismo nivel](peer-channel-security.md)
- [Creación de una aplicación de canal del mismo nivel](building-a-peer-channel-application.md)

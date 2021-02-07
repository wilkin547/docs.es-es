---
description: 'Más información acerca de: cuotas de transporte'
title: Cuotas de transporte
ms.date: 03/30/2017
helpviewer_keywords:
- transport quotas [WCF]
ms.assetid: 3e71dd3d-f981-4d9c-9c06-ff8abb61b717
ms.openlocfilehash: 0359d088402235a34b8cf1d13820c0a7c920b023
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752631"
---
# <a name="transport-quotas"></a>Cuotas de transporte

Las cuotas de transporte son un mecanismo de directivas para decidir cuándo una conexión está utilizando recursos excesivos. Una cuota es un límite que evita una vez el uso de recursos adicionales una vez que se supera el valor de cuota. Las cuotas de transporte evitan los ataques de denegación de servicio (DoS) malintencionados o involuntarios.  
  
 Los transportes de Windows Communication Foundation (WCF) tienen valores de cuota predeterminados que se basan en una asignación conservadora de recursos. Estos valores predeterminados son convenientes para entornos de desarrollo y pequeños escenarios de instalación. Los administradores del servicio deberían revisar las cuotas de transporte y ajustar los valores de la cuota individual si una instalación se está quedando sin recursos o si se limitan las conexiones a pesar de la disponibilidad de recursos adicionales.  
  
## <a name="types-of-transport-quotas"></a>Tipos de cuotas de transporte  

 Los transportes WCF tienen tres tipos de cuotas:  
  
- Los *tiempos de espera* mitigan los ataques de denegación de servicio que se basan en la vinculación de recursos durante un período de tiempo prolongado.  
  
- Los *límites de asignación de memoria* impiden que una sola conexión agote la memoria del sistema y deniegue el servicio a otras conexiones.  
  
- Los límites de tamaño de la *colección limitan* el consumo de recursos que asignan memoria indirectamente o se encuentran en un suministro limitado.  
  
## <a name="transport-quota-descriptions"></a>Descripciones de la cuota de transporte  

 En esta sección se describen las cuotas de transporte disponibles para los transportes WCF estándar: HTTP (S), TCP/IP y canalizaciones con nombre. Los transportes personalizados pueden exponer sus propias cuotas configurables no incluidas en esta lista. Consulte la documentación de un transporte personalizado para averiguar sus cuotas.  
  
 Cada valor de cuota tiene un tipo, valor mínimo y valor predeterminado. Su tipo limita el valor máximo de una cuota. Debido a las limitaciones de los equipos, no siempre es posible establecer una cuota en su valor máximo.  
  
|Nombre|Tipo|Mín.<br /><br /> value|Default<br /><br /> value|Descripción|  
|----------|----------|--------------------|-----------------------|-----------------|  
|`ChannelInitializationTimeout`|TimeSpan|1 tic|5 segundos|Tiempo máximo a esperar para que una conexión envíe el preámbulo durante la lectura inicial. Estos datos se reciben antes de que se produzca la autenticación. Este valor es generalmente mucho más pequeño que el valor de cuota de `ReceiveTimeout`.|  
|`CloseTimeout`|TimeSpan|0|1 min|El tiempo máximo que se ha de esperar para que una conexión se cierre antes de que el transporte produzca una excepción.|  
|`ConnectionBufferSize`|Entero|1|8 KB|Tamaño, en bytes, de los búfers de transmisión y recepción del transporte subyacente. Si se aumenta el tamaño de búfer, se puede mejorar el rendimiento al enviar mensajes grandes.|  
|`IdleTimeout`|TimeSpan|0|2 min|Tiempo máximo que una conexión agrupada puede permanecer inactiva antes de cerrarse.<br /><br /> Este ajuste solo se aplica a las conexiones agrupadas.|  
|`LeaseTimeout`|TimeSpan|0|5 min|Duración máxima de una conexión agrupada activa. Después de que transcurra la hora especificada, la conexión se cierra después de que se repare la solicitud actual.<br /><br /> Este ajuste solo se aplica a las conexiones agrupadas.|  
|`ListenBacklog`|Entero|1|10|Número máximo de conexiones que el agente de escucha puede tener sin atender antes de que se denieguen las conexiones adicionales a ese punto de conexión.|  
|`MaxBufferPoolSize`|long|0|512 KB|Memoria máxima, en bytes, que el transporte dedica a agrupar los búferes de mensajes reutilizables. Cuando el grupo no puede proporcionar un búfer de mensaje, se asigna un nuevo búfer para el uso temporal.<br /><br /> Las instalaciones que crean muchos generadores de canales o agentes de escucha pueden asignar grandes cantidades de memoria para grupos de búferes. Reducir este tamaño de búfer puede reducir en gran mediad el uso de memoria en este escenario.|  
|`MaxBufferSize`|Entero|1|64 KB|Tamaño máximo, en bytes, de un búfer utilizado para la secuenciación de datos. Si no se establece esta cuota de transporte, o el transporte no está utilizando la transmisión por secuencias, el valor de cuota es igual que el valor de cuota `MaxReceivedMessageSize` o <xref:System.Int32.MaxValue>, lo que sea más pequeño.|  
|`MaxOutboundConnectionsPerEndpoint`|Entero|1|10|Número máximo de conexiones salientes que pueden asociarse a un punto de conexión determinado.<br /><br /> Este ajuste solo se aplica a las conexiones agrupadas.|  
|`MaxOutputDelay`|TimeSpan|0|200 ms|Tiempo máximo que se debe esperar después de una operación de envío para procesar por lotes los mensajes adicionales en una única operación. Se envían los mensajes antes si el búfer del transporte subyacente se llena. Mediante el envío de mensajes adicionales, no se restablece el período del retraso.|  
|`MaxPendingAccepts`|Entero|1|1|Número máximo de aceptaciones para los canales que el agente de escucha puede tener en espera.<br /><br /> Hay un intervalo de tiempo entre la completación de la aceptación y el inicio de una nueva aceptación. El aumento de este tamaño de colección puede evitar que se quiten clientes que conecten durante este intervalo.|  
|`MaxPendingConnections`|Entero|1|10|Número máximo de conexiones que el agente de escucha puede tener en espera para que la aplicación las acepte. Cuando se supera este valor de cuota, se pierden las nuevas conexiones entrantes en lugar de esperar a ser aceptadas.<br /><br /> Características de conexión como la seguridad de mensaje pueden hacer que un cliente abra más de una conexión. Los administradores de servicio deberían tener en cuenta estas conexiones adicionales al establecer este valor de cuota.|  
|`MaxReceivedMessageSize`|long|1|64 KB|Tamaño máximo, en bytes, de un mensaje recibido, incluyendo los encabezados, antes de que el transporte produzca una excepción.|  
|`OpenTimeout`|TimeSpan|0|1 min|El tiempo máximo que se ha de esperar para que una conexión se establezca antes de que el transporte produzca una excepción.|  
|`ReceiveTimeout`|TimeSpan|0|10 min|El tiempo máximo a esperar para que una operación de lectura se complete antes de que el transporte produzca una excepción.|  
|`SendTimeout`|Timespan|0|1 min|El tiempo máximo a esperar para que una operación de escritura se complete antes de que el transporte produzca una excepción.|  
  
 Las cuotas de transporte `MaxPendingConnections` y `MaxOutboundConnectionsPerEndpoint` se combinan en una cuota de transporte única llamada `MaxConnections` cuando se establece a través del enlace o configuración. Solo el elemento de enlace permite ajustar estos valores individualmente. La cuota de transporte `MaxConnections` tiene el mismo mínimo y valores predeterminados.  
  
## <a name="setting-transport-quotas"></a>Establecimiento de cuotas de transporte  

 Las cuotas de transporte se establecen a través del elemento de enlace de transporte, el enlace de transporte, la configuración de la aplicación o la directiva de host. En este documento no se explica cómo establecer transportes mediante la directiva de host. Consulte la documentación del transporte subyacente para descubrir los ajustes de las cuotas de directivas de host. En el tema [configuración de http y https](configuring-http-and-https.md) se describe la configuración de cuota para el controlador de Http.sys. Busque más información en Microsoft Knowledge Base sobre cómo configurar los límites de Windows en HTTP, TCP/IP y conexiones de canalización con nombre.  
  
 Otros tipos de cuotas se aplican indirectamente a los transportes. El codificador del mensaje que utiliza el transporte para transformar un mensaje en bytes puede tener sus propios valores de cuota. No obstante, estas cuotas son independientes del tipo de transporte que se use.  
  
### <a name="controlling-transport-quotas-from-the-binding-element"></a>Control de las cuotas de transporte a partir del elemento de enlace  

 Establecer las cuotas de transporte a través del elemento de enlace proporciona la máxima flexibilidad para controlar el comportamiento del transporte. Los tiempos de espera predeterminados para operaciones de cierre, apertura, recepción y envío se toman del enlace cuando se crea un canal.  
  
|Nombre|HTTP|TCP/IP|Canalización con nombre|  
|----------|----------|-------------|----------------|  
|`ChannelInitializationTimeout`||X|X|  
|`CloseTimeout`||||  
|`ConnectionBufferSize`||X|X|  
|`IdleTimeout`||X|X|  
|`LeaseTimeout`||X||  
|`ListenBacklog`||X||  
|`MaxBufferPoolSize`|X|X|X|  
|`MaxBufferSize`|X|X|X|  
|`MaxOutboundConnectionsPerEndpoint`||X|X|  
|`MaxOutputDelay`||X|X|  
|`MaxPendingAccepts`||X|X|  
|`MaxPendingConnections`||X|X|  
|`MaxReceivedMessageSize`|X|X|X|  
|`OpenTimeout`||||  
|`ReceiveTimeout`||||  
|`SendTimeout`||||  
  
### <a name="controlling-transport-quotas-from-the-binding"></a>Control de las cuotas de transporte a partir del enlace  

 Establecer las cuotas de transporte a través del enlace ofrece un conjunto simplificado de cuotas de entre las que elegir al mismo tiempo que se proporciona acceso a los valores de cuota más comunes.  
  
|Nombre|HTTP|TCP/IP|Canalización con nombre|  
|----------|----------|-------------|----------------|  
|`ChannelInitializationTimeout`||||  
|`CloseTimeout`|X|X|X|  
|`ConnectionBufferSize`||||  
|`IdleTimeout`||||  
|`LeaseTimeout`||||  
|`ListenBacklog`||X||  
|`MaxBufferPoolSize`|X|X|X|  
|`MaxBufferSize`|1|X|X|  
|`MaxOutboundConnectionsPerEndpoint`||2|2|  
|`MaxOutputDelay`||||  
|`MaxPendingAccepts`||||  
|`MaxPendingConnections`||2|2|  
|`MaxReceivedMessageSize`|X|X|X|  
|`OpenTimeout`|X|X|X|  
|`ReceiveTimeout`|X|X|X|  
|`SendTimeout`|X|X|X|  
  
1. La cuota de transporte `MaxBufferSize` solo está disponible en el enlace `BasicHttp`. Los enlaces `WSHttp` son para escenarios que no admitan modos de transporte de transmisión por secuencias.  
  
2. Las cuotas de transporte `MaxPendingConnections` y `MaxOutboundConnectionsPerEndpoint` se combinan en una cuota de transporte única llamada `MaxConnections`.  
  
### <a name="controlling-transport-quotas-from-configuration"></a>Control de las cuotas de transporte a partir de la configuración  

 La configuración de la aplicación puede establecer las mismas cuotas de transporte como obtener acceso directamente a las propiedades en un enlace. En archivos de configuración, el nombre de una cuota de transporte se inicia siempre con una minúscula. Por ejemplo, la propiedad `CloseTimeout` en un enlace corresponde al valor `closeTimeout` en la configuración y la propiedad `MaxConnections` en un enlace corresponde al valor `maxConnections` en la configuración.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>

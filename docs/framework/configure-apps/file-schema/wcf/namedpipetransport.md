---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 00631ad88d771ed8f45638f28c84df05917fd3a0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736591"
---
# \<namedPipeTransport>
Define un transporte que hace que un canal transfiera mensajes mediante las canalizaciones con nombre cuando está incluido en un enlace personalizado.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedPipeTransport>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|ChannelInitializationTimeout|Obtiene o establece un <xref:System.TimeSpan> que determina el tiempo máximo que un canal puede estar en el estado de la inicialización antes de que se desconecte.|  
|ConnectionBufferSize|Obtiene o establece el tamaño del búfer usado para transmitir un bloque del mensaje serializado en la conexión del cliente o servicio.|  
|hostNameComparisonMode|Obtiene o establece un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.|  
|manualAddressing|Obtiene o establece un valor que indica si se requiere la dirección manual del mensaje.|  
|maxBufferPoolSize|Obtiene o establece el tamaño máximo, en bytes, de cualquier grupo de búferes utilizado por el transporte.|  
|maxBufferSize|Obtiene o establece el tamaño máximo del búfer que se va a usar. Para mensajes transmitidos por secuencias, este valor debería ser por lo menos el tamaño máximo posible de los encabezados de mensaje, que se leen en modo almacenado en búfer.|  
|maxOutputDelay|Obtiene o establece el intervalo máximo de tiempo que un bloque de mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.|  
|maxPendingAccepts|Obtiene o establece el número máximo de canales que un servicio puede tener en espera en un agente de escucha para procesar conexiones entrantes en el servicio.|  
|maxPendingConnections|Obtiene o establece el número máximo de conexiones pendientes de distribución en el servicio.|  
|maxReceivedMessageSize|Obtiene y establece el tamaño máximo permitido del mensaje, en bytes, que se puede recibir.|  
|transferMode|Obtiene o establece un valor que indica si los mensajes están almacenados en búfer o se transmiten por secuencias mediante el transporte orientado a la conexión.|  
|[\<connectionPoolSettings>de\<namedPipeTransport>](connectionpoolsettings.md)|Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="remarks"></a>Comentarios  
Este transporte utiliza los URI del formulario "net.pipe://hostname/path." Otros componentes URI son opcionales.  
  
El elemento `namedPipeTransport` es el punto inicial para crear un enlace personalizado que implementa el protocolo de transporte de canalizaciones con nombre. Este transporte se utiliza para la comunicación entre WCF y Windows Communication Foundation (WCF) en el equipo.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transportes](../../../wcf/feature-details/transports.md)
- [Elección del transporte](../../../wcf/feature-details/choosing-a-transport.md)
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)

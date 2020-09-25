---
title: <connectionPoolSettings> de <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 53523fd550ecad931bfb2af5eb9beb71c60d44f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176011"
---
# <a name="connectionpoolsettings-of-tcptransport"></a>\<connectionPoolSettings> de \<tcpTransport>

Especifica los valores de grupo de conexiones adicionales para un transporte TCP.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`groupName`|Una cadena que define el nombre del grupo de conexiones que se usa para canales salientes. En modo de transmisión, las conexiones no se comparten, lo cual significa que la agrupación de conexiones está deshabilitada. La cadena predeterminada es “default”. Puede modificar este valor para aislar las conexiones para un cliente determinado en grupos independientes.|  
|`idleTimeout`|Un <xref:System.TimeSpan> positivo que especifica el tiempo máximo que la conexión puede estar inactiva antes de que se desconecte. El valor predeterminado es 00:02:00.|  
|`leaseTimeout`|<xref:System.TimeSpan> que especifica el tiempo después del que se cierra una conexión activa. El valor predeterminado es 00:05:00.<br /><br /> Se cierra una conexión después de que se haya devuelto a la conexión caché y no durante la transmisión activa. El caché de conexión utilizado por el transporte TCP crea conexiones nuevas, como se requiere para cada punto de conexión, hasta el límite del caché establecido por `maxOutboundConnectionsPerEndpoint.`.|  
|`maxOutboundConnectionsPerEndpoint`|Un entero positivo que especifica el número máximo de conexiones a un punto de conexión remoto que inicia el servicio. Las conexiones que sobrepasen el límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite. `idleTimeout` limita la duración en la que las conexiones siguen en cola antes de que se inicie una excepción. El valor predeterminado es 10.<br /><br /> Este atributo limita el número de conexiones activas simultáneas del cliente a un extremo de servicio determinado. Si este valor se supera debido a más conexiones de cliente activas, el servicio puede se le muestre al cliente sin respuesta. En este caso, este valor se debería ajustar para superar el número máximo de conexiones de cliente simultáneas esperadas a un extremo determinado.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|Define un transporte que hace que un canal transfiera mensajes mediante canalizaciones con nombre.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transportes](../../../wcf/feature-details/transports.md)
- [Elección del transporte](../../../wcf/feature-details/choosing-a-transport.md)
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)

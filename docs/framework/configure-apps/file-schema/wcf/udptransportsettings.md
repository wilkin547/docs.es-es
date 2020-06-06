---
title: <udpTransportSettings>
ms.date: 03/30/2017
ms.assetid: 842d92e9-6199-4ec5-b2d1-58533054e1f0
ms.openlocfilehash: bb2ec84caa79f33e1e469592d0eca63d8f461dac
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854862"
---
# \<udpTransportSettings>
Este elemento de configuración expone la configuración de transporte de UDP para [\<udpDiscoveryEndpoint>](udpdiscoveryendpoint.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<udpDiscoveryEndpoint>**](udpdiscoveryendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<updTransportSettings>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint>
        <updTransportSettings duplicateMessageHistoryLength="Integer"
                              maxBufferPoolSize="Integer"
                              maxMulticastRetransmitCount="Integer"
                              maxPendingMessageCount="Integer"
                              maxReceivedMessageSize="Integer"
                              maxUnicastRetransmitCount="Integer"
                              multicastInterfaceId="String"
                              socketReceiveBufferSize="Integer"
                              timeToLive="Integer" />
      </standardEndpoint>
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|duplicateMessageHistoryLength|Entero que especifica el número máximo de hash del mensaje usado por el transporte para identificar los mensajes duplicados.  La detección de duplicados se realizará en el nivel de TransportManager. Al establecer esta propiedad en 0, se deshabilita la detección de duplicados.<br /><br /> Este atributo permite a administradores del sistema o a desarrolladores de software desactivar los algoritmos de detección de mensajes duplicados. Esto puede ser deseable si desea implementar su propio algoritmo de detección de duplicados.<br /><br /> El valor predeterminado es 4112.|  
|maxBufferPoolSize|Entero que especifica el tamaño máximo de cualquier grupo de búferes usado por el transporte.|  
|maxMulticastRetransmitCount|Entero que especifica el número máximo de veces que se debería retransmitir el mensaje (además del primer envío).<br /><br /> El valor predeterminado es 2.|  
|maxPendingMessageCount|Entero que especifica el número máximo de mensajes que se han recibido pero que todavía no se han quitado de InputQueue para una instancia del canal individual.  Si InputQueue ha llegado a su límite del número de mensajes pendiente, se quitará el mensaje.<br /><br /> El valor predeterminado es 32.|  
|maxReceivedMessageSize|Entero que especifica el tamaño máximo de un mensaje que puede ser procesado por el enlace.<br /><br /> El valor predeterminado es 65507.|  
|maxUnicastRetransmitCount|Entero que especifica el número máximo de veces que se debería retransmitir el mensaje (además del primer envío).  Si el mensaje se envía a una dirección de unidifusión y se recibe un mensaje de respuesta con un encabezado RelatesTo correspondiente, a continuación, la retransmisión puede terminar pronto (antes de retransmitir el número configurado de veces).<br /><br /> El valor predeterminado es 1.|  
|multicastInterfaceId|Cadena que identifica de forma única el adaptador de red que se debería usar al enviar y recibir tráfico de multidifusión en equipos de hosts múltiples. En tiempo de ejecución, el transporte usará este valor de atributo para buscar el índice de interfaz, que se usa a continuación para establecer las opciones de socket `IP_MULTICAST_IF` e `IPV6_MULTICAST_IF`.  Se utilizará el mismo índice de interfaz al unirse a un grupo de multidifusión, si procede.<br /><br /> El valor predeterminado es `null`.|  
|socketReceiveBufferSize|Entero que especifica el tamaño del búfer de recepción en el socket de WinSock subyacente.<br /><br /> Un usuario de un canal de recepción puede usar este atributo en el enlace para controlar el comportamiento del sistema al recibir datos.  Por ejemplo, dada una aplicación que usa mensajes WCF entrantes en el umbral máximo, el uso de un valor más alto para este atributo permitiría que los mensajes se apilasen en el búfer de WinSock mientras esperan a que la aplicación pueda procesarlos.  Usar un valor inferior en la misma situación produciría que los mensajes se quitaran. Este atributo expone la opción de socket de WinSock subyacente `SO_RCVBUF` . Este valor de atributo debe ser al menos el tamaño de `maxReceivedMessageSize` .   Si se establece en un valor menor que `maxReceivedMessageSize` , se producirá una excepción en tiempo de ejecución.<br /><br /> El valor predeterminado es 65536.|  
|timeToLive|Entero que especifica el número de saltos de segmentos de red que puede atravesar un paquete de multidifusión.  Este atributo expone la funcionalidad asociada a las opciones de socket `IP_MULTICAST_TTL` e `IP_TTL`.<br /><br /> El valor predeterminado es 1.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<udpDiscoveryEndpoint>](udpdiscoveryendpoint.md)|Punto de conexión estándar que tiene un contrato de detección fijo y enlace de transporte UDP.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Discovery.UdpTransportSettings>

---
title: '&lt;udpTransportSettings&gt; de &lt;udpAnnouncementEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7ddff1a-5eed-4bbc-8580-b95ef8890e1f
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f268d13af484f81e22f05e8917fd129fed68e611
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltudptransportsettingsgt-of-ltudpannouncementendpointgt"></a>&lt;udpTransportSettings&gt; de &lt;udpAnnouncementEndpoint&gt;
Este elemento de configuración expone la configuración de transporte UDP de [ \<udpAnnoucementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md).  
  
\<sistema. ServiceModel >  
\<standardEndpoints >  
\<udpAnnouncementEndpoint >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <udpAnnouncementEndpoint>
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
    </udpAnnouncementEndpoint>
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
|socketReceiveBufferSize|Entero que especifica el tamaño del búfer de recepción en el socket de WinSock subyacente.<br /><br /> Un usuario de un canal de recepción puede usar este atributo en el enlace para controlar el comportamiento del sistema al recibir datos.  Por ejemplo, dada una aplicación que usa mensajes WCF entrantes en el umbral máximo, el uso de un valor más alto para este atributo permitiría que los mensajes se apilasen en el búfer de WinSock mientras esperan a que la aplicación pueda procesarlos.  El uso de un valor inferior en la misma situación tendría como consecuencia quitar los mensajes. Este atributo expone la opción de socket de WinSock `SO_RCVBUF` subyacente. Este valor de atributo debe tener como mínimo, el tamaño de `maxReceivedMessageSize`.   Al establecerlo en un valor menor que `maxReceivedMessageSize`, producirá una excepción en tiempo de ejecución.<br /><br /> El valor predeterminado es 65536.|  
|timeToLive|Entero que especifica el número de saltos de segmentos de red que puede atravesar un paquete de multidifusión.  Este atributo expone la funcionalidad asociada a las opciones de socket `IP_MULTICAST_TTL` e `IP_TTL`.<br /><br /> El valor predeterminado es 1.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<udpAnnoucementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)|punto de conexión estándar que tiene un contrato de anuncio fijo y un enlace de transporte UDP.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Discovery.UdpTransportSettings>

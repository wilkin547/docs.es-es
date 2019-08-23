---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 5c9dbec13dd0d71ba1b92ea971d067540013b6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940314"
---
# <a name="websocketsettings"></a>\<webSocketSettings>
Un elemento de configuración usado para especificar valores de WebSockets.  
  
\<system.ServiceModel>  
\<bindings>  
\<netHttpBinding>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|createNotificationOnConnection|Especifica si se envía una notificación al realizar la conexión.|  
|disablePayloadMasking|Especifica si el enmascaramiento de WebSocket está deshabilitado.|  
|keepAliveInterval|Especifica el intervalo entre mensajes de mantenimiento de conexión.|  
|maxPendingConnections|Especifica el número máximo de conexiones pendientes de distribución en el servicio.|  
|receiveBufferSize|Especifica el tamaño de búfer de recibir.|  
|sendBufferSize|Especifica el tamaño de búfer de enviar.|  
|subProtocol|Especifica el subprotocolo WebSocket.|  
|transportUsage|Especifica cuándo usar WebSockets.|  
  
## <a name="transportusage-attribute"></a>Atributo transportUsage  
  
|Value|DESCRIPCIÓN|  
|-----------|-----------------|  
|WhenDuplex|Use el protocolo WebSocket cuando el contrato sea dúplex.|  
|Siempre|Use siempre el protocolo WebSocket independientemente del contrato.|  
|Nunca|Nunca use el protocolo WebSocket.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|\<netHttpBinding>|Especifica el NetHttpBinding|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar \<el elemento > de webSocketSettings.  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)

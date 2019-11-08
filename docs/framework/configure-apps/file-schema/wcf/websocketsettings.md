---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: fa87a1b0961425d6a9bc84769bef6e87cbc2ce96
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732556"
---
# <a name="websocketsettings"></a>\<webSocketSettings >
Un elemento de configuración usado para especificar valores de WebSockets.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding**](nethttpbinding.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webSocketSettings >**  
  
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
  
|Atributo|Descripción|  
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
  
|Valor|Descripción|  
|-----------|-----------------|  
|WhenDuplex|Use el protocolo WebSocket cuando el contrato sea dúplex.|  
|Siempre|Use siempre el protocolo WebSocket independientemente del contrato.|  
|Never|Nunca use el protocolo WebSocket.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|\<netHttpBinding >|Especifica el NetHttpBinding|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el elemento \<webSocketSettings >.  
  
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
- [\<> de enlace](bindings.md)

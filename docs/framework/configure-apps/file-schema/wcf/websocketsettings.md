---
title: '&lt;webSocketSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 01bc858aeeff750baa3f54e813dea5c9779143f8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltwebsocketsettingsgt"></a>&lt;webSocketSettings&gt;
Un elemento de configuración usado para especificar valores de WebSockets.  
  
\<system.ServiceModel>  
\<enlaces >  
\<netHttpBinding>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<netHttpBinding>  
  <binding>   
    <webSocketSettings createNotificationOnConnection="boolean" 
                       disablePayloadMasking="boolean" 
                       keepAliveInterval="TimeSpan" 
                       maxPendingConnections="Integer" 
                       receiveBufferSize="Integer" 
                       sendBufferSize="Integer" 
                       subProtocol="String" 
                       transportUsage="WhenDuplex/Always/Never"/>
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
|Nunca|Nunca use el protocolo WebSocket.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|\<netHttpBinding>|Especifica el NetHttpBinding|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el \<webSocketSettings > elemento.  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)

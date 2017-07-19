---
title: "&lt;&lt;connectionPoolSettings&gt;&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;&lt;connectionPoolSettings&gt;&gt;
Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.  
  
## Sintaxis  
  
```  
  
<connectionPoolSettings  
        groupName=”String”  
    idleTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint=”Integer” />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`groupName`|Una cadena que define el nombre del grupo de conexiones que se usa para canales salientes.  En modo de transmisión, las conexiones no se comparten, lo cual significa que la agrupación de conexiones está deshabilitada.  La cadena predeterminada es “default”.  Puede modificar este valor para aislar las conexiones para un cliente determinado en grupos independientes.|  
|`idleTimeout`|Un <xref:System.TimeSpan> positivo que especifica el tiempo máximo que la conexión puede estar inactiva antes de que se desconecte.  El valor predeterminado es 00:02:00.|  
|`maxOutboundConnectionsPerEndpoint`|Un entero positivo que especifica el número máximo de conexiones a un extremo remoto que inicia el servicio.  Las conexiones que sobrepasen el límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.  `idleTimeout` limita la duración en la que las conexiones siguen en cola antes de que se inicie una excepción.  El valor predeterminado es 10.<br /><br /> Este atributo limita el número de conexiones activas simultáneas del cliente a un extremo de servicio determinado.  Si este valor se supera debido a más conexiones de cliente activas, el servicio puede se le muestre al cliente sin respuesta.  En este caso, este valor se debería ajustar para superar el número máximo de conexiones de cliente simultáneas esperadas a un extremo determinado.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<namedPipeTransport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|Define un transporte que hace que un canal transfiera mensajes mediante canalizaciones con nombre.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>   
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>   
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>   
 <xref:System.ServiceModel.Channels.TransportBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Transportes](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Elección del transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
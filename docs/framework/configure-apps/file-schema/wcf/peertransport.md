---
title: "&lt;peerTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;peerTransport&gt;
Define un transporte del mismo nivel para un enlace personalizado.  
  
## Sintaxis  
  
```  
  
<peerTransport   
    listenIpAddress="String"  
    maxBufferPoolSize="Integer"  
    maxReceivedMessageSize="Integer"  
    port="Integer"  
        <security>  
    </security>  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|listenIpAddress|Una cadena que especifica una dirección IP en la que el nodo entre pares realizará escuchas para los mensajes del TCP.  De manera predeterminada, es `null`.|  
|maxBufferPoolSize|Un entero positivo que especifica el tamaño máximo del grupo de búferes.  El valor predeterminado es 524288.<br /><br /> Muchas partes de los búferes de uso WCF.  Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.  Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.  Así se evita la sobrecarga al crear y destruir búferes.|  
|maxReceivedMessageSize|Un entero positivo que define el tamaño de mensaje máximo en bytes incluidos los encabezados.  El remitente de un mensaje recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.  El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.  El valor predeterminado es 65536.|  
|puerto|Un entero que especifica el puerto de la interfaz de red en el que este enlace procesará los mensajes de TCP de canal del mismo nivel.  Dicho valor debe encontrarse entre <xref:System.Net.IPEndPoint.MinPort> y <xref:System.Net.IPEndPoint.MaxPort>.  El valor predeterminado es 0.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|Define la configuración de seguridad para este transporte.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Comentarios  
 Este transporte no se puede utilizar con contratos que tengan operaciones respuesta\-solicitud.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.PeerTransportElement>   
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>   
 <xref:System.ServiceModel.Channels.TransportBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Transportes](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Elección del transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
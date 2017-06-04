---
title: "&lt;oneWay&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;oneWay&gt;
Habilita el enrutamiento de paquetes y el uso de métodos unidireccionales para un enlace personalizado.  
  
## Sintaxis  
  
```  
  
<oneWay packetRoutable="Boolean">  
        <channelPoolSettings  
           idleTimeout"TimeSpan"  
          leaseTimeout"TimeSpan"  
          maxOutboundConnectionsPerEndpopint=”Integer” />  
```  
  
```  
  
</oneWay>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`packetRoutable`|Un valor booleano que especifica si se habilita el enrutamiento del paquete.  De manera predeterminada, es `false`.|  
|`MaxAcceptedChannels`|Un entero que especifica el número máximo de canales que se pueden aceptar.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<channelPoolSettings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|Un objeto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> que contiene propiedades del grupo de canales para el canal actual.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Comentarios  
 Para habilitar el enrutamiento de paquetes, se necesita una capa de conversión unidireccional, que proporciona este elemento.  Un usuario puede crear un enlace personalizado que coloque este enlace en una capa a través de un transporte consciente de sesión o de solicitud\/respuesta para que se pueda realizar el enrutamiento de paquetes.  Este elemento también es útil cuando desea exponer los métodos unidireccionales de una manera más nativa.  Se pueden aplicar más transformaciones sobre esta capa, como Dúplex Compuesto y Mensajería de confianza.  
  
## Vea también  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>   
 <xref:System.ServiceModel.Configuration.OneWayElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
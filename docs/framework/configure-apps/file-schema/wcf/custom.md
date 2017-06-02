---
title: "&lt;personalizadas&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;personalizadas&gt;
Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.  
  
## Sintaxis  
  
```  
  
<custom address="Uri"  
   resolverType="String">  
      <headers/>  
   <identity/>  
</peerResolver>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`address`|Un URI que especifica la dirección de extremo del nodo de iguales que hospeda el servicio de resolución del mismo nivel personalizado.|  
|`resolverType`|Una cadena que especifica el tipo de servicio de resolución del mismo nivel personalizado.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<identidad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Especifica la identidad para las resoluciones del mismo nivel personalizadas configuradas con este elemento.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.IdentityElement>.|  
|[\<encabezados\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Una colección de encabezado de dirección usada para mensajes SOAP administrados por la resolución del mismo nivel personalizada.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<resolver\>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|Una resolución del mismo nivel que se usa para resolver un Id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.|  
  
## Comentarios  
 Este elemento define la configuración básica para un servicio de la resolución del mismo nivel personalizado, incluso la dirección de extremo del igual que hospeda el servicio y cualquier configuración obligatoria concreta.  Para obtener más información acerca de cómo crear una resolución personalizada, vea [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/es-es/12aa3787-2962-439c-ad27-46523c8b0419).  
  
## Vea también  
 <xref:System.Servicemodel.PeerResolvers.CustomPeerResolverService>   
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>   
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>   
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>   
 [Resoluciones del mismo nivel](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)   
 [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/es-es/12aa3787-2962-439c-ad27-46523c8b0419)
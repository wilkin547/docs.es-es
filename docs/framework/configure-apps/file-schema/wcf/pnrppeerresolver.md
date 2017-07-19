---
title: "&lt;pnrpPeerResolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;pnrpPeerResolver&gt;
Especifica que la resolución de PNRP \(Protocolo de resolución de nombres de mismo nivel\) será utilizada como resolución.  Este elemento es opcional porque PNRP es la resolución predeterminada.  
  
## Sintaxis  
  
```  
  
<pnrpResolver resolverType="String" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|resolverType|Una cadena que especifica la resolución que se va a utilizar.  Este atributo es opcional.  Si no se establece, o si está establecido en una cadena vacía, se utiliza PNRP.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Ejemplo  
  
```  
<pnrpResolver resolverType="" />  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>   
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [Resoluciones del mismo nivel](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
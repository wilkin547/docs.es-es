---
title: "&lt;remove&gt; del elemento &lt;claimTypeRequirements&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;remove&gt; del elemento &lt;claimTypeRequirements&gt;
Especifica los tipos de notificaciones que se van a quitar en la credencial aliada.  
  
## Sintaxis  
  
```  
  
<claimTypeRequirements>  
      <remove claimType="URI" />  
</claimTypeRequirements>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|claimType|URI que define el tipo de una notificación que se va a eliminar.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<claimTypeRequirements\>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|Especifica una colección de tipos de notificación requeridos.  Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.<br /><br /> En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.  Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.  Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.|  
  
## Vea también  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>   
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>   
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>   
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>   
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
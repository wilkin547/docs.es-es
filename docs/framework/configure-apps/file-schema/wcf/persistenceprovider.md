---
title: "&lt;persistenceProvider&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;persistenceProvider&gt;
Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.  
  
## Sintaxis  
  
```  
  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|persistenceOperationTimeout|Un valor <xref:System.TimeSpan> que especifica el tiempo de espera usado en las operaciones de persistencia.  El valor predeterminado es "00:00:30".|  
|tipo|Una cadena que especifica el tipo del generador del proveedor de persistencia que se va a usar.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## Comentarios  
 Este elemento especifica el proveedor de persistencia que se va a utilizar para serializar el estado de un servicio WCF.  Se debería utilizar junto con `wsHttpContextBinding` que pasa la información de estado en encabezados HTTP.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>   
 <xref:System.ServiceModel.Persistence.PersistenceProvider>